# Guardar la búsqueda de billetes de AVE
## Automation, PowerShell, Web scraping 
### URL: https://www.jesusninoc.com/2016/08/14/guardar-la-busqueda-de-billetes-de-ave/
```PowerShell
$MouseEventSig=@'
[DllImport("user32.dll",CharSet=CharSet.Auto, CallingConvention=CallingConvention.StdCall)]
public static extern void mouse_event(long dwFlags, long dx, long dy, long cButtons, long dwExtraInfo);
'@
$MouseEvent = Add-Type -memberDefinition $MouseEventSig -name "MouseEventWinApi" -passThru

Start-Process chrome "https://venta.renfe.com/vol/home.do"

Start-Sleep -Seconds 10
[System.Windows.Forms.Cursor]::Position = New-Object System.Drawing.Point(294,247)
$MouseEvent::mouse_event(0x00000002, 0, 0, 0, 0)
$MouseEvent::mouse_event(0x00000004, 0, 0, 0, 0)
Start-Sleep -Seconds 10
[System.Windows.Forms.SendKeys]::SendWait('MADRID')
Start-Sleep -Seconds 5
[System.Windows.Forms.SendKeys]::SendWait('{TAB}')
Start-Sleep -Seconds 10
[System.Windows.Forms.SendKeys]::SendWait('BARCELONA')
Start-Sleep -Seconds 5
[System.Windows.Forms.SendKeys]::SendWait('{TAB}')
Start-Sleep -Seconds 10
[System.Windows.Forms.SendKeys]::SendWait('25/11/2016')
Start-Sleep -Seconds 5
[System.Windows.Forms.SendKeys]::SendWait('{ENTER}')
Start-Sleep -Seconds 10
[System.Windows.Forms.Cursor]::Position = New-Object System.Drawing.Point(343,671)
$MouseEvent::mouse_event(0x00000002, 0, 0, 0, 0)
$MouseEvent::mouse_event(0x00000004, 0, 0, 0, 0)
Start-Sleep -Seconds 10
#Si falla la petición pulsar en el botón "RECARGAR"
[System.Windows.Forms.Cursor]::Position = New-Object System.Drawing.Point(666,497)
$MouseEvent::mouse_event(0x00000002, 0, 0, 0, 0)
$MouseEvent::mouse_event(0x00000004, 0, 0, 0, 0)


#Guardar resultado de la búsqueda para un día en concreto
Start-Sleep -Seconds 5
$_
[System.Windows.Forms.SendKeys]::SendWait('^{s}')
Start-Sleep -Seconds 5
$tiempo=(Get-Date).tostring("dd-MM-yyyy-hh-mm-ss")
Start-Sleep -Seconds 5
[System.Windows.Forms.SendKeys]::SendWait("d:\ave\"+$tiempo)
Start-Sleep -Seconds 5
[System.Windows.Forms.SendKeys]::SendWait('{ENTER}')
Start-Sleep -Seconds 20
[System.Windows.Forms.SendKeys]::SendWait('{END}')

```
