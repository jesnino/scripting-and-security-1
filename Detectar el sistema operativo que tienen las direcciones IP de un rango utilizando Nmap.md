# Detectar el sistema operativo que tienen las direcciones IP de un rango utilizando Nmap
## Network, PowerShell 
### URL: https://www.jesusninoc.com/2016/09/04/detectar-el-sistema-operativo-que-tienen-las-direcciones-ip-de-un-rango-utilizando-nmap/
```PowerShell
1..254 | %{nmap -O ('192.168.1.'+$_)}

```
