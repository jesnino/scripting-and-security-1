# Crear un usuario con contraseña
## PowerShell, Users 
### URL: https://www.jesusninoc.com/2016/06/21/crear-un-usuario-con-contrasena/
```PowerShell
#Nombre del equipo
$ComputerName = $env:COMPUTERNAME
$computer = [ADSI]"WinNT://$($ComputerName),computer"

#Nombre de usuario
$Name = 'usuario'
$user = $computer.Create('User', "$($Name)")

#Password para usuario
$password = 'pass123@aAB1'
$user.SetPassword($password)
$user.SetInfo()

```
