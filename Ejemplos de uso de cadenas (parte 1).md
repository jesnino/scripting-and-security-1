# Ejemplos de uso de cadenas (parte 1)
## PowerShell, Strings 
### URL: https://www.jesusninoc.com/2014/09/28/ejemplos-de-uso-de-cadenas-parte-1/
```PowerShell
$palabra1='hola-'
$palabra2='adios'
$frasecontatenada=$palabra1+$palabra2
$frasecontatenada

```
```PowerShell
$frase='Texto largo'

#Extraer primer elemento (elemento 0)
$frase[0]

#Extraer segundo elemento (elemento 1)
$frase[1]

#Extraer último elemento
$frase[10]

```
```PowerShell
$frase='Texto largo'
$frase.Length

```
```PowerShell
$frase='Texto*muy*largo'
$frase.Split("*")

```
```PowerShell
$frase=' Texto muy largo '
$frase.Trim()

```
