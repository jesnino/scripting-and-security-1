# Introducción a los cmdlets (comandos)
## PowerShell 
### URL: https://www.jesusninoc.com/2015/10/16/introduccion-a-los-cmdlets-comandos/
```PowerShell
Verbo-Nombre -parametro1 argumento1 -parametro2 argumento2

```
```PowerShell
Tecla TAB

```
```PowerShell
Escribir Get-Process - y presionar la tecla TAB

```
```PowerShell
Get-History

```
```PowerShell
Get-History

```
```PowerShell
Get-Help

```
```PowerShell
Get-Help Get-History

```
```PowerShell
Get-Command

```
```PowerShell
Get-Command

```
```PowerShell
Get-Alias

```
```PowerShell
ps

```
```PowerShell
Get-ChildItem

```
```PowerShell
Get-ChildItem D:\ -Recurse

```
```PowerShell
|

```
```PowerShell
Get-Process | Sort-Object Name

```
```PowerShell
<,>,>>

```
```PowerShell
Get-Process > D:\power\procesos.txt

```
```PowerShell
Get-Date > D:\power\procesos.txt
Get-Process >> D:\power\procesos.txt

```
```PowerShell
Sort-Object

```
```PowerShell
Get-Process | Sort-Object ProcessName

```
```PowerShell
Where-Object

```
```PowerShell
Get-Process | Where-Object CPU -GT 10

```
