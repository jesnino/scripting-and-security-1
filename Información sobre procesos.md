# Información sobre procesos
## PowerShell, Processes 
### URL: https://www.jesusninoc.com/2015/11/28/informacion-sobre-procesos/
```PowerShell
#Obtener información básica sobre procesos
Get-Process
gps
ps

#Obtener información ampliada sobre procesos
Get-Process | Select-Object *
gps | Select-Object *
ps | Select-Object *

#Obtener información sobre las propiedades de los procesos
Get-Process | Select-Object Name, Id, Company
gps | Select-Object Name, Id, Company
ps | Select-Object Name, Id, Company

#Obtener información ordenada sobre las propiedades de los procesos
Get-Process | Select-Object Name, Id, Company | Sort-Object Name
gps | Select-Object Name, Id, Company | Sort-Object Name
ps | Select-Object Name, Id, Company | Sort-Object Name

#Obtener los 5 primeros procesos ordenados
Get-Process | Select-Object Name, Id, Company | Sort-Object Name | Select-Object -First 5
gps | Select-Object Name, Id, Company | Sort-Object Name | Select-Object -First 5
ps | Select-Object Name, Id, Company | Sort-Object Name | Select-Object -First 5

```
