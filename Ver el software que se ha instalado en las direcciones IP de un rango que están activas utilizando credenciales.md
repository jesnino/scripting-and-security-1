# Ver el software que se ha instalado en las direcciones IP de un rango que están activas utilizando credenciales
## Network, PowerShell 
### URL: https://www.jesusninoc.com/2016/09/19/ver-el-software-que-se-ha-instalado-en-las-direcciones-ip-de-un-rango-que-estan-activas-utilizando-credenciales/
```PowerShell
$credencial=Get-Credential
1..254 | %{
('192.168.1.'+$_)
if(Test-Connection ('192.168.1.'+$_) -Quiet)
{
Get-WmiObject -Class Win32_Product -ComputerName ('192.168.1.'+$_) -Credential $credencial
}
}

```
