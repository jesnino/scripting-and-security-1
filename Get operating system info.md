# Get operating system info
## PowerShell, Processes, Services 
### URL: https://www.jesusninoc.com/2015/02/17/get-operating-system-info/
```PowerShell
$computer=’.’
Get-WmiObject Win32_ComputerSystem -cn $computer
Get-WmiObject Win32_Group -cn $computer
Get-WmiObject Win32_LogicalDisk -cn $computer
Get-WmiObject Win32_NetworkClient -cn $computer
Get-WmiObject Win32_NetworkConnection -cn $computer
Get-WmiObject Win32_NetworkLoginProfile -cn $computer
Get-WmiObject Win32_NTLogEvent -cn $computer
Get-WmiObject Win32_OperatingSystem -cn $computer
Get-WmiObject Win32_Process -cn $computer
Get-WmiObject Win32_Product -cn $computer
Get-WmiObject Win32_QuickFixEngineering -cn $computer
Get-WmiObject Win32_Service -cn $computer
Get-WmiObject Win32_Share -cn $computer
Get-WmiObject Win32_StartupCommand -cn $computer
Get-WmiObject Win32_UserAccount -cn $computer
Get-WmiObject Win32_Volume -cn $computer

```
