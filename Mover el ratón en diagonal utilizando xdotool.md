# Mover el ratón en diagonal utilizando xdotool
## Bash 
### URL: https://www.jesusninoc.com/2016/03/20/mover-el-raton-en-diagonal-utilizando-xdotool/
```Shell
x=0;y=0;while [[ $y -lt 600 ]] ; do xdotool mousemove $x $y ; x=$(($x+1));y=$(($y+1)); echo $x $y; sleep 0.001; done

```
