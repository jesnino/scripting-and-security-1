# Leer agenda (primera versión)
## PowerShell 
### URL: https://www.jesusninoc.com/2014/04/28/leer-agenda-primera-version/
```PowerShell
#De los datos guardados por "Agenda (primera versión)"
#https://www.jesusninoc.com/2014/04/27/agenda-primera-version/

#Mostrar los datos de cada usuario por su DNI utilizando el cmdlet Get-ChildItem

#Pedir el DNI al usuario
$dni=Read-Host "Introduzca DNI: "

#Buscar el fichero cuyo nombre el el DNI junto con la extensión .txt
$fichero=Get-ChildItem $dni".txt"

#Obtener el contenido del fichero
$contenido=Get-Content $fichero.Name

#Imprimir el contenido por pantalla
$contenido

```
