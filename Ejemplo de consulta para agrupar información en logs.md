# Ejemplo de consulta para agrupar información en logs
## Logs, PHP, Security, Servers 
### URL: https://www.jesusninoc.com/2009/05/07/ejemplo-de-consulta-para-agrupar-informacion-en-logs/
```PowerShell
/phpmyadmin/main.php
/phpMyAdmin/main.php
/myadmin/main.php
/phpmyadmin2/main.php
/PMA/main.php
/mysql/main.php
/db/main.php

```
```PowerShell
select cs-uri-stem, count (*) as a from 'W3SVC1W3SVC1*.*' group by cs-uri-stem order by a desc

```
