# Ordenar en distinto orden propiedades de objetos
## PowerShell 
### URL: https://www.jesusninoc.com/2016/07/14/ordenar-en-distinto-orden-propiedades-de-objetos/
```PowerShell
#Ordenar procesos por nombre descendente y uso de CPU ascendente
Get-Process |  Sort-Object -Property @{E='Name'; A=$False},@{E='CPU';A=$True}

```
