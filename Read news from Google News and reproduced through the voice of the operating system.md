# Read news from Google News and reproduced through the voice of the operating system
## PowerShell 
### URL: https://www.jesusninoc.com/2013/12/09/read-news-google-news-reproduced-voice-operating-system/
```PowerShell
$sam = New-Object -comObject SAPI.SpVoice
[xml]$doc = (New-Object System.Net.WebClient).DownloadString('https://news.google.es/news?pz=1&cf=all&ned=es&hl=es&output=rss')
$doc.rss.channel.Item | %{$sam.Speak($_.title)}

```
