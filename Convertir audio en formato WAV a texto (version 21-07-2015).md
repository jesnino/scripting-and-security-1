# Convertir audio en formato WAV a texto (version 21-07-2015)
## Multimedia, PowerShell, Recognition 
### URL: https://www.jesusninoc.com/2015/07/21/convertir-audio-en-formato-wav-a-texto-version-21-07-2015/
```PowerShell
#Abrir un fichero WAV y convertir a texto el contenido

#Más información: https://msdn.microsoft.com/en-us/library/ms720151(v=vs.85).aspx#API_Speech_Recognition

[void][reflection.assembly]::loadwithpartialname('system.speech')
$rec = New-Object 'System.Speech.Recognition.SpeechRecognitionEngine'
$rec.RecognizerInfo.Description
$rec.LoadGrammar((New-Object 'System.Speech.Recognition.DictationGrammar'))
$rec.SetInputToWaveFile('F:\power\song.wav')
for(1)
{
$rec.Recognize().Text
}

```
