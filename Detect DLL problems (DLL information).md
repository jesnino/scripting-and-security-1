# Detect DLL problems (DLL information)
## PowerShell, Processes, Security 
### URL: https://www.jesusninoc.com/2014/02/26/detect-dll-problems-dll-information/
```PowerShell
#Getting list of dll files and modules loaded by process
foreach($proces in ((get-process).Modules).ModuleName)
{
#DLL information
$url="https://es.dll-files.com/"+$proces+".html"
$url
((Invoke-WebRequest $url).AllElements | Where Class -eq "body" | Select -ExpandProperty innerText)[1]
}

```
