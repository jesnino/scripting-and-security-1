# Obtener el fabricante de los dispositivos de las conexiones inalámbricas que están accesibles
## Database, Network, PowerShell, Wireless 
### URL: https://www.jesusninoc.com/2015/01/19/obtener-el-fabricante-de-los-dispositivos-de-las-conexiones-inalambricas-que-estan-accesibles/
```PowerShell
$macwifi=netsh wlan show networks mode=bssid | Select-String '([0-9A-F]{2}[:]){5}([0-9A-F]{2})$' | % {$_.matches} | Select-Object value

foreach($mac in $macwifi.value)
{
$url=”https://standards.ieee.org/cgi-bin/ouisearch?”+$mac.Substring(0,8).replace(':','-')
$url
$result=Invoke-WebRequest $url
#Here are the results of your search through the public section of the IEEE Standards MA-L database report for MAC
($result.AllElements | Where tagName -eq “PRE”).outerText
}

```
