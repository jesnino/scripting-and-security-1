# Check Googlebot can’t access your site
## PowerShell 
### URL: https://www.jesusninoc.com/2014/10/12/check-googlebot-cant-access-site/
```PowerShell
Get-Content 'C:\ips.txt' | Sort-Object | Group-Object | % {
$ip=$_.name
#Add more IP
#Example 66.
if($ip -contains "66.")
{
$ip, [System.Net.Dns]::GetHostbyAddress($_).HostName
}
else
{
$ip
}
}

```
