# Ejemplos de ejecución de comandos en Bash y PowerShell (parte 1)
## Bash, Filesystem, PowerShell 
### URL: https://www.jesusninoc.com/2008/09/29/ejemplos-de-ejecucion-de-comandos-en-bash-y-powershell-parte-1/
```Shell
echo "Hola"

```
```PowerShell
Write-Output "Hola"

echo "Hola"

```
```Shell
echo "directorio1" > directorios

```
```PowerShell
Write-Output "directorio1" > directorios

echo "directorio1" > directorios

```
```Shell
for d in `cat directorios`; do mkdir $d; done

cat dirs | xargs mkdir

```
```PowerShell
ForEach ($d in Get-Content directorios.txt){mkdir $d}

Get-Content .\directorios.txt | %{mkdir $_}

```
