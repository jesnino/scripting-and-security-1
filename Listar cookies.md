# Listar cookies
## Forensic analysis, PowerShell 
### URL: https://www.jesusninoc.com/2016/04/30/listar-cookies/
```PowerShell
Get-ChildItem ([Environment]::GetFolderPath("Cookies"))

```
