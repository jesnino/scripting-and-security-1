# TCP connect
## Network, PowerShell, Security 
### URL: https://www.jesusninoc.com/2014/02/05/tcp-connect/
```PowerShell
$tcpClient = New-Object System.Net.Sockets.TCPClient
$tcpClient.Connect("localhost",446)
$tcpClient.Connected

```
