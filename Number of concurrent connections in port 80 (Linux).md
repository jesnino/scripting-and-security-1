# Number of concurrent connections in port 80 (Linux)
## Bash, Network 
### URL: https://www.jesusninoc.com/2014/12/03/number-of-concurrent-connections-in-port-80/
```Shell
date;netstat -ant | grep ":80" | wc -l

```
