# Automatizar el inicio de sesión en un gestor de contenido WordPress de forma gráfica utilizando PowerShell
## Automation, PHP, PowerShell 
### URL: https://www.jesusninoc.com/2015/08/09/automatizar-el-inicio-de-sesion-en-un-gestor-de-contenido-wordpress-de-forma-grafica-utilizando-powershell/
```PowerShell
#Importar DLL para simular el clic del ratón
#Es necesario poner las comillas correctamente cuando se importa la DLL user32.dll

$MouseEventSig=@’
[DllImport("user32.dll",CharSet=CharSet.Auto, CallingConvention=CallingConvention.StdCall)]
public static extern void mouse_event(long dwFlags, long dx, long dy, long cButtons, long dwExtraInfo);
‘@
$MouseEvent = Add-Type -memberDefinition $MouseEventSig -name “MouseEventWinApi” -passThru

Start-Process chrome https://www.jesusninoc.com/wp-login.php

#Esperar a cargar correctamente la página
Start-Sleep -Seconds 10

#Situar el ratón en la caja de texto “Username”
[System.Windows.Forms.Cursor]::Position=New-Object System.Drawing.Point(580,349)
$MouseEvent::mouse_event(0x00000002, 0, 0, 0, 0)
$MouseEvent::mouse_event(0x00000004, 0, 0, 0, 0)
[System.Windows.Forms.SendKeys]::SendWait(‘username’)

#Situar el ratón en la caja de texto “Password”
[System.Windows.Forms.Cursor]::Position=New-Object System.Drawing.Point(580,425)
$MouseEvent::mouse_event(0x00000002, 0, 0, 0, 0)
$MouseEvent::mouse_event(0x00000004, 0, 0, 0, 0)
[System.Windows.Forms.SendKeys]::SendWait(‘contracontra’)

#Pulsar la tecla ENTER
[System.Windows.Forms.SendKeys]::SendWait(‘{ENTER}’)

```
