# Read in a Comma-Separated Values File
## PowerShell 
### URL: https://www.jesusninoc.com/2014/11/12/read-comma-separated-values-file/
```PowerShell
Name,Department,Title
Paula Marín,Research,Manager
Juan Hana,Finance,Finance Specialist
Carlos Abel,Finance,Accountant

```
```PowerShell
Import-Csv c:\scripts\test.txt

```
```PowerShell
Name                       Department                 Title
----                       ----------                 -----
Paula Marín             Research                   Manager
Juan Hana              Finance                    Finance Specialist
Carlos Abel                   Finance                    Accountant

```
```PowerShell
Import-Csv c:\scripts\test.txt | Where-Object {$_.department -eq "Finance"}

```
```PowerShell
Name                       Department                 Title
----                       ----------                 -----
Juan Hana              Finance                    Finance Specialist
Carlos Abel                   Finance                    Accountant

```
```PowerShell
Import-Csv c:\scripts\test.txt | Where-Object {$_.department -ne "Finance"}

```
```PowerShell
Name                       Department                 Title
----                       ----------                 -----
Paula Marín             Research                   Manager

```
```PowerShell
Import-Csv c:\scripts\test.txt | Where-Object {$_.department -eq "Finance" -and $_.title -eq "Accountant"}

```
```PowerShell
Name                       Department                 Title
----                       ----------                 -----
Carlos Abel                   Finance                    Accountant

```
```PowerShell
Import-Csv c:\scripts\test.txt | Where-Object {$_.department -eq "Research" -or $_.title -eq "Accountant"}

```
```PowerShell
Name                       Department                 Title
----                       ----------                 -----
Paula Marín             Research                   Manager
Carlos Abel                   Finance                    Accountant

```
