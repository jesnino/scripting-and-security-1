# Obtener las cuentas relacionadas a otra en Twitter (versión optimizada)
## PowerShell, Web scraping 
### URL: https://www.jesusninoc.com/2016/02/22/obtener-las-cuentas-relacionadas-a-otra-en-twitter-version-optimizada/
```PowerShell
Start-Process chrome 'https://twitter.com/i/related_users/15670515'
(((Invoke-WebRequest -Uri 'https://twitter.com/i/related_users/15670515').Content) |  ConvertFrom-JSON).related_users_html

```
