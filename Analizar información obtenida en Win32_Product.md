# Analizar información obtenida en Win32_Product
## PowerShell, Software 
### URL: https://www.jesusninoc.com/2015/01/24/analizar-informacion-obtenida-en-win32_product/
```PowerShell
((Get-WmiObject -Class Win32_Product).name) | % {$_.split(' ')[0]} | Group-Object

```
```PowerShell
(Get-WmiObject -Class Win32_Product).count

```
```PowerShell
$name='Google'
$producto=(Get-WmiObject -Class Win32_Product)
foreach($uno in $producto)
{
if($uno.name -match $name)
{
$valor=$uno.IdentifyingNumber
$valor=$valor.replace('{','')
$valor=$valor.replace('}','')
}
}
Get-ChildItem hklm:\ -rec -ea SilentlyContinue | % {
if($_ -match $valor){$_}
}

```
