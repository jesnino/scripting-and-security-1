# Relación entre puertos abiertos UDP y lista de puertos de la IANA
## Network, PowerShell 
### URL: https://www.jesusninoc.com/2016/03/02/relacion-entre-puertos-abiertos-udp-y-lista-de-puertos-de-la-iana/
```PowerShell
#Descargar y guardar el listado de puertos
Invoke-WebRequest 'https://www.iana.org/assignments/service-names-port-numbers/service-names-port-numbers.csv' -OutFile d:\service-names-port-numbers.csv

#Relación entre puertos abiertos UDP y lista de puertos
$portscsv=Import-Csv d:\service-names-port-numbers.csv
$listado=$portscsv | Select-Object 'Service Name','Port Number','Transport Protocol' | Where-Object 'Transport Protocol' -EQ udp
Get-NetUDPEndpoint | Select-Object Localaddress,Localport | %{$_.Localaddress; $listado | Select-Object 'Service Name','Port Number' | Where-Object 'Port Number' -EQ $_.Localport}

```
