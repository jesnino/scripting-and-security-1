# Select and download images in Google images
## PowerShell 
### URL: https://www.jesusninoc.com/2014/04/12/select-download-images-google-images/
```PowerShell
$i=1
(Invoke-WebRequest 'https://www.google.es/search?q=powershell&tbm=isch' | select -expand images | select -expand src) | %{
$name="imagen"+$i+".jpg"
Start-BitsTransfer -Source $_ -Destination F:\power\$name
$i++
}

```
