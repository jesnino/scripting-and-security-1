# Habilitar el firewall de Windows
## Network, PowerShell 
### URL: https://www.jesusninoc.com/2016/05/29/habilitar-el-firewall-de-windows/
```PowerShell
Set-NetFirewallProfile -Profile Domain,Public,Private -Enabled True

```
