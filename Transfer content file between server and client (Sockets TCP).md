# Transfer content file between server and client (Sockets TCP)
## Network, PowerShell, Security, Servers 
### URL: https://www.jesusninoc.com/2014/02/15/transfer-content-file-between-server-and-client-sockets-tcp/
```PowerShell
##Server
$port=2050
$IPEndPoint=New-Object System.Net.IPEndPoint([IPAddress]::Any,$port)
$TcpListener=New-Object System.Net.Sockets.TcpListener $IPEndPoint
$TcpListener.Start()

$AcceptTcpClient=$TcpListener.AcceptTcpClient()
$GetStream=$AcceptTcpClient.GetStream()
$StreamReader=New-Object System.IO.StreamReader $GetStream
do{
$ReadLine = $StreamReader.ReadLine()
$ReadLine
}while ($ReadLine)

$StreamReader.Dispose()
$GetStream.Dispose()
$AcceptTcpClient.Dispose()
$TcpListener.Stop()

```
```PowerShell
##Client
$port=2050
$TcpClient=New-Object System.Net.Sockets.TcpClient([IPAddress]::Loopback, $port)

$GetStream = $TcpClient.GetStream()
$StreamWriter = New-Object System.IO.StreamWriter $GetStream

$file=Get-Content 'F:\power\file.txt'
$file | %{
$StreamWriter.Write($_)
}

$StreamWriter.Dispose()
$GetStream.Dispose()
$TcpClient.Dispose()

```
