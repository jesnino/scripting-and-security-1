# Mostrar información sobre procesos en Linux y Windows
## Bash, PowerShell, Processes, Services, Threads 
### URL: https://www.jesusninoc.com/2015/02/03/mostrar-informacion-sobre-procesos-en-linux-y-windows/
```Shell
ps aux

```
```PowerShell
Get-Process | select *
Get-WmiObject win32_process

```
```Shell
ps -f -u juanito

```
```PowerShell
Get-WmiObject win32_process |% {Write-Host $_.processname $_.getowner().user}

```
```Shell
ps -C nano

```
```PowerShell
Get-Process -Name notepad

```
```Shell
ps -f  -p 2732

```
```PowerShell
Get-Process -Id 2732

```
```Shell
ps aux --sort=-pcpu,+pmem

```
```PowerShell
Get-Process | Sort-Object CPU,PM

```
```Shell
ps -f --forest -C nano

```
```PowerShell
Get-Process | Select * | Format-Custom

```
```Shell
ps -o pid,uname,comm -C nano

```
```PowerShell
Get-WmiObject win32_process | Select-Object ParentProcessId,ProcessId

```
```Shell
ps -p 1112 -L

```
```PowerShell
(Get-Process -Id 1112) | Select-Object Id,Threads

```
```Shell
ps -e -o pid,pcpu,pmem

```
```PowerShell
Get-Process | Select-Object Id,CPU,PM

```
```Shell
ps -e -o pid,comm,etime

```
```PowerShell
Get-Process | Select-Object Id,TotalProcessorTime

```
