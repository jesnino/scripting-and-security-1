# Almacenar el número de resultados de una búsqueda en Google
## PowerShell 
### URL: https://www.jesusninoc.com/2016/04/22/almacenar-el-numero-de-resultados-de-una-busqueda-en-google/
```PowerShell
"--------------------------------------------------------------------------------" | Out-File D:\resultado.txt -Append
Get-Date | Out-File D:\resultado.txt -Append
"--------------------------------------------------------------------------------" | Out-File D:\resultado.txt -Append
$concepto='PowerShell'
#Búsqueda normal
$consulta='https://www.google.es/search?q='+$concepto;$consulta
((((Invoke-WebRequest $consulta).AllElements).where{$_.class -eq 'sd'})).outerText  | Out-File D:\resultado.txt -Append
#Búsqueda normal en mayúsculas
$consulta='https://www.google.es/search?q='+$concepto.ToUpper();$consulta
((((Invoke-WebRequest $consulta).AllElements).where{$_.class -eq 'sd'})).outerText | Out-File D:\resultado.txt -Append
#Búsqueda normal en minúsculas
$consulta='https://www.google.es/search?q='+$concepto.ToLower();$consulta
((((Invoke-WebRequest $consulta).AllElements).where{$_.class -eq 'sd'})).outerText | Out-File D:\resultado.txt -Append
#Búsqueda con el concepto entre comillas
$consulta='https://www.google.es/search?q="'+$concepto+'"';$consulta
((((Invoke-WebRequest $consulta).AllElements).where{$_.class -eq 'sd'})).outerText | Out-File D:\resultado.txt -Append
#Búsqueda con el concepto en mayúsculas y entre comillas
$consulta='https://www.google.es/search?q="'+$concepto.ToUpper()+'"';$consulta
((((Invoke-WebRequest $consulta).AllElements).where{$_.class -eq 'sd'})).outerText | Out-File D:\resultado.txt -Append
#Búsqueda con el concepto en minúsculas y entre comillas
$consulta='https://www.google.es/search?q="'+$concepto.ToLower()+'"';$consulta
((((Invoke-WebRequest $consulta).AllElements).where{$_.class -eq 'sd'})).outerText | Out-File D:\resultado.txt -Append

```
