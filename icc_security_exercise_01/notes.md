# ICC Security - Exercise 01 - Metasploit

Log all commands entered using script command:

Initialise msfdb and start using command: `msfdb init` and `msfdb start`.

## Q1

![](images/2020-06-30-09-45-08.png)

## Q2

![](images/2020-06-30-09-48-38.png)

## Q3

![](images/2020-06-30-09-50-09.png)

![](images/2020-06-30-09-56-11.png)

## Q4

![](images/2020-06-30-09-52-56.png)

## Q5

![](images/2020-06-30-09-53-22.png)

## Q6

![](images/2020-06-30-09-53-54.png)

## Q7

![](images/2020-06-30-09-57-47.png)

## Q8

![](images/2020-06-30-09-59-27.png)

## Q9

![](images/2020-06-30-10-00-34.png)

## Q10

![](images/2020-06-30-10-01-07.png)

## Q11

![](images/2020-06-30-10-02-29.png)

## Q12

![](images/2020-06-30-10-03-46.png)

## Q13

![](images/2020-06-30-10-05-34.png)

## Q14

![](images/2020-06-30-10-06-26.png)

## Q15

![](images/2020-06-30-10-09-12.png)

## Q16

Determine difference between system boot time (from "systeminfo" command output) and current system time.

![](images/2020-06-30-10-16-43.png)

## Q17

![](images/2020-06-30-10-18-55.png)

![](images/2020-06-30-10-19-11.png)

## Q18

![](images/2020-06-30-10-19-31.png)

## Q19

![](images/2020-06-30-10-19-47.png)

## Q20

![](images/2020-06-30-10-20-28.png)

## Q21

Yes - "systeminfo" output indicates that a hypervisor has been detected, indicating the target machine is running as a VM.

## Q22

![](images/2020-06-30-10-22-06.png)

![](images/2020-06-30-10-22-17.png)

![](images/2020-06-30-10-22-32.png)

## Q23

![](images/2020-06-30-10-23-34.png)

## Q24

![](images/2020-06-30-10-24-20.png)

## Q25

Process hosting the Meterpreter shell is running as local SYSTEM, so has full control over the target machine.

## Q26

No - powershell.exe is not a safe process to be injected into. Command shells are not typically left open the entire time a system is running, so may be closed regularly. It would be better for the Meterpreter shell to be injected into a process that is typically not terminated whilst the system is running (e.g. explorer.exe).

## Q27

No - cannot see any sign of security products or malware running in the process list.

## Q28

![](images/2020-06-30-10-32-21.png)

![](images/2020-06-30-10-32-35.png)

![](images/2020-06-30-10-32-53.png)

![](images/2020-06-30-10-33-10.png)

## Q29

![](images/2020-06-30-10-39-08.png)

## Q30

![](images/2020-06-30-10-41-21.png)

## Q31

![](images/2020-06-30-10-45-20.png)

![](images/2020-06-30-10-45-37.png)

## Q32

Ref Q31 screenshots.

10.10.1.1

## Q33

![](images/2020-06-30-10-46-57.png)

## Q34

Yes - firewall is running on target machine.

![](images/2020-06-30-10-48-49.png)

![](images/2020-06-30-10-49-04.png)

![](images/2020-06-30-10-49-19.png)

![](images/2020-06-30-10-49-31.png)

## Q35

Yes - from Meterpreter session, use command: `run countermeasure`.

## Q36

`run multicommand -cl "netsh advfirewall show allprofiles`

## Q37

![](images/2020-06-30-11-13-26.png)

## Q38

ANSWER: Danger 5

## Q39

![](images/2020-06-30-11-17-36.png)

![](images/2020-06-30-11-17-57.png)

## Q40-43

![](images/2020-06-30-11-20-32.png)

## Q44

![](images/2020-06-30-11-28-39.png)

---

+++

---

## Q46

+++

## Q49

ANSWER:
- The first event in the command output (most recent event) at time "29/06/2020 06:40:40" was created when we terminated the Meterpreter session, resulting in the SYSTEM user logon session being terminated.

```
Security log on \\AD:
[138976] Microsoft-Windows-Security-Auditing
   Type:     SUCCESS AUDIT 
   Computer: AD.iccex.com
   Time:     29/06/2020 06:40:40 م   ID:       4634 
An account was logged off.

  Subject:

	Security ID:		S-1-5-18

	Account Name:		AD$

	Account Domain:		ICCEX

	Logon ID:		0xd7c9c

  Logon Type:			3

  This event is generated when a logon session is destroyed. It may be positively correlated with a logon event using the Logon ID value. Logon IDs are only unique between reboots on the same computer.
```
