# Obtener la resolución de pantalla
## Graphics, PowerShell 
### URL: https://www.jesusninoc.com/2015/11/04/obtener-la-resolucion-de-pantalla/
```PowerShell
[System.Windows.Forms.Screen]::AllScreens.bounds | Select-Object Width,Height

```
