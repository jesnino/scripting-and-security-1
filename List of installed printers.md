# List of installed printers
## Hardware, PowerShell 
### URL: https://www.jesusninoc.com/2016/05/30/list-of-installed-printers/
```PowerShell
(Get-WmiObject -Class Win32_Printer).Name

```
