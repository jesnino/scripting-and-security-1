# Realizar petición HTTP utilizando el método POST
## PHP, PowerShell, Servers, Web 
### URL: https://www.jesusninoc.com/2015/12/09/realizar-peticion-http-utilizando-el-metodo-post/
```PowerShell
#Crear el fichero PHP con el contenido:
#<?php echo htmlspecialchars($_POST['nombre']); ?> tiene <?php echo (int)$_POST['edad']; ?> años.

$postParams = @{nombre='Juan';edad='34'}
$web=Invoke-WebRequest -Uri 'https://localhost/examplepost.php' -Method Post -Body $postParams
$web.content

```
