# Say remote user
## PowerShell 
### URL: https://www.jesusninoc.com/2011/03/20/say-remote-user/
```PowerShell
$sam = New-Object -comObject SAPI.SpVoice
$sam.Speak((gwmi -class win32_computerSystem -ComputerName .).username)

```
