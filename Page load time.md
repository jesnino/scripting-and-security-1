# Page load time
## PowerShell 
### URL: https://www.jesusninoc.com/2014/10/05/page-load-time/
```PowerShell
Get-Content "C:\urls.txt" | %{
$Start = Get-Date
(Invoke-WebRequest $_).statuscode
$TimeTaken = ((Get-Date) - $Start).TotalMilliseconds
Write-Host URL $_ Request $i took $TimeTaken ms -ForegroundColor Green
}

```
