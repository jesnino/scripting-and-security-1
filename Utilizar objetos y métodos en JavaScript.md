# Utilizar objetos y métodos en JavaScript
## JavaScript, PowerShell 
### URL: https://www.jesusninoc.com/2016/03/28/utilizar-objetos-y-metodos-en-javascript/
```PowerShell
$ie = New-Object -com "InternetExplorer.Application"
$ie.Navigate("about:blank")
$ie.visible = $true

$ie.document.write('<p id="mostrar"></p>
<script>
var persona = {
    nombre: "Pepe",
    mostrarnombre : function() {
       return this.nombre;
    }
};
document.getElementById("mostrar").innerHTML = persona.mostrarnombre();</script>')

```
