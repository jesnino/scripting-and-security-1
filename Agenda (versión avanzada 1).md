# Agenda (versión avanzada 1)
## Graphics, PowerShell 
### URL: https://www.jesusninoc.com/2015/04/27/agenda-version-avanzada-1/
```PowerShell
#Para leer los datos que se van a almacenar en la "Agenda (versión avanzada 1)" hay que utilizar "Leer agenda (versión avanzada 1)"
#<a href="https://www.jesusninoc.com/2015/04/28/leer-agenda-version-avanzada-1/" target="_blank">https://www.jesusninoc.com/2015/04/28/leer-agenda-version-avanzada-1/</a>

Write-Host '————————————————————————————————————'
Write-Host 'Agenda'
Write-Host '————————————————————————————————————'

do
{
Write-Host '————————————————————————————————————'
$nombre=Read-Host 'Introduzca nombre'
$apellidos=Read-Host 'Introduzca apellidos'
$dni=Read-Host 'Introduzca DNI'
$edad=Read-Host 'Introduzca edad'
$calle=Read-Host 'Introduzca calle'
$nombre,$apellidos,$dni,$edad,$calle > $dni'.txt'

#Parte avanzada:

############################################################################################
#Buscar en Google la calle y hacer una captura de pantalla de calle donde vive la persona
############################################################################################

#Buscar en Google la calle

#Utilizando The Google Geocoding API
#https://developers.google.com/maps/documentation/geocoding/

#$calle='Avenida de Concha Espina 1'
$urlsi='https://maps.googleapis.com/maps/api/geocode/json?address=' + $calle + “+MADRID”
$urlsi=$urlsi.replace(” “,”+”)
$urlsi
$resulti=(Invoke-WebRequest -Uri $urlsi)
foreach($pit in $resulti.Content)
{
$conver=$pit | ConvertFrom-JSON
$lat=$conver.results.geometry.location.lat
$long=$conver.results.geometry.location.lng
$urlgooglemap='https://www.google.es/maps?q='+$lat+','+$long
Start-Process chrome $urlgooglemap
}
Start-Sleep -Seconds 10

#Realizar captura de pantalla de la calle
$path=’F:\power\agenda\'+$dni+'.bmp'
$Bitmap=New-Object System.Drawing.Bitmap([System.Windows.Forms.Screen]::PrimaryScreen.Bounds.Width, [System.Windows.Forms.Screen]::PrimaryScreen.Bounds.Height)
$Graphics=[System.Drawing.Graphics]::FromImage($Bitmap)
$Graphics.CopyFromScreen((New-Object System.Drawing.Point(0,0)), (New-Object System.Drawing.Point(0,0)), $Bitmap.Size)
$Graphics.Dispose()
$Bitmap.Save($path,’Bmp’)

#Cerramos Google Chrome

Stop-Process chrome

############################################################################################

$control=Read-Host '¿Quiere continuar introduciendo datos (1 para sí y 0 para no)?'
}while($control -eq 1)

```
