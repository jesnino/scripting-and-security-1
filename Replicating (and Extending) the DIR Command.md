# Replicating (and Extending) the DIR Command
## Filesystem, PowerShell 
### URL: https://www.jesusninoc.com/2014/12/17/replicating-extending-dir-command/
```PowerShell
Directory: Microsoft.Windows PowerShell.Core\FileSystem::C:\Documents and Settings\user

Mode LastWriteTime Length Name
---- ------------- ------ ----
d---- 3/1/2013 9:03 AM Bluetooth Software
d---s 5/10/2013 8:55 AM Cookies
d---- 5/9/2013 2:09 PM Desktop
d-r-- 5/9/2013 8:22 AM Favorites
d-r-- 5/9/2013 2:24 PM My Documents
d-r-- 3/1/2013 8:15 AM Start Menu
d---s 3/1/20133:41 PM UserData
d---- 3/16/2013 3:29 PM WINDOWS

```
```PowerShell
Get-ChildItem -recurse

```
```PowerShell
Get-ChildItem env:

```
```PowerShell
Get-ChildItem HKLM:\SOFTWARE\Microsoft\Windows\CurrentVersion\Uninstall

```
```PowerShell
Get-ChildItem c:\scripts\*.* -include *.txt,*.log

```
```PowerShell
Mode LastWriteTime Length Name
---- ------------- ------ ----
-a--- 4/6/2013 8:28 PM 3508 950.Log
-a--- 4/28/2013 1:16 PM 27 x.txt
-a--- 5/8/2013 2:39 PM 25 y.txt

```
```PowerShell
Get-ChildItem c:\scripts\*.* -exclude *.txt,*.log

```
```PowerShell
Get-ChildItem c:\scripts\*.* | Sort-Object length

```
```PowerShell
Get-ChildItem c:\scripts\*.* | Sort-Object length -descending

```
