# Check if a text has been modified during transmission (using MD5)
## Cryptography, Network, PowerShell, Security, Servers 
### URL: https://www.jesusninoc.com/2014/02/28/check-if-a-text-has-been-modified-during-transmission-using-md5/
```PowerShell
#############################
##Server
#############################
$port=2021
$endpoint = new-object System.Net.IPEndPoint ([IPAddress]::Any,$port)
$udpclient=new-Object System.Net.Sockets.UdpClient $port
$content=$udpclient.Receive([ref]$endpoint)
$convert=[Text.Encoding]::ASCII.GetString($content)
$spli=$convert.Split(“*”)

$val=$spli[1]

#MD5
$result1=""
$cryptoServiceProvider = [System.Security.Cryptography.MD5CryptoServiceProvider];
$hashAlgorithm = new-object $cryptoServiceProvider
$hashByteArray1 = $hashAlgorithm.ComputeHash([Char[]]$val);
foreach($byte in $hashByteArray1) { $result1 += “{0:X2}” -f $byte}

if($spli[0] -eq $result1)
{
Write-Host "Text unchanged, same source and destination"
Write-Host "MD5 source" + $spli[0] + "MD5 destination" + $result1
}
else
{
Write-Host "Text changed, isn't the same in the source and destination"
Write-Host "MD5 source" + $spli[0] + "MD5 destination" + $result1
}

$udpclient.Close()

```
```PowerShell
#############################
##Client
#############################
$port=2021
$endpoint = new-object System.Net.IPEndPoint ([IPAddress]::Loopback,$port)
$udpclient=new-Object System.Net.Sockets.UdpClient

$val="hola"

#MD5
$result1=""
$cryptoServiceProvider = [System.Security.Cryptography.MD5CryptoServiceProvider];
$hashAlgorithm = new-object $cryptoServiceProvider
$hashByteArray1 = $hashAlgorithm.ComputeHash([Char[]]$val);
foreach($byte in $hashByteArray1) { $result1 += “{0:X2}” -f $byte}

#Bad solution
$enviar=$result1.ToString()+"*"+$val

$b=[Text.Encoding]::ASCII.GetBytes($enviar.ToString())
$bytesSent=$udpclient.Send($b,$b.length,$endpoint)
$udpclient.Close()

```
