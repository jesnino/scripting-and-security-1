# Buscar información en el Firewall de Windows
## Network, PowerShell 
### URL: https://www.jesusninoc.com/2016/04/24/buscar-informacion-en-el-firewall-de-windows/
```PowerShell
#Detectar regla sobre programas permtidos
Get-NetFirewallRule | Where-Object {$_.name -match '.exe'} | select *
#Detectar regla sobre un programa permitido
Get-NetFirewallRule | Where-Object {$_.DisplayName -match 'MySQL'} | select *

```
