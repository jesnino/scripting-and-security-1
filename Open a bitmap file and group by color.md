# Open a bitmap file and group by color
## Graphics, PowerShell 
### URL: https://www.jesusninoc.com/2014/11/05/open-bitmap-file-group-color/
```PowerShell
$Group=""
$Cave = [System.Drawing.Bitmap]::FromFile('F:\power\script.bmp')
for ($x = 0;$x -lt $Cave.Height;$x+=1)
{
for ($y = 0;$y -lt $Cave.Width;$y+=1)
{
$Group=$Group+"|"+($Cave.GetPixel($y,$x).name).substring(2,6)
}
}
$Group.Split("|") | Group-Object | Sort-Object count -Descending

```
