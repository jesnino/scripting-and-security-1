# Listar las entradas de la caché del cliente DNS local
## Network, PowerShell 
### URL: https://www.jesusninoc.com/2016/10/02/listar-las-entradas-de-la-cache-del-cliente-dns-local/
```PowerShell
Get-DnsClientCache | Select-Object Entry

```
