# Agenda (versión avanzada 2)
## Graphics, PowerShell 
### URL: https://www.jesusninoc.com/2015/05/27/agenda-version-avanzada-2/
```PowerShell
#Para leer los datos que se van a almacenar en la "Agenda (versión avanzada 2)" hay que utilizar "Leer agenda (versión avanzada 2)"
#https://www.jesusninoc.com/2015/05/28/leer-agenda-version-avanzada-2/

Write-Host ‘————————————————————————————————————’
Write-Host ‘Agenda’
Write-Host ‘————————————————————————————————————’

do
{
Write-Host ‘————————————————————————————————————’
$nombre=Read-Host ‘Introduzca nombre’
$apellidos=Read-Host ‘Introduzca apellidos’
$dni=Read-Host ‘Introduzca DNI’
$edad=Read-Host ‘Introduzca edad’
$calle=Read-Host ‘Introduzca calle’
$nombre,$apellidos,$dni,$edad,$calle > $dni’.txt’

#Parte avanzada:

############################################################################################
#Buscar en Google a la persona y hacer una captura de pantalla de la foto
############################################################################################

#Buscar en Google la foto de la persona mediante su nombre y sus apellidos

$urlsp='https://www.google.es/search?hl=es&site=imghp&tbm=isch&source=hp&q='+$nombre+$apellidos
Start-Process chrome $urlsp

Start-Sleep -Seconds 10

#Realizar captura de pantalla de la persona
$path=’F:\power\agenda\’+$dni+’_fotopersona.bmp’
$Bitmap=New-Object System.Drawing.Bitmap([System.Windows.Forms.Screen]::PrimaryScreen.Bounds.Width, [System.Windows.Forms.Screen]::PrimaryScreen.Bounds.Height)
$Graphics=[System.Drawing.Graphics]::FromImage($Bitmap)
$Graphics.CopyFromScreen((New-Object System.Drawing.Point(0,0)), (New-Object System.Drawing.Point(0,0)), $Bitmap.Size)
$Graphics.Dispose()
$Bitmap.Save($path,’Bmp’)

############################################################################################
#Buscar en Google la calle y hacer una captura de pantalla de calle donde vive la persona
############################################################################################

#Buscar en Google la calle

#Utilizando The Google Geocoding API
#https://developers.google.com/maps/documentation/geocoding/

#$calle=’Avenida de Concha Espina 1′
$urlsi=’https://maps.googleapis.com/maps/api/geocode/json?address=’ + $calle + “+MADRID”
$urlsi=$urlsi.replace(” “,”+”)
$urlsi
$resulti=(Invoke-WebRequest -Uri $urlsi)
foreach($pit in $resulti.Content)
{
$conver=$pit | ConvertFrom-JSON
$lat=$conver.results.geometry.location.lat
$long=$conver.results.geometry.location.lng
$urlgooglemap=’https://www.google.es/maps?q=’+$lat+’,’+$long
Start-Process chrome $urlgooglemap
}
Start-Sleep -Seconds 10

#Realizar captura de pantalla de la calle
$path=’F:\power\agenda\’+$dni+’_calle.bmp’
$Bitmap=New-Object System.Drawing.Bitmap([System.Windows.Forms.Screen]::PrimaryScreen.Bounds.Width, [System.Windows.Forms.Screen]::PrimaryScreen.Bounds.Height)
$Graphics=[System.Drawing.Graphics]::FromImage($Bitmap)
$Graphics.CopyFromScreen((New-Object System.Drawing.Point(0,0)), (New-Object System.Drawing.Point(0,0)), $Bitmap.Size)
$Graphics.Dispose()
$Bitmap.Save($path,’Bmp’)

#Cerramos Google Chrome

Stop-Process chrome

############################################################################################

$control=Read-Host ‘¿Quiere continuar introduciendo datos (1 para sí y 0 para no)?’
}while($control -eq 1)

```
