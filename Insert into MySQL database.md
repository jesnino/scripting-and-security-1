# Insert into MySQL database
## Database, PowerShell 
### URL: https://www.jesusninoc.com/2015/12/14/insert-into-mysql-database/
```PowerShell
[void][System.Reflection.Assembly]::LoadWithPartialName("MySql.Data")
$Connection = New-Object MySql.Data.MySqlClient.MySqlConnection
$ConnectionString = "server=" + "localhost" + ";port=3306;uid=" + "root" + ";pwd=" + "root" + ";database="+"world"
$Connection.ConnectionString = $ConnectionString
$Connection.Open()

$Query = 'INSERT INTO city (name,CountryCode,District,Population) VALUES ("mad","ISR","rein","10932")'
$Command = New-Object MySql.Data.MySqlClient.MySqlCommand($Query, $Connection)
$DataAdapter = New-Object MySql.Data.MySqlClient.MySqlDataAdapter($Command)
$DataSet = New-Object System.Data.DataSet
$RecordCount = $dataAdapter.Fill($dataSet, "data")
$DataSet.Tables[0]
$Connection.Close()

```
