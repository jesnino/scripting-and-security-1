# How to save your Twitter timeline to a file
## PowerShell 
### URL: https://www.jesusninoc.com/2014/11/18/save-twitter-timeline-file/
```PowerShell
#JSON Twitter
$numero="490274947189993472"
while($numero)
{
$numero
$ur='https://twitter.com/i/profiles/show/Microsoft/timeline?include_available_features=1&include_entities=1&max_id='+$numero
$result=(Invoke-WebRequest -Uri $ur)
$conv=$result.Content
$convi = $conv | ConvertFrom-JSON
#Max id
$numero=$convi.max_id
#More items?
$convi.items_html >> 'F:\power\dao.html'
}

```
