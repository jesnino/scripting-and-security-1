# Leer las noticias de un medio de comunicación mediante la voz del Sistema Operativo
## Automation, Multimedia, PowerShell 
### URL: https://www.jesusninoc.com/2015/08/07/leer-las-noticias-de-un-medio-de-comunicacion-mediante-la-voz-del-sistema-operativo/
```PowerShell
$sam = New-Object -comObject SAPI.SpVoice
[xml]$xml=(Invoke-WebRequest 'rss.elconfidencial.com/espana/').content
$xml.feed.entry.title.'#cdata-section' | %{$sam.Speak($_)}

```
