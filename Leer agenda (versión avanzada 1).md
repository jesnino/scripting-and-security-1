# Leer agenda (versión avanzada 1)
## PowerShell 
### URL: https://www.jesusninoc.com/2015/04/28/leer-agenda-version-avanzada-1/
```PowerShell
#De los datos guardados por "Agenda (versión avanzada 1)"
#https://www.jesusninoc.com/2015/04/27/agenda-version-avanzada-1/

#Mostrar los datos de cada usuario por su DNI utilizando el cmdlet Get-ChildItem, también mostrar la imagen de la calle en donde vive el usuario

#Pedir el DNI al usuario
$dni=Read-Host 'Introduzca DNI: '

#Buscar el fichero cuyo nombre el el DNI junto con la extensión .txt
$fichero=Get-ChildItem $dni'.txt'

#Obtener el contenido del fichero
$contenido=Get-Content $fichero.Name

#Abrir la imagen de la calle en donde vive el usuario
Start-Process C:\WINDOWS\system32\mspaint.exe $dni'.bmp'

#Imprimir el contenido por pantalla
$contenido

```
