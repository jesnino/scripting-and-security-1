# Drawing a line
## Graphics, PowerShell 
### URL: https://www.jesusninoc.com/2013/01/26/drawing-a-line/
```PowerShell
[void] [System.Reflection.Assembly]::LoadWithPartialName("System.Drawing")
[void] [System.Reflection.Assembly]::LoadWithPartialName("System.Windows.Forms")

$mypen = new-object Drawing.Pen red
$mypen.width = 10
$form = New-Object Windows.Forms.Form
$formGraphics = $form.createGraphics()
$form.add_paint({$formGraphics.DrawLine($mypen, 10, 10, 200, 200)})
$form.ShowDialog()

```
