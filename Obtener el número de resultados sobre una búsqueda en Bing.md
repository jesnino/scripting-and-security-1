# Obtener el número de resultados sobre una búsqueda en Bing
## PowerShell, Web scraping 
### URL: https://www.jesusninoc.com/2015/12/18/obtener-el-numero-de-resultados-sobre-una-busqueda-en-bing/
```PowerShell
$url='https://www.bing.com/search?q=powershell'
$result = Invoke-WebRequest $url
$result.AllElements | Where Class -eq “sb_count” | %{$_.innerText}

```
