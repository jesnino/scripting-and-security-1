# Mostrar últimos tweets de una cuenta
## PowerShell, Web scraping 
### URL: https://www.jesusninoc.com/2016/03/18/mostrar-ultimos-tweets-de-una-cuenta/
```PowerShell
(((Invoke-WebRequest 'https://twitter.com/microsoft').AllElements).where{$_.Class -eq "TweetTextSize TweetTextSize--16px js-tweet-text tweet-text"}).innerText

```
