# Añadir permiso NTFS a una carpeta
## Filesystem, Permissions, PowerShell 
### URL: https://www.jesusninoc.com/2015/08/19/anadir-permiso-ntfs-a-una-carpeta/
```PowerShell
$ruta = 'F:\power\carpeta'

New-Item -Path $ruta -ItemType Directory

$permisos = Get-Acl -Path $ruta

#Crear regla de acceso
#System.Security.AccessControl.FileSystemAccessRule: Representa una abstracción de una entrada de control de acceso (ACE) que define una regla de acceso para un archivo o directorio
$permisoadd = 'Todos', 'FullControl', 'ContainerInherit, ObjectInherit', 'None', 'Allow'
$regla = New-Object -TypeName System.Security.AccessControl.FileSystemAccessRule -ArgumentList $permisoadd
$permisos.SetAccessRule($regla)

#Añadir permisos a la carpeta
$permisos | Set-Acl -Path $ruta

#Comprobar permisos
$permisos.Access

```
