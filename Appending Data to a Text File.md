# Appending Data to a Text File
## Filesystem, PowerShell 
### URL: https://www.jesusninoc.com/2014/11/05/appending-data-text-file/
```PowerShell
Add-Content c:\scripts\test.txt "The End"

```
```PowerShell
Add-Content c:\scripts\test.txt "`nThe End"

```
```PowerShell
`0 -- Null
`a -- Alert
`b -- Backspace
`n -- New line
`r -- Carriage return
`t -- Horizontal tab
`' -- Single quote
`" -- Double quote

```
```PowerShell
Write-Host `a

```
```PowerShell
$A = Get-Date; Add-Content c:\scripts\*.log $A

```
