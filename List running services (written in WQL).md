# List running services (written in WQL)
## PowerShell, Processes, Services 
### URL: https://www.jesusninoc.com/2015/11/14/list-running-services-written-in-wql/
```PowerShell
Get-WmiObject -query "select * from win32_service where state='Running'"

```
