# Ducky Script API
## Ducky scripts 
### URL: https://www.jesusninoc.com/2014/12/26/ducky-script-api/
```PowerShell
| REM |

```
```PowerShell
REM The next three lines execute a command prompt in Windows
GUI r
STRING cmd
ENTER

```
```PowerShell
| DEFAULT_DELAY | //n * 10 ms// |
| DEFAULTDELAY | //n * 10 ms// |

```
```PowerShell
DEFAULT_DELAY 10
REM delays 100ms between each subsequent command sequence

```
```PowerShell
| DELAY | //n * 10 ms// |

```
```PowerShell
DELAY 50
REM will wait 500ms before continuing to the next command.

```
```PowerShell
| STRING | a…z A…Z 0..9 !…) `~ += _- “‘ :; <, >. ?/ \ and pipe |

```
```PowerShell
GUI r
DELAY 50
STRING notepad.exe
ENTER
DELAY 100
STRING Hello World!

```
```PowerShell
| GUI | Single Char |
| WINDOWS | Single Char |

```
```PowerShell
GUI r
REM will hold the Windows-key and press r, on windows systems resulting in the Run menu.

```
```PowerShell
| APP |
| MENU |

```
```PowerShell
GUI d
MENU
STRING v
STRING d

```
```PowerShell
| SHIFT | DELETE, HOME, INSERT, PAGEUP, PAGEDOWN, WINDOWS, GUI, UPARROW, DOWNARROW, LEFTARROW, RIGHTARROW, TAB |

```
```PowerShell
SHIFT INSERT
REM this is paste for most operating systems

```
```PowerShell
| ALT |END, ESC, ESCAPE, F1…F12, Single Char, SPACE, TAB |

```
```PowerShell
GUI r
DELAY 50
STRING notepad.exe
ENTER
DELAY 100
STRING Hello World
ALT f
STRING s
REM alt-f pulls up the File menu and s saves. This two keystroke combo is why ALT is jealous of CONTROL's leetness and CTRL+S

```
```PowerShell
| CONTROL | BREAK, PAUSE, F1…F12, ESCAPE, ESC, Single Char |
| CTRL | BREAK, PAUSE, F1…F12, ESCAPE, ESC, Single Char |

```
```PowerShell
CONTROL ESCAPE
REM this is equivalent to the GUI key in Windows

```
```PowerShell
| DOWNARROW or DOWN |
| LEFTARROW or LEFT |
| RIGHTARROW or RIGHT |
| UPARROW or UP |

```
```PowerShell
| BREAK or PAUSE | For the infamous combo CTRL BREAK |
| CAPSLOCK | Cruise control for cool. Toggles |
| DELETE | |
| END | When will it ever |
| ESC or ESCAPE | You can never |
| HOME | There’s no place like |
| INSERT | |
| NUMLOCK | Toggles number lock |
| PAGEUP | |
| PAGEDOWN | |
| PRINTSCREEN | Typically takes screenshots |
| REPEAT X | Repeat previous command X times |
| SCROLLLOCK | Hasn’t been nearly as useful since the GUI was invented |
| SPACE | the final frontier | 
| TAB | not just a cola.

```
