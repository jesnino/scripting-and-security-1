# Get streets and coordinates (new version)
## PowerShell 
### URL: https://www.jesusninoc.com/2013/03/26/get-streets-and-coordinates-new-version/
```PowerShell
#The Google Geocoding API
#https://developers.google.com/maps/documentation/geocoding/

$calle='Avenida de Concha Espina 1'
$urlsi='https://maps.googleapis.com/maps/api/geocode/json?address=' + $calle + '+MADRID'
$urlsi=$urlsi.replace(' ','+')
$urlsi
$resulti=(Invoke-WebRequest -Uri $urlsi)

foreach($pit in $resulti.Content)
{
    $conver=$pit | ConvertFrom-JSON
    $lat=$conver.results.geometry.location.lat
    $long=$conver.results.geometry.location.lng
    $urlgooglemap='https://www.google.es/maps?q='+$lat+','+$long
    Write-Host $lat $long
}

```
