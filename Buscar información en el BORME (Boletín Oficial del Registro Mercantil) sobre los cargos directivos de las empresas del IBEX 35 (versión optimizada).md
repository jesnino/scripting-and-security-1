# Buscar información en el BORME (Boletín Oficial del Registro Mercantil) sobre los cargos directivos de las empresas del IBEX 35 (versión optimizada)
## PowerShell, Web scraping 
### URL: https://www.jesusninoc.com/2016/02/26/buscar-informacion-en-el-borme-boletin-oficial-del-registro-mercantil-sobre-los-cargos-directivos-de-las-empresas-del-ibex-35-version-optimizada/
```PowerShell
foreach($empresa in @(((Invoke-WebRequest 'http://www.bolsamadrid.es/esp/aspx/Mercados/Precios.aspx?indice=ESI100000000').AllElements).where{$_.Class -eq "DifFlBj"}).innerText)
{
foreach($directivo in @(((Invoke-WebRequest "http://www.empresia.es/empresa/$empresa").AllElements).where{$_.id -eq "ListaRelaciones"}).innerText -split '[\r\n]')
{
#$directivo.Split('.')[0]
@(((Invoke-WebRequest "https://www.google.es/search?q=inurl:boe.es+$directivo").AllElements).where{$_.Class -eq "st"}).innerText
Start-Sleep -Seconds 5
}
Start-Sleep -Seconds 10
}

```
