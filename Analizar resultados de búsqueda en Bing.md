# Analizar resultados de búsqueda en Bing
## PowerShell 
### URL: https://www.jesusninoc.com/2015/03/02/analizar-resultados-de-busqueda-en-bing/
```PowerShell
#Leer nombres en un fichero para realizar la búsqueda en Bing, almacenar en un fichero los resultados y la fecha de ejecución
Get-Content F:\power\nombres.txt | %{

#La primera búsqueda se realiza con el nombre que aparece en el fichero
$urls=’https://www.bing.com/search?q=’+ $_
$result=Invoke-WebRequest $urls
$valor=($result.AllElements | ? {$_.class -eq “sb_count”}).innerText
$valor=$valor.Trim()
Get-Date | Out-File F:\power\datosjesusninocbing.txt -Append
$_ | Out-File F:\power\datosjesusninocbing.txt -Append
$valor | Out-File F:\power\datosjesusninocbing.txt -Append

#La segunda búsqueda se realiza con el nombre que aparece en el fichero convertido a minúsculas
$lower=$_.tolower()
$urls=’https://www.bing.com/search?q=’+ $lower
$result=Invoke-WebRequest $urls
$valor=($result.AllElements | ? {$_.class -eq “sb_count”}).innerText
$valor=$valor.Trim()
Get-Date | Out-File F:\power\datosjesusninocbing.txt -Append
$lower | Out-File F:\power\datosjesusninocbing.txt -Append
$valor | Out-File F:\power\datosjesusninocbing.txt -Append

#La tercera búsqueda se realiza con el nombre que aparece en el fichero convertido a mayúsculas
$upper=$_.ToUpper()
$urls=’https://www.bing.com/search?q=’+ $upper
$result=Invoke-WebRequest $urls
$valor=($result.AllElements | ? {$_.class -eq “sb_count”}).innerText
$valor=$valor.Trim()
Get-Date | Out-File F:\power\datosjesusninocbing.txt -Append
$upper | Out-File F:\power\datosjesusninocbing.txt -Append
$valor | Out-File F:\power\datosjesusninocbing.txt -Append
}

```
