# Email address search
## PowerShell 
### URL: https://www.jesusninoc.com/2012/12/29/email-address-search/
```PowerShell
for($i=1;$i -le 2;$i++){
$urls="https://www.example.com/example.asp?Ref=" + $i + "&let"
$results=Invoke-WebRequest $urls
$en=($results.links).href
foreach($tu in $en)
{
if($tu -match "\b[A-Z0-9._%+-]+@[A-Z0-9.-]+\.[A-Z]+\b"){$tu}
}
}

```
