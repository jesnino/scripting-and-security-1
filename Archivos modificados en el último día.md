# Archivos modificados en el último día
## Filesystem, PowerShell 
### URL: https://www.jesusninoc.com/2015/02/01/archivos-modificados-en-el-ultimo-dia/
```PowerShell
Get-ChildItem | Where-Object {
$_.LastWriteTime -ge (Get-Date).AddDays(-1)
}

```
