# Detectar los servicios que están activos en las direcciones IP de un rango utilizando Nmap
## Network, PowerShell 
### URL: https://www.jesusninoc.com/2016/09/06/detectar-los-servicios-que-estan-activos-en-las-direcciones-ip-de-un-rango-utilizando-nmap/
```PowerShell
1..254 | %{nmap -sV ('192.168.1.'+$_)}

```
