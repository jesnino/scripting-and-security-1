# Convert a string to a int array
## PowerShell, Strings 
### URL: https://www.jesusninoc.com/2014/03/10/convert-a-string-to-a-int-array/
```PowerShell
[string]$a="PowerShell"
for($i=0; $i -lt $a.Length; $i=$i+1)
{([int]$a[$i])}

```
