# Drawing number seven
## Graphics 
### URL: https://www.jesusninoc.com/2014/04/07/drawing-number-seven/
```PowerShell
#Number seven

#Create pen
$mypen = new-object Drawing.Pen red
$mypen.width = 10

$form = New-Object Windows.Forms.Form
$formGraphics = $form.createGraphics()

#Drawing parallel lines
#10, 10, 200, 10
#——————————-
#10, 100, 200, 100
#——————————-

#Drawing perpendicular line
#|
#|
#|
#|
#|
#|
#|
#|
#200, 10, 200, 200

#Create coordinates of points that define lines
#Draw lines to screen (perpendicular and parallel)

#Drawing parallel lines
$form.add_paint({$formGraphics.DrawLine($mypen, 10, 10, 200, 10)})
$form.add_paint({$formGraphics.DrawLine($mypen, 10, 100, 200, 100)})

#Drawing perpendicular lines
$form.add_paint({$formGraphics.DrawLine($mypen, 200, 10, 200, 200)})

$form.ShowDialog()

```
