# Search “PowerShell” in Google
## PowerShell 
### URL: https://www.jesusninoc.com/2014/02/05/search-powershell-in-google/
```PowerShell
$IE= new-object -com InternetExplorer.Application
$IE.navigate2(“https://www.google.es”)

while ($IE.busy) {
sleep -milliseconds 10000
}

$IE.visible=$true
$IE.Document.getElementById(“q”).value="""powershell"""+" inurl:jesusninoc.com”+""
$IE.visible=$false
$IE.visible=$true
$IE.Document.getElementById(“gbqf”).submit()

while ($IE.busy) {
sleep -milliseconds 10000
}

$links=@($ie.document.getElementsByTagName(“a”))
$arra = "google"

foreach($a in $links)
{
foreach($b in $arra)
{
if (($a.href).contains($b))
{
}
else
{
$a | select href
}
}
}

```
