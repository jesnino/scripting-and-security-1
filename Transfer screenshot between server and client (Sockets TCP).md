# Transfer screenshot between server and client (Sockets TCP)
## Graphics, Network, PowerShell, Security, Servers 
### URL: https://www.jesusninoc.com/2015/07/13/transfer-screenshot-between-server-and-client-sockets-tcp/
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
[System.IO.File]::WriteAllBytes('F:\power\screenshotcopy.bmp',$Bytes)

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

$path=’F:\power\screenshot.bmp’
$Bitmap=New-Object System.Drawing.Bitmap([System.Windows.Forms.Screen]::PrimaryScreen.Bounds.Width, [System.Windows.Forms.Screen]::PrimaryScreen.Bounds.Height)
$Graphics=[System.Drawing.Graphics]::FromImage($Bitmap)
$Graphics.CopyFromScreen((New-Object System.Drawing.Point(0,0)), (New-Object System.Drawing.Point(0,0)), $Bitmap.Size)
$Graphics.Dispose()
$Bitmap.Save($path,'Bmp')

$Bytes = [System.IO.File]::ReadAllBytes($path)
$StreamWriter.Write($Bytes,0,$Bytes.length)

$StreamWriter.Dispose()
$GetStream.Dispose()
$TcpClient.Dispose()

```
