# Obtener enlaces de Youtube
## Automation, PowerShell, Web scraping 
### URL: https://www.jesusninoc.com/2016/08/04/obtener-enlaces-de-youtube/
```PowerShell
$url="https://www.youtube.com/results?search_query=no+dolls"
$result = Invoke-WebRequest $url
($result.Links.href | Select-String "watch" | Group-Object).Name | %{"https://www.youtube.com"+$_}

```
