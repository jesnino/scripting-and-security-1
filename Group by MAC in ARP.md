# Group by MAC in ARP
## Network, PowerShell, Security 
### URL: https://www.jesusninoc.com/2014/05/12/group-by-mac-in-arp/
```PowerShell
$all=""
$arps=arp -a
foreach($line in $arps)
{
if($line -match "mico")
{
$line
$a=$line.Replace(" "," ")
$a=$a.Split(" ")
$all=$all+"*"+$a[9]
}
}
$all.Split("*") | Group-Object | Sort-Object Count -descending

```
