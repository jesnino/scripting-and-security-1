# Crear una tarea programada que se ejecute una vez al día y a una hora en concreto
## Schedule tasks 
### URL: https://www.jesusninoc.com/2016/06/03/crear-una-tarea-programada-que-se-ejecute-una-vez-al-dia-y-a-una-hora-en-concreto/
```PowerShell
schtasks /create /tn "NC" /tr F:\power\nc.exe /sc daily /st 08:00:00

```
