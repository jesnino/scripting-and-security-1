# Analizar resultados de búsqueda en Google y almacenar el análisis en un fichero
## PowerShell 
### URL: https://www.jesusninoc.com/2015/01/30/analizar-resultados-de-busqueda-en-google-y-almacenar-el-analisis-en-un-fichero/
```PowerShell
#Leer nombres en un fichero para realizar la búsqueda en Google, almacenar en un fichero los resultados del análisis y la fecha de ejecución
Get-Content F:\power\nombres.txt | %{

#La primera búsqueda se realiza con el nombre que aparece en el fichero
$urls=’https://www.google.com/search?q=’+ $_
$result=Invoke-WebRequest $urls
$valor=($result.AllElements | ? {$_.id -eq “resultStats”}).innerText
$valor=$valor.replace(“Aproximadamente”,””)
$valor=$valor.replace(“resultados”,””)
$valor=$valor.Trim()
Get-Date | Out-File F:\power\datosjesusninoc.txt -Append
$_ | Out-File F:\power\datosjesusninoc.txt -Append
$valor | Out-File F:\power\datosjesusninoc.txt -Append

#La segunda búsqueda se realiza con el nombre que aparece en el fichero convertido a minúsculas
$lower=$_.tolower()
$urls=’https://www.google.com/search?q=’+ $lower
$result=Invoke-WebRequest $urls
$valor=($result.AllElements | ? {$_.id -eq “resultStats”}).innerText
$valor=$valor.replace(“Aproximadamente”,””)
$valor=$valor.replace(“resultados”,””)
$valor=$valor.Trim()
Get-Date | Out-File F:\power\datosjesusninoc.txt -Append
$lower | Out-File F:\power\datosjesusninoc.txt -Append
$valor | Out-File F:\power\datosjesusninoc.txt -Append

#La tercera búsqueda se realiza con el nombre que aparece en el fichero convertido a mayúsculas
$upper=$_.ToUpper()
$urls=’https://www.google.com/search?q=’+ $upper
$result=Invoke-WebRequest $urls
$valor=($result.AllElements | ? {$_.id -eq “resultStats”}).innerText
$valor=$valor.replace(“Aproximadamente”,””)
$valor=$valor.replace(“resultados”,””)
$valor=$valor.Trim()
Get-Date | Out-File F:\power\datosjesusninoc.txt -Append
$upper | Out-File F:\power\datosjesusninoc.txt -Append
$valor | Out-File F:\power\datosjesusninoc.txt -Append
}

```
