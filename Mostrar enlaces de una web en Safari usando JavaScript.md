# Mostrar enlaces de una web en Safari usando JavaScript
## AppleScript, JavaScript, Web 
### URL: https://www.jesusninoc.com/2016/03/09/mostrar-enlaces-de-una-web-en-safari-usando-javascript/
```AppleScript
tell application "Safari"
	open location "https://jesusninoc.com"
	delay 10
	set links to "var links = document.links;
    for(var i=0;i<links.length;i++){
    alert(\"Enlace#\"+(i+1)+\":\"+links[i].href);
    }"
	do JavaScript links in the front document
end tell

```
