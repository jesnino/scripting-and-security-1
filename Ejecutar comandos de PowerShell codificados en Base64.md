# Ejecutar comandos de PowerShell codificados en Base64
## PowerShell 
### URL: https://www.jesusninoc.com/2015/10/09/ejecutar-comandos-de-powershell-codificados-en-base64/
```PowerShell
$codigo = {Get-NetAdapter; Start-Sleep -Seconds 5}
$bytes = [System.Text.Encoding]::Unicode.GetBytes($codigo.ToString())
$codificado = [Convert]::ToBase64String($bytes)

$argumentos = '-encodedcommand ' + $codificado

Start-Process -FilePath powershell.exe -ArgumentList $argumentos

```
