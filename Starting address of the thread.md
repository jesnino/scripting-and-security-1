# Starting address of the thread
## PowerShell, Processes, Threads 
### URL: https://www.jesusninoc.com/2015/06/12/starting-address-of-the-thread/
```PowerShell
Get-WmiObject -Class Win32_Thread | Select-Object ProcessHandle,StartAddress

```
