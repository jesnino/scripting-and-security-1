# Intensidad de la señal de la conexión inalámbrica
## Network, PowerShell, Wireless 
### URL: https://www.jesusninoc.com/2015/01/17/intensidad-de-la-senal-de-la-conexion-inalambrica/
```PowerShell
netsh wlan show interface | Select-String Nombre,SSID,BSSID,Se¤al

```
