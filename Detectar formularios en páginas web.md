# Detectar formularios en páginas web
## PowerShell, Web, Web scraping 
### URL: https://www.jesusninoc.com/2016/06/27/detectar-formularios-en-paginas-web/
```PowerShell
(((Invoke-WebRequest 'https://www.google.es/').AllElements).where{$_.tagName -eq "form"})

```
