# Partir un fichero WAV dividiendo por silencios
## Multimedia 
### URL: https://www.jesusninoc.com/2015/07/25/partir-un-fichero-wav-dividiendo-por-silencios/
```PowerShell
sox -V3 sound.wav output.wav silence 1 0.50 0.1% 1 0.3 0.1% : newfile : restart

```
