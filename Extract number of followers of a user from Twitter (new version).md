# Extract number of followers of a user from Twitter (new version)
## PowerShell 
### URL: https://www.jesusninoc.com/2014/05/14/extract-number-followers-user-twitter-new-version/
```PowerShell
$url = "https://twitter.com/microsoft"
$result = Invoke-WebRequest $url
$result.AllElements | Where Class -eq “ProfileNav-value” | %{$_.innerText}

```
