# Poner una palabra en color si aparece dentro de una frase
## PowerShell, Strings 
### URL: https://www.jesusninoc.com/2015/07/20/poner-una-palabra-en-color-si-aparece-dentro-de-una-frase/
```PowerShell
$procesar='En cierto lugar de mi casa'
$palabras='lugar','casa'

$procesar.Split(' ') | % {
if($_ | Select-String $palabras.Split(','))
{
Write-Host $_ ' ' -BackgroundColor Cyan -ForegroundColor Blue -NoNewline
}
else
{
Write-Host $_ ' ' -NoNewline
}
}

```
