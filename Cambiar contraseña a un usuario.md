# Cambiar contraseña a un usuario
## PowerShell, Users 
### URL: https://www.jesusninoc.com/2016/07/19/cambiar-contrasena-a-un-usuario/
```PowerShell
$usuario = [ADSI]"WinNT://$env:COMPUTERNAME/usuario,User" 
$usuario.description ='Contraseña cambiada al usuario'
$usuario.SetPassword('pass123@aAB1234')
$usuario.SetInfo()

```
