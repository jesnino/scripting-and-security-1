# Open a bitmap file and display pixel color
## Graphics, PowerShell 
### URL: https://www.jesusninoc.com/2014/11/05/open-bitmap-file-display-pixel-color/
```PowerShell
$Cave = [System.Drawing.Bitmap]::FromFile('F:\power\script.bmp')
for ($x = 0;$x -lt $Cave.Height;$x+=1)
{
for ($y = 0;$y -lt $Cave.Width;$y+=1)
{
Write-Host "X="$x "Y="$y ($Cave.GetPixel($y,$x).name).substring(2,6)
}
}

```
