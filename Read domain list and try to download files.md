# Read domain list and try to download files
## PowerShell, Security, Servers 
### URL: https://www.jesusninoc.com/2014/01/27/read-domain-list-and-try-to-download-files/
```PowerShell
#Read domains
foreach ($i in Get-Content .\dominios.txt)
{
    (Invoke-WebRequest $i).StatusCode

    #Domains and files
    foreach ($carpetas in Get-Content .\carpetas.txt)
    {
        $url=$i+"/"+$carpetas
        (Invoke-WebRequest $url).StatusCode
    }
}

```
