# Get image for captcha session
## PowerShell, Security 
### URL: https://www.jesusninoc.com/2013/12/09/get-image-for-captcha-session/
```PowerShell
[int]$aa=0
for(1)
{
    $a=Invoke-WebRequest 'https://example.com/register/'
    $t=$a.Images
    $aa=$aa+1
    $remoteUri = $t[4].src
    $b= $aa.ToString() + ".gif"
    $fileName = $b
    $webClient = new-object System.Net.WebClient
    $webClient.DownloadFile($remoteUri, $fileName)
}

```
