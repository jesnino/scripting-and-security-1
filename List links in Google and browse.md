# List links in Google and browse
## PowerShell 
### URL: https://www.jesusninoc.com/2013/01/01/list-links-in-google-and-browse/
```PowerShell
$urls='https://www.google.es/search?q=powershell'
$result=Invoke-WebRequest $urls

$en=$result.AllElements | ? {$_.tagName -eq "cite"}

foreach($aen in $en.innerText){
    $resulta=Invoke-WebRequest $aen
    echo $aen
    $resulta.AllElements
    sleep -milliseconds 100
}

```
