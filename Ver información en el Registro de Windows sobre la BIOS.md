# Ver información en el Registro de Windows sobre la BIOS
## PowerShell, Registry 
### URL: https://www.jesusninoc.com/2015/03/25/ver-informacion-en-el-registro-de-windows-sobre-la-bios/
```PowerShell
Get-ItemProperty -Path ‘Registry::HKEY_LOCAL_MACHINE\HARDWARE\DESCRIPTION\System\BIOS'

```
