### Descripcion
How to automate tasks to run at intervals on linux servers?Use ssh to connect to this server:

```
Server: saturn.picoctf.net
Port: 53825
Username: picoplayer 
Password: 5wf1w1hVxt
```

### Solucion
Como nos dice algo sobre las tareas que se ejecutan automáticamente, y el nombre dice chrono, pues buscamos como enumerar las tareas cron, que son las tareas que en linux, estan como programadas
Encontramos que en ubuntu se listan en /etc/crontab, por lo que procedi a hacerle un cat
```bash
picoplayer@challenge:~$ cat /etc/crontab 
# picoCTF{Sch3DUL7NG_T45K3_L1NUX_9d5cb744}
```

### Tags
#cron #crontab