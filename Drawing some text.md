# Drawing some text
## Graphics, PowerShell 
### URL: https://www.jesusninoc.com/2013/01/28/drawing-some-text/
```PowerShell
Add-Type -AssemblyName System.Drawing

$file = "example2.png"

$png = new-object System.Drawing.Bitmap 200,50
$font = new-object System.Drawing.Font Arial,30

$colorl = [System.Drawing.Brushes]::White
$graphics = [System.Drawing.Graphics]::FromImage($png)

$graphics.DrawString("Hello",$font,$colorl,5,5)
$graphics.Dispose()
$png.Save($file)

```
