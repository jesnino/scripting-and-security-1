# Leer RSS Feeds
## PowerShell 
### URL: https://www.jesusninoc.com/2016/01/15/leer-rss-feeds/
```PowerShell
([XML](Invoke-WebRequest -Uri 'https://www.jesusninoc.com/feed').Content).rss.channel.item | Select-Object title

```
