# Morse code
## PowerShell 
### URL: https://www.jesusninoc.com/2014/10/27/morse-code/
```PowerShell
#Morse code
#morse.txt
#A|. –
#B|– . . .
#C|– . – .
#Ch|– – – –
#D|– . .
#E|.
#F|. . – .
#G|– – .
#H|. . . .
#I|. .
#J|. – – –
#K|– . –
#L|. – . .
#M|– –
#N|– .
#Ñ|– – . – –
#O|– – –
#P|. – – .
#Q|– – . –
#R|. – .
#S|. . .
#T|–
#U|. . –
#V|. . . –
#W|. – –
#X|– . . –
#Y|– . – –
#Z|– – . .

Get-Content F:\power\morse.txt | %{
$letter=$_.split("|")[0]
$morse=$_.split("|")[1]
$values=$morse.split(" ")
Write-Host $letter,$morse
foreach($sound in $values)
{
if($sound -eq ".")
{
[console]::beep(2000,500)
}
elseif($sound -eq "–")
{
[console]::beep(2000,800)
}
}
}

```
