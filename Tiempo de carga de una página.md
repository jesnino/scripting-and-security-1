# Tiempo de carga de una página
## PowerShell 
### URL: https://www.jesusninoc.com/2016/06/07/tiempo-de-carga-de-una-pagina/
```PowerShell
Get-Content 'F:\urls.txt' | %{
$Comienzo = Get-Date
(Invoke-WebRequest $_).statuscode
$Tiempo = ((Get-Date) - $Comienzo).TotalMilliseconds
Write-Host URL $_ Tiempo $Tiempo ms -ForegroundColor Green
}

```
