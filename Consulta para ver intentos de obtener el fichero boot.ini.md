# Consulta para ver intentos de obtener el fichero boot.ini
## Logs, Security, Servers 
### URL: https://www.jesusninoc.com/2009/05/08/consulta-para-ver-intentos-de-obtener-el-fichero-boot-ini/
```PowerShell
/????/????/????/boot.ini

```
```PowerShell
SELECT     [cs-uri-stem], [cs-uri-query]
FROM         tabla
where  [cs-uri-stem] like '%?%'
ORDER BY 1 desc

```
