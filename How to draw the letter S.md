# How to draw the letter S
## Graphics, PowerShell 
### URL: https://www.jesusninoc.com/2013/02/22/draw-letter-s/
```PowerShell
#Create pen
$mypen = new-object Drawing.Pen red
$mypen.width = 10

$form = New-Object Windows.Forms.Form
$form.Width = 500
$form.Height = 550
$formGraphics = $form.createGraphics()

#S
$form.add_paint({$formGraphics.DrawLine($mypen, 0, 0, 200, 0)})
$form.add_paint({$formGraphics.DrawLine($mypen, 0, 100, 200, 100)})
$form.add_paint({$formGraphics.DrawLine($mypen, 0, 200, 200, 200)})

$form.add_paint({$formGraphics.DrawLine($mypen, 0, 0, 0, 100)})
$form.add_paint({$formGraphics.DrawLine($mypen, 200, 100, 200, 200)})

$form.ShowDialog()

```
