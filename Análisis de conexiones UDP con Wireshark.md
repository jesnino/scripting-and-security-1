# Análisis de conexiones UDP con Wireshark
## Network, PowerShell 
### URL: https://www.jesusninoc.com/2016/03/15/analisis-de-conexiones-udp-con-wireshark/
```PowerShell
##Client
$port=2020
$endpoint = new-object System.Net.IPEndPoint ([IPAddress]"192.168.1.56",$port)
$udpclient=new-Object System.Net.Sockets.UdpClient
$b=[Text.Encoding]::ASCII.GetBytes('Hi')
$bytesSent=$udpclient.Send($b,$b.length,$endpoint)
$udpclient.Close()

```
```PowerShell
##Server
$port=2020
$endpoint = new-object System.Net.IPEndPoint ([IPAddress]::Any,$port)
$udpclient=new-Object System.Net.Sockets.UdpClient $port
$content=$udpclient.Receive([ref]$endpoint)
[Text.Encoding]::ASCII.GetString($content)

```
