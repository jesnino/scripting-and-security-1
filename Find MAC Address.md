# Find MAC Address
## Network, PowerShell 
### URL: https://www.jesusninoc.com/2014/12/01/use-powershell-find-mac-address/
```PowerShell
Get-WmiObject win32_networkadapterconfiguration | select description, macaddress

```
```PowerShell
Get-NetAdapter -Physical | Select-Object Name,MacAddress

```
