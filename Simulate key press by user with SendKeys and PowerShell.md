# Simulate key press by user with SendKeys and PowerShell
## Automation, PowerShell 
### URL: https://www.jesusninoc.com/2015/11/05/simulate-key-press-by-user-with-sendkeys-and-powershell/
```PowerShell
#Write some text
[System.Windows.Forms.SendKeys]::SendWait("Hi")
#Press on Enter
[System.Windows.Forms.SendKeys]::SendWait("{ENTER}")
#Repeat a key
[System.Windows.Forms.SendKeys]::SendWait("{RIGHT 5}")

```
