# Encontrar una clase WMI
## PowerShell, Processes, Services 
### URL: https://www.jesusninoc.com/2015/11/11/encontrar-una-clase-wmi/
```PowerShell
Get-WmiObject -List | Where-Object { $_.name -match 'Service'}

```
