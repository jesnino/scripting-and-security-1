# Recorrer un rango de direcciones IP y comprobar si un puerto está abierto
## Network, PowerShell 
### URL: https://www.jesusninoc.com/2016/06/12/recorrer-un-rango-de-direcciones-ip-y-comprobar-si-un-puerto-esta-abierto/
```PowerShell
foreach($primer in 1..254)
{
    foreach($segundo in 1..254)
    {
        foreach($tercero in 1..254)
        {
            $ip=("1."+$primer+"."+$segundo+"."+$tercero)
            $tcpClient = New-Object System.Net.Sockets.TCPClient
            $tcpClient.Connect($ip,80)
            if($tcpClient.Connected)
            {
                $ip 
            }
        }
    }
}

```
