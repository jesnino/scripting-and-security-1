# Almacenar en un fichero las posiciones del ratón
## Automation, PowerShell 
### URL: https://www.jesusninoc.com/2016/01/30/almacenar-en-un-fichero-las-posiciones-del-raton/
```PowerShell
while(1)
{
[string]::Concat(([System.Windows.Forms.Cursor]::Position).X.ToString(),'|',([System.Windows.Forms.Cursor]::Position).Y.ToString()) | Out-File D:\power\posicionesraton.txt
Start-Sleep -Seconds 1
}
notepad D:\power\posicionesraton.txt

```
