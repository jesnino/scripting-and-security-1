# Drawing number three
## Graphics 
### URL: https://www.jesusninoc.com/2014/04/04/drawing-number-three/
```PowerShell
#Number three

#Create pen
$mypen = new-object Drawing.Pen red
$mypen.width = 10

$form = New-Object Windows.Forms.Form
$formGraphics = $form.createGraphics()

#Drawing parallel lines
#10, 10, 200, 10
#-------------------------------
#10, 100, 200, 100
#-------------------------------
#10, 200, 200, 200
#-------------------------------

#Drawing perpendicular line
#200, 10, 200, 200
# |
# |
# |
# |
# |
# |
# |
# |

#Create coordinates of points that define lines
#Draw lines to screen (perpendicular and parallel)

#Drawing parallel lines
$form.add_paint({$formGraphics.DrawLine($mypen, 10, 10, 200, 10)})
$form.add_paint({$formGraphics.DrawLine($mypen, 10, 100, 200, 100)})
$form.add_paint({$formGraphics.DrawLine($mypen, 10, 200, 200, 200)})

#Drawing perpendicular line
$form.add_paint({$formGraphics.DrawLine($mypen, 200, 10, 200, 200)})

$form.ShowDialog()

```
