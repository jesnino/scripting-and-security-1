# Find number of active connections in Linux
## Bash, Network 
### URL: https://www.jesusninoc.com/2014/12/26/find-number-active-connections-linux/
```Shell
netstat -ntu | awk ' $5 ~ /^[0-9]/ {print $5}' | cut -d: -f1 | sort | uniq -c | sort -n

```
