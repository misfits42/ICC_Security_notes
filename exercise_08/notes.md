# ICC Security - Exercise 08 - Threats on the Network

Conduct a survey of the target:

- systeminfo/permissions
  - `run multicommand -cl "systeminfo"`
- process list
  - `ps`
- netstat/ifconfig/ipconfig
  - `netstat`, `run multicommand -cl "netstat"`
  - `ipconfig`, `run multicommand -cl "ipconfig"`
- persistence vectors
  - Run keys:
    - `HKLM\Software\Microsoft\Windows\CurrentVersion\Run`
    - `HKLM\Software\Microsoft\Windows\CurrentVersion\RunOnce`
    - `HKU\<user_sid>\Software\Microsoft\Windows\CurrentVersion\Run`
    - `HKU\<user_sid>\Software\Microsoft\Windows\CurrentVersion\RunOnce`
- files around the same date/time as any suspicious files
  - Can use powershell (run through "multicommand") to look at file times around times of suspect file. This is provided that the compromised machine has powershell installed.
    - `run multicommand -cl 'powershell -noprofile -command "$bad_time = Get-Date -Year 2020 -Month 07 -Date 09 -Hour 10 -Minute 45 -Second 15; gci -path "C:\" -recurse -erroraction silentlycontinue | ? {$_.LastWriteTime -gt $bad_time.AddMinutes(-10) -and $_.LastWriteTime -lt $bad_time.AddMinutes(10)}"'`
- search for more than one instance of a file
  - Again, can use powershell if it is installed on the compromised machine.
    - `run multicommand -cl 'powershell -noprofile -command "gci -path "C:\" -Name "bad_file.exe" -Recurse"'`
- check C:\Windows\Temp
  - `run multicommand -cl 'cmd /c dir C:\\Windows\\Temp'`
- parse the registry
  - `reg enumkey -k '...'`
  - `reg enumkey -k '...' -v '...'`
- use strings to view any suspicious files
  - Using sysinternals tool "strings" - may need to be uploaded to compromised machine to ensure we have trusted version of tool to execute.
    - `run multicommand -cl "cmd /c strings.exe <sus_file.exe>"`
- dump the memory for any suspicious processes
  - `run process_memdump -p <PID>`
- view services
  - `run post/windows/gather/enum_services`
- check for unsigned drivers
  - Using sysinternals tool "sigcheck" - may need to be uploaded to compromised machine to ensure we have trusted version of tool to execute.
    - `run multicommand -cl "cmd /c sigcheck.exe -u C:\Windows\System32\drivers"`
- view installed applications
  - Check registry entries to view installed applications
    - `run enumkey -k 'HKLM\Software'`
    - `run enumkey -k 'HKLM\Software\Microsoft\Windows\CurrentVersion\Uninstall'`

---

+++
