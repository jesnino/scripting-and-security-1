# Convert bitmap to characters in Write-Host (simple version)
## Graphics, PowerShell 
### URL: https://www.jesusninoc.com/2015/01/05/convert-bitmap-characters-write-host-simple-version/
```PowerShell
$foto1 = [System.Drawing.Bitmap]::FromFile(‘F:\power\foto1.bmp’)

for($y=0;$y -lt $foto1.Height;$y+=1)
{
for($x=0;$x -lt $foto1.Width;$x+=1)
{
switch ($foto1.GetPixel($x,$y).name){
'fffdfdfd'{Write-Host ‘ ‘ -BackgroundColor Black -ForegroundColor White -NoNewLine}
default{Write-Host ‘ ‘ -BackgroundColor White -ForegroundColor Black -NoNewLine}
}
}
Write-Host ” ”
}

```
