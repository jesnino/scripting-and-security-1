# Almacenar entradas caché DNS en un fichero
## Network, PowerShell 
### URL: https://www.jesusninoc.com/2016/10/21/almacenar-entradas-cache-dns-en-un-fichero/
```PowerShell
while($true){Get-DnsClientCache | Select-Object Entry,Data | Out-File d:\entradasydatoDNS.txt -Append;Start-Sleep -Seconds 10}

```
