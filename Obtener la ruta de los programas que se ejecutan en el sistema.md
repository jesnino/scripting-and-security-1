# Obtener la ruta de los programas que se ejecutan en el sistema
## PowerShell, Processes 
### URL: https://www.jesusninoc.com/2015/02/13/obtener-la-ruta-de-los-programas-que-se-ejecutan-en-el-sistema/
```PowerShell
Get-WmiObject win32_process -co . | Select-Object Description,Path

```
