# Enviar correos masivos
## PowerShell, Servers 
### URL: https://www.jesusninoc.com/2015/01/15/enviar-correos-masivos/
```PowerShell
#Abrir fichero con cuentas de correo
Get-Content F:\power\correos.txt | %{
#Es necesario tener un servidor SMTP instalado
Send-MailMessage -to $_ -from "mail@example.com" -subject "Test mail" -SmtpServer localhost
}

```
