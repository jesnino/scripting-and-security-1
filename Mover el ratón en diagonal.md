# Mover el ratón en diagonal
## Automation, Graphics, PowerShell 
### URL: https://www.jesusninoc.com/2015/01/30/mover-el-raton-en-diagonal/
```PowerShell
for($i=0;$i -ne 500; $i+=1){
[System.Windows.Forms.Cursor]::Position = New-Object System.Drawing.Point($i,$i)
Start-Sleep -Milliseconds 5
}

```
