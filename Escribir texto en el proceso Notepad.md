# Escribir texto en el proceso Notepad
## PowerShell 
### URL: https://www.jesusninoc.com/2016/02/14/escribir-texto-en-el-proceso-notepad/
```PowerShell
$codigo='
[DllImport("user32.dll", EntryPoint = "FindWindowEx")]public static extern IntPtr FindWindowEx(IntPtr hwndParent, IntPtr hwndChildAfter, string lpszClass, string lpszWindow);
[DllImport("User32.dll")]public static extern int SendMessage(IntPtr hWnd, int uMsg, int wParam, string lParam);
'
$notepad=Start-Process notepad -PassThru
$notepad.WaitForInputIdle()

$acciones=Add-Type -MemberDefinition $codigo -Name TextoNotepad -PassThru
#FindWindowEx(IntPtr hwndParent, IntPtr hwndChildAfter, string lpszClass, string lpszWindow)
#SendMessage(IntPtr hWnd, int uMsg, int wParam, string lParam)
$acciones::SendMessage([IntPtr]$acciones::FindWindowEx($notepad.MainWindowHandle, [IntPtr]::Zero, "Edit", $null), 0x000C, 0, "Texto")

```
