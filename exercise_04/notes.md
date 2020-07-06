# ICC Security - Exercise 04 - Security

- Log on to Win7 as user "cchestbridge".
- Open Administrator cmd prompt.
- Execute following command:
  - `nc -l -p 3978 -e cmd.exe`

![](images/2020-07-06-10-41-48.png)

- Setting up bind_tcp handler on Kali box (10.10.1.60)

![](images/2020-07-06-10-44-49.png)

![](images/2020-07-06-10-53-41.png)

![](images/2020-07-06-10-56-33.png)

![](images/2020-07-06-10-57-53.png)

- Meterpreter session upgrade did not work. Error message presented on Win7 machine:

![](images/2020-07-06-10-59-25.png)

- Kill the job started to handle the reverse connection from meterpreter session.
- Try to upgrade the shell session again.

![](images/2020-07-06-11-01-15.png)

![](images/2020-07-06-11-01-40.png)

![](images/2020-07-06-11-01-53.png)

## Q1

Document the full path of the four most common registry keys/values used to provide application persistence.

```
HKLM\Software\Microsoft\Windows\Currentversion\Run

HKLM\Software\Microsoft\Windows\Currentversion\RunOnce

HKCU\Software\Microsoft\Windows\Currentversion\Run

HKCU\Software\Microsoft\Windows\Currentversion\RunOnce
```

## Q2

What is the date and time on the target?

![](images/2020-07-06-14-13-13.png)

## Q3

Identify and document the name of the target machine.

```
EX-WIN7
```

![](images/2020-07-06-11-09-16.png)

## Q4

Identify and document the operating system and service pack (if any).

```
Windows 7 (Build 7601, Service Pack 1)
```

## Q5

SYSTEM is the authority/account that is running.

```
False

> The session is running as the account used to run the original nc command on the Win7 machine.
```

## Q6

What PID and process is Meterpreter injected into?

![](images/2020-07-06-11-11-59.png)

![](images/2020-07-06-11-12-25.png)

```
PID 3216 (YAkQK.exe)
```

---

## Privilege Escalation

Check current privilege in meterpreter session with:
`run post/windows/gather/win_privs`

![](images/2020-07-06-11-14-50.png)

![](images/2020-07-06-11-15-26.png)

Migrate to another less obvious SYSTEM process:

![](images/2020-07-06-11-16-46.png)

![](images/2020-07-06-11-17-01.png)

---

## Q7

Identify and document the suspect's account name.

```
cchestbridge
```

![](images/2020-07-06-11-19-36.png)

## Q8

What is the IP address of the target?

```
10.10.1.30
```

![](images/2020-07-06-11-20-17.png)

## Q9

Identify the Meterpreter reverse shell process.

```
PID 3216 (YAkQK.exe)
```

![](images/2020-07-06-11-21-25.png)

## Q10

What security product is present?

```
MS Security Essentials
```

- Looking at process list does not indicate individual process tied to a particular security product.
- Looking at services running in each process, there is an instance of svchost.exe (PID 2632) running the "WinDefend" service, which is part of MS Security Essentials.

![](images/2020-07-06-11-30-43.png)

## Q11

What is the name of the executable associated with the security product?

```
svchost.exe
```

![](images/2020-07-06-11-33-09.png)

## Q12

What is the display name of the security product?

```
Windows Defender
```

## Q13

Document the full directory path from which the security product is running.

```
C:\Windows\System32
```

## Q14

The only established network connections originate from the current operation.

```
True

> Only two ESTABLISHED network connections exist, relating to the two sessions with the target box (nc.exe - cmd shell, and YAkQK.exe - meterpreter reverse shell).
```

![](images/2020-07-06-11-37-04.png)

---

![](images/2020-07-06-11-38-47.png)

---

## Q19

The actions of this operation were logged by the security product.

```
False
```

![](images/2020-07-06-12-47-41.png)

---

![](images/2020-07-06-12-37-16.png)

![](images/2020-07-06-12-42-21.png)

---
