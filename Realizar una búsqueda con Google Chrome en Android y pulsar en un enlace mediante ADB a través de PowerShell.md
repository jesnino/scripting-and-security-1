# Realizar una búsqueda con Google Chrome en Android y pulsar en un enlace mediante ADB a través de PowerShell
## Android, PowerShell 
### URL: https://www.jesusninoc.com/2016/04/09/realizar-una-busqueda-con-google-chrome-en-android-y-pulsar-en-un-enlace-mediante-adb-a-traves-de-powershell/
```PowerShell
#Abrir Google Chrome en Android mediante ADB
#Es necesario habilitar el modo depuración en Android
cd "D:\program\android-sdk-windows\platform-tools"
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
#Pulsar en una posición
.\adb shell input tap 280 820

```
