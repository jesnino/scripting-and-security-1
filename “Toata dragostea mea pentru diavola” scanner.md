# “Toata dragostea mea pentru diavola” scanner
## Logs, Security, Servers 
### URL: https://www.jesusninoc.com/2009/05/03/toata-dragostea-mea-pentru-diavola-scanners/
```PowerShell
/bin/msgimport;3
/cube/bin/msgimport;3
/mail/bin/msgimport;3
/mail2/bin/msgimport;3
/mss2/bin/msgimport;3
/rc/bin/msgimport;2
/rms/bin/msgimport;3
/round/bin/msgimport;3
/roundcube-0.1/bin/msgimport;2
/roundcube-0.2/bin/msgimport;3
/roundcube/bin/msgimport;4
/roundcubemail-0.1/bin/msgimport;3
/roundcubemail-0.2/bin/msgimport;2
/roundcubemail/bin/msgimport;3
/webmail/bin/msgimport;3
/webmail2/bin/msgimport;3
/wm/bin/msgimport;3

```
```PowerShell
SELECT    cs-uri-stem,count(*)
FROM        'C:\Logfiles\W3SVC1\*.*'
where  cs(User-Agent) like '%Toata%'
group by cs-uri-stem
order by cs-uri-stem

```
