# Introducción (ejemplos clase 1)
## PowerShell 
### URL: https://www.jesusninoc.com/2014/03/21/introduccion-ejemplos-clase-1/
```PowerShell
##Introducción (ejemplos clase 1)

#Variables
 #Operaciones aritméticas
 #Almacenar y abrir ficheros
 #Partir cadenas
 #Listar ficheros y directorios
 #Sentencias de repetición

##Ejemplo 1
$a=1
$a

##Ejemplo 2
$a=1
$a
$letra='a'
$letra
$frase='hola'
$frase

##Ejemplo 3
$ipcon=ipconfig
$ipcon

##Ejemplo 4
$listado=ls
foreach($fichero in $listado)
{
$fichero
}

##Ejemplo 5
#Crear carpetas
#fichero1, fichero2, fichero3, fichero4
$listado=gc q:\power\ficheroscrear.txt
foreach($fichero in $listado)
{
mkdir $fichero
}

##Ejemplo 6
$listado='1','2','3','4'
foreach($numero in $listado)
{
$numero
}

##Ejemplo 7
$numero=7
$operacion=$numero%2
$operacion

##Ejemplo 8
$numero=7
$operacion=$numero%2
if($operacion -eq 0)
{
"par"
}
else
{
"impar"
}

##Ejemplo 9
$listado='1','2','3','4'
foreach($numero in $listado)
{
$operacion=$numero%2
if($operacion -eq 0)
{
"par"
}
else
{
"impar"
}
}

##Ejemplo 10
$listado=ls C:\power
foreach($numero in $listado)
{
$operacion=$numero.name.Split(".")[0]%2
if($operacion -eq 0)
{
"par"
}
else
{
"impar"
}
}

##Ejemplo 10.1
$listado=ls C:\power
foreach($numero in $listado)
{
$numero
}

##Ejemplo 10.2
$listado=ls C:\power
foreach($numero in $listado)
{
$operacion=$numero.name
$operacion
}

##Ejemplo 10.3
$listado=ls C:\power
foreach($numero in $listado)
{
$numero
$operacion=$numero.name.Split(".")[0]%2
$operacion
}

##Ejemplo 11
$listado=ls C:\power
foreach($numero in $listado)
{
$operacion=$numero.name.Split(".")[0]%2
if($operacion -eq 0)
{
"par"
}
else
{
"impar"
}
}

```
