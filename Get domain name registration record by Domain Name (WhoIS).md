# Get domain name registration record by Domain Name (WhoIS)
## PowerShell, Servers, Web Service 
### URL: https://www.jesusninoc.com/2016/02/10/get-domain-name-registration-record-by-domain-name-whois/
```PowerShell
$whois=New-WebServiceProxy -uri "https://www.webservicex.net/whois.asmx?WSDL"
$whois.GetWhoIS('www.google.com')

```
