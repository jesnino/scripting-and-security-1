# Ver en logs la dirección de la página web que creó el vínculo con el recurso
## Logs, Security, Servers, Web 
### URL: https://www.jesusninoc.com/2009/05/04/ver-en-logs-la-direccion-de-la-pagina-web-que-creo-el-vinculo-con-el-recurso/
```PowerShell
[cs(Referer)], COUNT(*) AS EXPR1
FROM tabla
WHERE (Date > '2009-05-01')
GROUP BY [cs(Referer)]
ORDER BY [cs(Referer)] DESC

```
