# How to draw the letter Y
## Graphics, PowerShell 
### URL: https://www.jesusninoc.com/2013/02/25/draw-letter-y/
```PowerShell
#Create pen
$mypen = new-object Drawing.Pen red
$mypen.width = 10

$form = New-Object Windows.Forms.Form
$form.Width = 500
$form.Height = 550
$formGraphics = $form.createGraphics()

#Y
$form.add_paint({$formGraphics.DrawLine($mypen, 0, 0, 100, 100)})
$form.add_paint({$formGraphics.DrawLine($mypen, 200, 0, 0, 200)})

$form.ShowDialog()

```
