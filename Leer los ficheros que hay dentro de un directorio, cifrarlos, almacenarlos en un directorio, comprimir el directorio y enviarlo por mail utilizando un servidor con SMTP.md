# Leer los ficheros que hay dentro de un directorio, cifrarlos, almacenarlos en un directorio, comprimir el directorio y enviarlo por mail utilizando un servidor con SMTP
## Cryptography, Filesystem, PowerShell, Security 
### URL: https://www.jesusninoc.com/2015/06/17/leer-los-ficheros-que-hay-dentro-de-un-directorio-cifrarlos-almacenarlos-en-un-directorio-comprimir-el-directorio-y-enviarlo-por-mail-utilizando-un-servidor-smtp/
```PowerShell
#Para descrifrar ver: https://www.jesusninoc.com/2015/02/12/algoritmo-de-descifrado-sencillo/ (Algoritmo de descifrado sencillo)

foreach ($fichero in ls F:\power\ficheros)
{
$e=''
foreach ($line in gc F:\power\ficheros\$fichero) {
$n=''
$n+= foreach ($word in ($line.Split()))
{
$chars = for ($i=0;$i -lt $word.length;$i++)
{
$x=$word[$i]
$x=[char]::ConvertToUtf32(“$x”,0)
[int]$y=$x+8
[char]::ConvertFromUtf32($y)
}
$chars -join ''
}
$e+=$n
}
$e | out-file F:\power\ficherosconvertidos\$fichero
$ficherodestino='C:\powershell\comprimidoconvertido.zip'
Compress-Archive -LiteralPathF:\power\ficherosconvertidos\$fichero –CompressionLevel Optimal -DestinationPath $ficherodestino

Send-MailMessage -To 'user2@gmail.com' -From 'user1@example.com' -Subject 'Fichero comprimido' -Attachments $ficherodestino <strong>-SmtpServer</strong> localhost
}

```
