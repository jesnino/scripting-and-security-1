# Select title and photo where text is “XXXX” (Flickr) and convert to JSON (YQL statement)
## PowerShell 
### URL: https://www.jesusninoc.com/2013/03/27/select-title-and-photo-where-text-is-xxxx-flickr-and-convert-to-json-yql-statement/
```PowerShell
#Well, it does not work like that

#IMPORTANT
#Console: https://developer.yahoo.com/yql/console/
#YOUR YQL STATEMENT: select * from flickr.photos.search where text="Cat" and api_key="XXXXX" limit 10
#URL: https://developer.yahoo.com/yql/console/#
#h=select%20*%20from%20flickr.photos.search%20where%20text
#%3D%22Cat%22%20and%20api_key
#%3D%22XXXXX%22%20limit%2010

#Need an Api Key
$ur="https://bit.ly/YSJjT9"

$result=(Invoke-WebRequest -Uri $ur)
$conv=$result.Content
$convi = $conv | ConvertFrom-JSON
foreach($i in $convi)
{$a=$i.query.results.photo
$a.id,$a.title}

```
