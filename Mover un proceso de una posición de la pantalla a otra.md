# Mover un proceso de una posición de la pantalla a otra
## PowerShell, Processes 
### URL: https://www.jesusninoc.com/2016/02/03/mover-un-proceso-de-una-posicion-de-la-pantalla-a-otra/
```PowerShell
#Abrir Notepad en una posición y después indicarle otra en la función MoveWindow
Add-Type @"
using System;
using System.Runtime.InteropServices;
public class Win32 {
[DllImport("user32.dll")]
public static extern bool MoveWindow(IntPtr hWnd, int X, int Y, int nWidth, int nHeight, bool bRepaint);
}
"@

[Win32]::MoveWindow((Get-Process -Name notepad).MainWindowHandle, 100, 200, 300, 400, $true)

```
