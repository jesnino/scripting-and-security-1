# Permisos en Linux
## Bash, Filesystem, Permissions 
### URL: https://www.jesusninoc.com/2016/02/21/permisos-en-linux/
```Shell
kali@kali:~/carpeta$ mkdir carpeta1
kali@kali:~/carpeta$ touch fichero
kali@kali:~/carpeta$ ls -la
total 12
drwxr-xr-x  3 kali kali 4096 feb 17 05:59 .
drwxr-xr-x 17 kali kali 4096 feb 17 05:59 ..
drwxr-xr-x  2 kali kali 4096 feb 17 05:59 carpeta1
-rw-r--r--  1 kali kali    0 feb 17 05:59 fichero
kali@kali:~/carpeta$ chmod ugo=rwx fichero
kali@kali:~/carpeta$ ls -l fichero
-rwxrwxrwx 1 kali kali 0 feb 17 05:59 fichero
kali@kali:~/carpeta$ chmod g-x fichero
kali@kali:~/carpeta$ ls -l fichero
-rwxrw-rwx 1 kali kali 0 feb 17 05:59 fichero
kali@kali:~/carpeta$ chgrp root fichero
chgrp: cambiando el grupo de «fichero»: Operación no permitida
kali@kali:~/carpeta$ sudo chgrp root fichero
[sudo] password for kali:
kali@kali:~/carpeta$ ls -l fichero
-rwxrw-rwx 1 kali root 0 feb 17 05:59 fichero
kali@kali:~/carpeta$ chown root fichero
chown: cambiando el propietario de «fichero»: Operación no permitida
kali@kali:~/carpeta$ sudo chown root fichero

```
```Shell
kali@kali:~$ sudo ls -la carpeta/
total 12
d---------  3 kali kali 4096 feb 17 05:59 .
drwxr-xr-x 17 kali kali 4096 feb 17 05:59 ..
drwxr-xr-x  2 kali kali 4096 feb 17 05:59 carpeta1
-rwxrw-rwx  1 root root    0 feb 17 05:59 fichero
kali@kali:~$ sudo chgrp -R root carpeta/
kali@kali:~$ sudo ls -la carpeta/
total 12
d---------  3 kali root 4096 feb 17 05:59 .
drwxr-xr-x 17 kali kali 4096 feb 17 05:59 ..
drwxr-xr-x  2 kali root 4096 feb 17 05:59 carpeta1
-rwxrw-rwx  1 root root    0 feb 17 05:59 fichero
kali@kali:~$ sudo chown -R root carpeta/
kali@kali:~$ sudo ls -la carpeta/
total 12
d---------  3 root root 4096 feb 17 05:59 .
drwxr-xr-x 17 kali kali 4096 feb 17 05:59 ..
drwxr-xr-x  2 root root 4096 feb 17 05:59 carpeta1
-rwxrw-rwx  1 root root    0 feb 17 05:59 fichero

```
```Shell
kali@kali:~$ mkdir carpeta
kali@kali:~$ cd carpeta/
kali@kali:~/carpeta$ ls -la
total 8
drwxr-xr-x  2 kali kali 4096 feb 17 06:17 .
drwxr-xr-x 17 kali kali 4096 feb 17 06:17 ..
kali@kali:~/carpeta$ umask
0022
kali@kali:~/carpeta$ umask 0077
kali@kali:~/carpeta$ touch fichero
kali@kali:~/carpeta$ ls -la fichero
-rw------- 1 kali kali 0 feb 17 06:18 fichero
kali@kali:~/carpeta$ umask 0022
kali@kali:~/carpeta$ touch fichero2
kali@kali:~/carpeta$ ls -la fichero2
-rw-r--r-- 1 kali kali 0 feb 17 06:18 fichero2

```
