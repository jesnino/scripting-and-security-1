# Devolver el contenido de una variable de entorno del sistema operativo
## PowerShell, Visual Basic 
### URL: https://www.jesusninoc.com/2016/04/12/devolver-el-contenido-de-una-variable-de-entorno-del-sistema-operativo/
```PowerShell
#https://msdn.microsoft.com/es-es/library/b2d05613(v=vs.110).aspx

Add-Type -AssemblyName Microsoft.VisualBasic

[Microsoft.VisualBasic.Interaction]::Environ("windir")

```
