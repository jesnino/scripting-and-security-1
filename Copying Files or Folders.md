# Copying Files or Folders
## Filesystem, PowerShell 
### URL: https://www.jesusninoc.com/2014/11/17/copying-files-folders/
```PowerShell
Copy-Item c:\scripts\test.txt c:\test

```
```PowerShell
Copy-Item c:\scripts\* c:\test

```
```PowerShell
Copy-Item c:\scripts\*.txt c:\test

```
```PowerShell
Copy-Item c:\scripts c:\test -recurse

```
