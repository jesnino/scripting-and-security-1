# How to draw the letter H
## Graphics, PowerShell 
### URL: https://www.jesusninoc.com/2013/02/12/draw-letter-h/
```PowerShell
#Create pen
$mypen = new-object Drawing.Pen red
$mypen.width = 10

$form = New-Object Windows.Forms.Form
$form.Width = 500
$form.Height = 550
$formGraphics = $form.createGraphics()

#H
$form.add_paint({$formGraphics.DrawLine($mypen, 0, 100, 200, 100)})

$form.add_paint({$formGraphics.DrawLine($mypen, 0, 0, 0, 200)})
$form.add_paint({$formGraphics.DrawLine($mypen, 200, 0, 200, 200)})

$form.ShowDialog()

```
