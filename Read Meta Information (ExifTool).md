# Read Meta Information (ExifTool)
## PowerShell 
### URL: https://www.jesusninoc.com/2014/12/20/read-meta-information-exiftool/
```PowerShell
#ExifTool is a platform-independent Perl library plus a command-line application for reading, writing and editing meta information in a wide variety of files. ExifTool supports many different metadata formats including EXIF, GPS, IPTC, XMP, JFIF, GeoTIFF, ICC Profile, Photoshop IRB, FlashPix, AFCP and ID3, as well as the maker notes of many digital cameras by Canon, Casio, FLIR, FujiFilm, GE, HP, JVC/Victor, Kodak, Leaf, Minolta/Konica-Minolta, Nikon, Nintendo, Olympus/Epson, Panasonic/Leica, Pentax/Asahi, Phase One, Reconyx, Ricoh, Samsung, Sanyo, Sigma/Foveon and Sony.

#ExifTool is installed in the local

ls F:\power\fotos\fotos | %{
$_
$meta=([xml](.\exiftool.exe $_.FullName -X)).rdf.description
$meta
}

```
