# Expand shortened URL to JSON
## PowerShell 
### URL: https://www.jesusninoc.com/2013/03/26/expand-shortened-url-to-json/
```PowerShell
#Well, it does not work like that

$val=Get-Content F:\power\val.txt
foreach($part in $val)
{
$ur="https://api.longurl.org/v2/expand?url="+$part+"&format=json"
$ur >> f:content2.txt
$result=(Invoke-WebRequest -Uri $ur)
$part
$conv=$result.Content | ConvertFrom-JSON
$conv."long-url" >> F:\power\content2.txt
"---------------------------------------------------------------------------------" >> F:\power\content2.txt
}

```
