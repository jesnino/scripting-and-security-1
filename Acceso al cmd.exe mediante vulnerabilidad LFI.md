# Acceso al cmd.exe mediante vulnerabilidad LFI
## Logs, Security, Servers 
### URL: https://www.jesusninoc.com/2009/04/30/acceso-al-cmd-exe-mediante-vulnerabilidad-lfi/
```PowerShell
/scripts/..??../winnt/system32/cmd.exe
/msadc/..??../..??../..??../winnt/system32/cmd.exe
/_vti_bin/..??../..??../..??../winnt/system32/cmd.exe

```
```PowerShell
SELECT     [cs-uri-stem], COUNT(*) AS EXPR1
FROM         tabla
where  [cs-uri-stem] like '%?%'
GROUP BY [cs-uri-stem]
ORDER BY 2 desc

```
