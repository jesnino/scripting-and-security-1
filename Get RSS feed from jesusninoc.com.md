# Get RSS feed from jesusninoc.com
## PowerShell, Web 
### URL: https://www.jesusninoc.com/2013/04/04/get-rss-feed-from-jesusninoc-com/
```PowerShell
#The YQL (Yahoo! Query Language) platform enables you to query, filter, and combine data across the web through a single interface.
#IMPORTANT
#Console: https://developer.yahoo.com/yql/console/
#YOUR YQL STATEMENT: select * from rss where
#url="https://www.jesusninoc.com/feed/"

$ur='https://bit.ly/10CcFq7'

$result=(Invoke-WebRequest -Uri $ur)
$conv=$result.Content
$convi = $conv | ConvertFrom-JSON
foreach($i in $convi)
{$i.query.results.item.title}

```
