# Codificar un string en Base64
## PowerShell 
### URL: https://www.jesusninoc.com/2016/09/22/codificar-un-string-en-base64/
```PowerShell
#UTF8
[System.Convert]::ToBase64String([System.Text.Encoding]::UTF8.GetBytes('cadena'))
#Unicode
[System.Convert]::ToBase64String([System.Text.Encoding]::Unicode.GetBytes('cadena'))

```
