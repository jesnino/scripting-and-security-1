# Buscar una palabra en las descripciones de los resultados de una búsqueda en Bing
## PowerShell, Web scraping 
### URL: https://www.jesusninoc.com/2016/01/13/buscar-una-palabra-en-las-descripciones-de-los-resultados-de-una-busqueda-en-bing/
```PowerShell
$url='https://www.bing.com/search?q=powershell'
$result = Invoke-WebRequest $url
$array=@($result.AllElements | Where Class -eq “b_caption”).innerText
for($i=0;$i -lt $array.Length;$i++)
{
if($array[$i] -match 'scripting'){
Write-Host 'Encontrado posición: ' ($i+1) `n'Texto: ' $array[$i]
}
}

```
```PowerShell
@((Invoke-WebRequest 'https://www.bing.com/search?q=powershell').AllElements | Where Class -eq “b_caption”).innerText | Select-String 'scripting'

```
