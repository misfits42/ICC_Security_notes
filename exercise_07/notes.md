# ICC Security - Exercise 07 - Threats on the Target

1. Log on to Ubuntu VM (10.10.1.70) as intern01
   1. `su intern01`
2. Log on to Windows 2012 server (10.10.1.10) as ICCEX\Administrator
3. Switch to Kali box (10.10.1.60)
   1. Start script file to record commands entered and outputs received.
   2. Set up handler to catch reverse shell and execute.
4. Logon to Windows 10 machine (10.10.1.20) as user "ICCEX\intern01"
   1. Visit the site "downloads.iccex.com" and download the file "xmsol.zip"
   2. Unzip "zmsol.zip" using password "FreeGame"
   3. Run the file "xmsol.exe" as local Administrator.
5. Switch back over to Kali box and check that we have caught the reverse shell, starting a meterpreter session

![](images/2020-07-08-11-03-04.png)

![](images/2020-07-08-11-03-55.png)

Target computer localtime at commencement of operation:

![](images/2020-07-08-11-07-59.png)

---

`run multicommand -cl "systeminfo"`

![](images/2020-07-08-11-05-35.png)

---

![](images/2020-07-08-11-06-49.png)

---

![](images/2020-07-08-11-08-59.png)

---

## Q9

```
PID 9780 (xmsol.exe)
```

![](images/2020-07-08-11-10-13.png)

---

## Q10

Look at process list and services running within processes.

```
run multicommand -cl "cmd /c tasklist"
run multicommand -cl "cmd /c tasklist /svc"
```

## Q11

Document one security product process from the process list.

```
MsMpEng.exe

- Process is associated with Windows Defender. Observed to be running the "windefend" service.
```

![](images/2020-07-08-11-13-47.png)

---

## Q12

![](images/2020-07-08-11-14-15.png)

## Q13

![](images/2020-07-08-11-15-06.png)

## Q14

![](images/2020-07-08-11-15-50.png)

## Q15

![](images/2020-07-08-11-16-37.png)

## Q16

Using command: `run multicommand -cl "cmd /c ipconfig /all".

Extract:

![](images/2020-07-08-11-17-29.png)

## Q17

Refer to native "systeminfo" command output.

```
iccex.com
```

## Q19

![](images/2020-07-08-11-31-37.png)

## Q20

![](images/2020-07-08-11-32-16.png)

## Q21

5 local accounts on target.

![](images/2020-07-08-11-34-27.png)

## Q23

![](images/2020-07-08-12-00-14.png)

## Q24

![](images/2020-07-08-12-02-06.png)

## Q25

![](images/2020-07-08-12-06-06.png)

## Q26

![](images/2020-07-08-12-06-47.png)

## Q27

![](images/2020-07-08-13-28-30.png)

## Q28

![](images/2020-07-08-13-30-49.png)

## Q29

![](images/2020-07-08-13-31-31.png)

## Q30

![](images/2020-07-08-13-32-02.png)

## Q31

Target computer has drives "C:\" and "P:\" mounted.

![](images/2020-07-08-13-33-16.png)

## Q32

```
run multicommand -cl "cmd /c schtasks"
```

![](images/2020-07-08-13-34-01.png)

## Q33

![](images/2020-07-08-13-35-14.png)

## Q34

![](images/2020-07-08-13-37-18.png)

## Q35

![](images/2020-07-08-13-39-45.png)

## Q36

![](images/2020-07-08-13-41-31.png)

## Q37

PID 4056 (MsMpEng.exe)

## Q38, Q39

![](images/2020-07-08-13-49-39.png)

## Q40

Windows Defender registry key located at "HKLM\Software\Microsoft\Windows Defender". Cannot see this reg key when querying from Kali box through meterpreter session. However, reg key can be found when using regedit logged on directly to target box.

- Alternative method:
  - Drop into powershell shell from the meterpreter session, then run command: `Get-MpComputerStatus`

![](images/2020-07-08-14-15-58.png)
