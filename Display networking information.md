# Display networking information
## Android, Network 
### URL: https://www.jesusninoc.com/2016/04/16/display-networking-information/
```PowerShell
adb shell netcfg
adb shell netcfg | grep wlan0

adb shell ls /sys/class/net

adb shell dumpsys netstats

adb shell ip link
adb shell ip address
adb shell ip addrlabel
adb shell ip neighbour
adb shell ip route
adb shell ip rule
adb shell ip maddress
adb shell ip mroute
adb shell ip tunnel
adb shell ip xfrm state

adb shell ifconfig

adb shell netstat
adb shell netstat -n
adb shell netstat -anp
adb shell netstat -p
adb shell netstat -a

```
