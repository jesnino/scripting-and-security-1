# Escribir un texto en el procesador de texto TextEdit de Mac
## AppleScript 
### URL: https://www.jesusninoc.com/2016/01/16/escribir-hola-mundo-en-el-procesador-de-texto-textedit-de-mac/
```AppleScript
tell application "TextEdit"
activate
make new document
set text of front document to "Hola mundo"
end tell

```
