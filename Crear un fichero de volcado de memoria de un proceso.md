# Crear un fichero de volcado de memoria de un proceso
## Forensic analysis, PowerShell, Processes, Security 
### URL: https://www.jesusninoc.com/2016/03/04/crear-un-fichero-de-volcado-de-memoria-de-un-proceso/
```PowerShell
$Proceso=Get-Process -Name notepad
$NombreF='d:\dump\'+(($Proceso).name)+'.dmp'
$Fichero = New-Object IO.FileStream($NombreF,[IO.FileMode]::Create)
(([PSObject].Assembly.GetType('System.Management.Automation.WindowsErrorReporting')).GetNestedType('NativeMethods', 'NonPublic')).GetMethod('MiniDumpWriteDump',[Reflection.BindingFlags] 'NonPublic, Static').Invoke($null, @($Proceso.Handle,$Proceso.Id,$Fichero.SafeFileHandle,[UInt32] 2,[IntPtr]::Zero,[IntPtr]::Zero,[IntPtr]::Zero))
$Fichero.Close()

```
