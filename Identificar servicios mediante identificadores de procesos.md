# Identificar servicios mediante identificadores de procesos
## PowerShell, Processes, Services 
### URL: https://www.jesusninoc.com/2015/10/19/identificar-servicios-mediante-identificadores-de-procesos/
```PowerShell
Get-WmiObject -Class Win32_Service | Select-Object Name,ProcessID

```
