# Pasar un OCR a una captura de pantalla de una búsqueda con Google Chrome en Android mediante ADB a través de PowerShell
## Android, PowerShell 
### URL: https://www.jesusninoc.com/2016/04/27/pasar-un-ocr-a-una-captura-de-pantalla-de-una-busqueda-con-google-chrome-en-android-mediante-adb-a-traves-de-powershell/
```PowerShell
#Abrir Google Chrome en Android mediante ADB
#Es necesario habilitar el modo depuración en Android
cd d:\adb
#Abrir Google Chrome
.\adb shell am start -n com.android.chrome/com.google.android.apps.chrome.Main -d 'https://www.google.es'
Start-Sleep -Seconds 5
#Pulsar en la caja de búsqueda
.\adb shell input tap 101 880
#Buscar la palabra "powershell"
.\adb shell input text "powershell"
#Introducir Enter
.\adb shell input keyevent 66
Start-Sleep -Seconds 5
#Realizar una captura después de realizar la búsqueda
.\adb shell screencap -p /sdcard/screencap.png
.\adb pull /sdcard/screencap.png
.\adb shell rm /sdcard/screencap.png
#Pasar el OCR a la captura y guardar el texto procesado
#Es necesario descar el OCR Tesseract Open Source OCR Engine: https://github.com/tesseract-ocr
D:\Tesseract-OCR\tesseract.exe screencap.png texto.txt

```
