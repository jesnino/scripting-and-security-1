# Mostrar las tendencias de búsqueda más recientes en Google Trends
## PowerShell, Web scraping 
### URL: https://www.jesusninoc.com/2016/02/26/mostrar-las-tendencias-de-busqueda-mas-recientes-en-google-trends/
```PowerShell
(((Invoke-WebRequest 'https://www.google.es/trends/hottrends/widget?pn=p26&tn=20').AllElements).where{$_.Class -eq "widget-title-in-list"}).innerText

```
```PowerShell
$contenido=[xml](Invoke-WebRequest -Uri 'https://www.google.es/trends/hottrends/atom/feed?pn=p26').content $contenido.rss.channel.item | %{$_.title,$_.pubDate}

```
