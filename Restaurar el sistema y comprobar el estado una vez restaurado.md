# Restaurar el sistema y comprobar el estado una vez restaurado
## PowerShell 
### URL: https://www.jesusninoc.com/2015/08/16/restaurar-el-sistema-y-comprobar-el-estado-una-vez-restaurado/
```PowerShell
Get-ComputerRestorePoint
Restore-Computer -RestorePoint 255
Get-ComputerRestorePoint -LastStatus

```
