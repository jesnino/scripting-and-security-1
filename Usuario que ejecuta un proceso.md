# Usuario que ejecuta un proceso
## PowerShell, Processes 
### URL: https://www.jesusninoc.com/2016/04/21/usuario-que-ejecuta-un-proceso-2/
```PowerShell
Get-WmiObject Win32_Process | Select-Object Name,@{n='Owner';e={$_.GetOwner().User}} | Format-Custom

```
# Usuario que ejecuta un proceso
## PowerShell, Processes 
### URL: https://www.jesusninoc.com/2014/04/06/usuario-que-ejecuta-un-proceso/
```PowerShell
$p = Get-WmiObject win32_process -filter "name='explorer.exe'"
$p.getowner().user

```
