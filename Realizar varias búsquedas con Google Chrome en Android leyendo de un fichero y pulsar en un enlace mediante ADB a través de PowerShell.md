# Realizar varias búsquedas con Google Chrome en Android leyendo de un fichero y pulsar en un enlace mediante ADB a través de PowerShell
## Android, PowerShell 
### URL: https://www.jesusninoc.com/2016/04/10/realizar-varias-busquedas-con-google-chrome-en-android-leyendo-de-un-fichero-y-pulsar-en-un-enlace-mediante-adb-a-traves-de-powershell/
```PowerShell
cd "D:\program\android-sdk-windows\platform-tools"

#Crear el fichero con el contenido de la palabra a buscar y la posición donde hacer clic
#powershell,280 820
#powershell,280 1385

gc D:\buscar.txt | %{
$_
.\adb shell am start -n com.android.chrome/com.google.android.apps.chrome.Main -d 'https://www.google.es'
Start-Sleep -Seconds 5
.\adb shell input tap 101 880
#Buscar la palabra powershell
.\adb shell input text $_.Split(',')[0]
.\adb shell input keyevent 66
Start-Sleep -Seconds 5
#Pulsar en la posición 280,820
.\adb shell input tap $_.Split(',')[1]
Start-Sleep -Seconds 5
}

```
