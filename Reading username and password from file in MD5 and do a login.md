# Reading username and password from file in MD5 and do a login
## Cryptography, PowerShell, Security 
### URL: https://www.jesusninoc.com/2014/03/10/reading-username-password-file-md5-login/
```PowerShell
#Read user and password
$user=Read-Host
$pass=Read-Host

#Read MD5 file userpass.txt, example content:
#24c9e15e52afc47c225b757e7bee1f9d,4604c8f5d958fea18967bbc7504d0f03 is user1,passwoasdfK$
#Convert user and pass to MD5 and compare
#MD5
$result1=''
$result2=''
$cryptoServiceProvider = [System.Security.Cryptography.MD5CryptoServiceProvider]
$hashAlgorithm = new-object $cryptoServiceProvider
$hashByteArray1 = $hashAlgorithm.ComputeHash([Char[]]$user)
foreach($byte in $hashByteArray1) { $result1 += '{0:X2}' -f $byte}
$hashByteArray1 = $hashAlgorithm.ComputeHash([Char[]]$pass)
foreach($byte in $hashByteArray1) { $result2 += '{0:X2}' -f $byte}
Get-Content userpass.txt | % {if(($_.split(",")[0] -like $result1) -and ($_.split(",")[1] -like $result2)){"Login OK"}}

```
