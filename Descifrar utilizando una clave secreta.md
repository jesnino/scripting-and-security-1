# Descifrar utilizando una clave secreta
## Cryptography, PowerShell, Security 
### URL: https://www.jesusninoc.com/2015/08/20/descifrar-utilizando-una-clave-secreta/
```PowerShell
$clave='clavesecreta123'
 
#La clave para cifrar tiene que ser correcta en tipo System.Byte
$clavebyte=[Byte[]]($clave.PadRight(24).Substring(0,24).ToCharArray())
 
$cadenadescifrando = $cadenacifrada | ConvertTo-SecureString -Key $clavebyte
 
$BSTR = [System.Runtime.InteropServices.Marshal]::SecureStringToBSTR($cadenadescifrando)
$PlainPassword = [System.Runtime.InteropServices.Marshal]::PtrToStringAuto($BSTR)
$PlainPassword

```
