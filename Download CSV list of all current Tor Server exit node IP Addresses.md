# Download CSV list of all current Tor Server exit node IP Addresses
## PHP, PowerShell, Security 
### URL: https://www.jesusninoc.com/2016/01/08/download-csv-list-of-all-current-tor-server-exit-node-ip-addresses/
```PowerShell
Set-Content -Path 'D:\power\fichero.csv' -Value (Invoke-WebRequest 'https://torstatus.blutmagie.de/ip_list_exit.php/Tor_ip_list_EXIT.csv').Content -Encoding Byte

```
