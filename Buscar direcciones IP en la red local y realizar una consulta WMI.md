# Buscar direcciones IP en la red local y realizar una consulta WMI
## Network, PowerShell 
### URL: https://www.jesusninoc.com/2016/08/23/buscar-direcciones-ip-en-la-red-local-y-realizar-una-consulta-wmi/
```PowerShell
$credencial=Get-Credential
(Get-NetNeighbor).IPAddress | Select-String "192.168.1." | % {
Get-WmiObject -Class Win32_BIOS -ComputerName ($_) -Credential $credencial
}

```
