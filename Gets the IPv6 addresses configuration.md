# Gets the IPv6 addresses configuration
## Network, PowerShell 
### URL: https://www.jesusninoc.com/2016/05/06/gets-the-ipv6-addresses-configuration/
```PowerShell
Get-NetIPAddress | Where-Object AddressFamily -EQ IPv6 | Select-Object IPAddress

```
