# Buscar varias palabras dentro de las descripciones de los resultados de una búsqueda en Google (recorriendo varias páginas de la búsqueda)
## Automation, PowerShell, Web scraping 
### URL: https://www.jesusninoc.com/2015/12/07/buscar-varias-palabras-dentro-de-las-descripciones-de-los-resultados-de-una-busqueda-en-google-recorriendo-varias-paginas-de-la-busqueda/
```PowerShell
for($pagina=0;$pagina -lt 250;$pagina=$pagina+10)
{
#Fichero con las palabras que hay que buscar dentro de las descripciones de los resultados de una búsqueda en Google
$ficheropalabras=gc D:\power\ficheropalabras.txt
Write-Host '--------------------------------------------------------------------'
$url='https://www.google.es/search?q=powershell&start='+$pagina
Write-Host 'La URL:' $url
Write-Host '--------------------------------------------------------------------'
$result=Invoke-WebRequest $url
$array=@($result.AllElements | Where Class -eq “st”).innerText
foreach($palabra in $ficheropalabras)
{
for($i=0;$i -lt $array.Length;$i++)
{
if($array[$i] -cmatch $palabra){
Write-Host 'La palabra:' $palabra 'se ha encontrado posición: ' ($pagina+$i+1) `n'Texto: ' $array[$i]
}
}
Write-Host '--------------------------------------------------------------------'
}
Start-Sleep -Seconds 5
}

```
