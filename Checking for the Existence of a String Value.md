# Checking for the Existence of a String Value
## Filesystem, PowerShell, Strings 
### URL: https://www.jesusninoc.com/2014/11/06/checking-existence-string-value/
```PowerShell
Operation succeeded, 5/1/2014
Operation succeeded, 5/2/2014
Operation failed, 5/3/2014
Operation succeeded, 5/4/2014
Operation succeeded, 5/5/2014

```
```PowerShell
Get-Content c:\scripts\test.txt | Select-String "Failed" -quiet

```
```PowerShell
Operation failed, 5/3/2014

```
```PowerShell
Get-Content c:\scripts\test.txt | Select-String "Failed" -quiet -casesensitive

```
