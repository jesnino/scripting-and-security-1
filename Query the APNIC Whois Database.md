# Query the APNIC Whois Database
## Database, PowerShell, Servers 
### URL: https://www.jesusninoc.com/2015/01/02/query-apnic-whois-database/
```PowerShell
1..255 | % {
#Query the APNIC Whois Database
[String]$ip='1.1.'+$_+'.1’
$url=’https://wq.apnic.net/apnic-bin/whois.pl?searchtext='+$ip
$url

$result = Invoke-WebRequest $url
$whois=$result.AllElements | Where tagName -eq “pre” | %{$_.innerText}
$fichero='F:\power\resumen\'+$ip.replace(“.”,””)+’.txt’
$whois | Out-File $fichero -Append

$resumen='F:\power\resumen\dominios.txt'
$contact=$whois | Select-String '% Abuse contact for'
$contact | Out-File $resumen -Append

$contact
sleep -Seconds 10
}

```
