# Realizar captura de pantalla y guardar con formato de imagen de mapa de bits (BMP)
## Graphics, PowerShell 
### URL: https://www.jesusninoc.com/2015/06/01/realizar-captura-de-pantalla-y-guardar-con-formato-de-imagen-de-mapa-de-bits-bmp/
```PowerShell
$path=’F:\power\bitmap\prueba.bmp’
$b=New-Object System.Drawing.Bitmap([System.Windows.Forms.Screen]::PrimaryScreen.Bounds.Width, [System.Windows.Forms.Screen]::PrimaryScreen.Bounds.Height)
$g=[System.Drawing.Graphics]::FromImage($b)
$g.CopyFromScreen((New-Object System.Drawing.Point(0,0)), (New-Object System.Drawing.Point(0,0)), $b.Size)
$g.Dispose()
$b.Save($path,'Bmp')

```
