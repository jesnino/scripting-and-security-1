# Extract number of followers of a user from Twitter
## PowerShell 
### URL: https://www.jesusninoc.com/2014/05/12/extract-number-of-followers-of-a-user-from-twitter/
```PowerShell
#List Twitter Accounts
#Example content:
#https://twitter.com/Microsoft
foreach($url in Get-Content c:powershelllistado.txt)
{
$sinurl=$url.Replace("https://twitter.com/","")
$result = Invoke-WebRequest $url
#Select div class
$result.AllElements | Where Class -eq “ProfileNav-stat ProfileNav-stat--link u-borderUserColor u-textCenter js-tooltip js-nav u-textUserColor” |
%{
#Remplace followers -> Seguidores
if($_.title -match "Seguidores")
{
#Save date and followers
$fecha=Get-Date -format "dd-MMM-yyyy HH:mm"
$fecha + "*" + $_.title.replace(" Seguidores","") >> C:powershell$sinurl.txt
$sinurl
}
}
}

```
