# Almacenar y utilizar credenciales
## PowerShell, Security 
### URL: https://www.jesusninoc.com/2016/09/20/almacenar-y-utilizar-credenciales/
```PowerShell
Get-Credential | Export-Clixml -Path credenciales.xml
$cred=Import-Clixml -Path credenciales.xml
Start-Process notepad -Credential $cred

```
