# Rotate screen
## PowerShell 
### URL: https://www.jesusninoc.com/2016/02/24/rotate-screen/
```PowerShell
[System.Windows.Forms.SendKeys]::SendWait("^%({RIGHT})")
Start-Sleep -Seconds 2
[System.Windows.Forms.SendKeys]::SendWait("^%({LEFT})")
Start-Sleep -Seconds 2
[System.Windows.Forms.SendKeys]::SendWait("^%({DOWN})")
Start-Sleep -Seconds 2
[System.Windows.Forms.SendKeys]::SendWait("^%({UP})")

```
