# States for threads
## PowerShell, Processes, Threads 
### URL: https://www.jesusninoc.com/2015/03/11/states-for-threads/
```PowerShell
(Get-WmiObject -Class Win32_Thread) | Select-Object ProcessHandle,ThreadState | Sort-Object ProcessHandle

```
```PowerShell
(Get-Process).Threads | Select-Object Id,ThreadState | Sort-Object Id

```
