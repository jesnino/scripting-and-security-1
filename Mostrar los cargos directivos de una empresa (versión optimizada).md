# Mostrar los cargos directivos de una empresa (versión optimizada)
## PowerShell, Web scraping 
### URL: https://www.jesusninoc.com/2016/01/07/mostrar-los-cargos-directivos-de-una-empresa-version-optimizada/
```PowerShell
(((Invoke-WebRequest 'https://www.empresia.es/empresa/google-spain/').AllElements).where{$_.id -eq "ListaRelaciones"}).innerText

```
