# Relación entre puertos TCP y procesos
## Network, PowerShell 
### URL: https://www.jesusninoc.com/2016/09/09/relacion-entre-puertos-tcp-y-procesos/
```PowerShell
Get-NetTCPConnection | %{Write-Host (Get-Process -id $_.OwningProcess).Name,$_.RemoteAddress,$_.RemotePort}

```
