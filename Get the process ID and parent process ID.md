# Get the process ID and parent process ID
## PowerShell, Processes 
### URL: https://www.jesusninoc.com/2015/08/21/get-the-process-id-and-parent-process-id/
```PowerShell
(Get-WmiObject win32_process) | Select-Object ProcessId,Description,ParentProcessId

```
