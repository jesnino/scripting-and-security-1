# Crear un usuario con contraseña leyendo los datos de un fichero
## PowerShell, Users 
### URL: https://www.jesusninoc.com/2016/08/26/crear-un-usuario-con-contrasena-leyendo-los-datos-de-un-fichero/
```PowerShell
#Es necesario ejecutar PowerShell en modo administrador
#Nombre del equipo
$ComputerName = $env:COMPUTERNAME
$computer = [ADSI]"WinNT://$($ComputerName),computer"

#Fichero con usuarios y contraseñas
#usuario,pass123@aAB1
gc D:\usuarios.txt | % {
$datos=$_.split(',')
#Nombre de usuario
$user = $computer.Create('User', "$($datos[0])")
#Password para usuario
$user.SetPassword($datos[1])
$user.SetInfo()
}

```
