# Simulate key press by user with KeyEvent in Android
## Android 
### URL: https://www.jesusninoc.com/2016/04/07/simulate-key-press-by-user-with-keyevent-in-android/
```Shell
KEYCODE_0 Key code constant: '0' key.
KEYCODE_1 Key code constant: '1' key.
KEYCODE_2 Key code constant: '2' key.
KEYCODE_3 Key code constant: '3' key.
KEYCODE_4 Key code constant: '4' key.
KEYCODE_5 Key code constant: '5' key.
KEYCODE_6 Key code constant: '6' key.
KEYCODE_7 Key code constant: '7' key.
KEYCODE_8 Key code constant: '8' key.
KEYCODE_9 Key code constant: '9' key.

```
```PowerShell
#Call 1234
adb.exe shell am start -a android.intent.action.VIEW tel:1
Start-Sleep -Seconds 5
adb shell input keyevent KEYCODE_2
adb shell input keyevent KEYCODE_3
adb shell input keyevent KEYCODE_4
adb shell input keyevent KEYCODE_ENTER

```
