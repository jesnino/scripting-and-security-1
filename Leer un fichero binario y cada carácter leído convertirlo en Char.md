# Leer un fichero binario y cada carácter leído convertirlo en Char
## Filesystem, PowerShell 
### URL: https://www.jesusninoc.com/2015/02/10/leer-un-fichero-binario-y-cada-caracter-leido-convertirlo-en-char/
```PowerShell
$bytes = [System.IO.File]::ReadAllBytes('F:\power\dibujos\1.bmp')

foreach($off in $bytes)
{
$choff=[Char[]]$off
Write-Host $off, $choff
}

```
