# Almacenar frecuencias en un fichero de audio con rtl_fm
## Bash, Multimedia, Radio 
### URL: https://www.jesusninoc.com/2016/04/19/almacenar-frecuencias-en-un-fichero-de-audio-con-rtl_fm/
```Shell
rtl_fm -f 434977400 -p 22 - | sox -t raw -e signed -c 1 -b 16 -r 11025 - fichero.wav

```
