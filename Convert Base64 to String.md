# Convert Base64 to String
## PowerShell 
### URL: https://www.jesusninoc.com/2015/10/05/convert-base64-to-string/
```PowerShell
[System.Text.Encoding]::UTF8.GetString([System.Convert]::FromBase64String('aG9sYQ=='))

```
