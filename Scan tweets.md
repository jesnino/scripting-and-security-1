# Scan tweets
## PowerShell 
### URL: https://www.jesusninoc.com/2014/02/22/scan-tweets/
```PowerShell
#JSON Twitter
#Download code: https://copypastebin.com/ucjpeF9A
$ur="https://twitter.com/i/profiles/show/microsoft/timeline?include_available_features=1&include_entities=1&max_id=409692797806333951"
$result=(Invoke-WebRequest -Uri $ur)
$conv=$result.Content
$convi = $conv | ConvertFrom-JSON
#Max id
$convi.max_id
#More items?
$convi.has_more_items
$num=0
while($convi.has_more_items)
{
foreach($i in $convi.items_html.Split("`n"))
{
#Match p class
if($i -Match "js-tweet-text tweet-text")
{
$i
$num++
#parser
##################################################
##################################################
##################################################
}
}
$ur="https://twitter.com/i/profiles/show/microsoft/timeline?include_available_features=1&include_entities=1&max_id="+$convi.max_id
$result=(Invoke-WebRequest -Uri $ur)
$conv=$result.Content
$convi = $conv | ConvertFrom-JSON
#Max id
$convi.max_id
#More items?
}

```
