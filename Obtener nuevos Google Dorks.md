# Obtener nuevos Google Dorks
## Database, PowerShell, Security, Web scraping 
### URL: https://www.jesusninoc.com/2015/12/01/obtener-nuevos-google-dorks/
```PowerShell
(Invoke-WebRequest 'https://www.exploit-db.com/google-hacking-database/').AllElements | %{$_.href | Select-String https://www.exploit-db.com/ghdb/} | %{
((Invoke-WebRequest $_.tostring()).AllElements | Where class -eq “w-pagehead”).outerText
}

```
