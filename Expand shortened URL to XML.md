# Expand shortened URL to XML
## PowerShell 
### URL: https://www.jesusninoc.com/2013/03/26/expand-shortened-url-to-xml/
```PowerShell
#Well, it does not work like that

$val=Get-Content f:\val.txt
foreach($part in $val)
{
$ur="https://api.longurl.org/v2/expand?url="+$part
$ur >> f:content.txt
$result=(Invoke-WebRequest -Uri $ur)
$part
[xml]$xm=$result.Content
$xm.response."long-url"."#cdata-section" >> f:content.txt
"---------------------------------------------------------------------------------" >> f:content.txt
}

```
