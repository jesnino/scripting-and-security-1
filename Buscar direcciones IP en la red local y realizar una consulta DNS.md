# Buscar direcciones IP en la red local y realizar una consulta DNS
## Network, PowerShell 
### URL: https://www.jesusninoc.com/2016/09/01/buscar-direcciones-ip-en-la-red-local-y-realizar-una-consulta-dns/
```PowerShell
(Get-NetNeighbor).IPAddress | Select-String "192.168.1." | % {
Resolve-DnsName $_
}

```
