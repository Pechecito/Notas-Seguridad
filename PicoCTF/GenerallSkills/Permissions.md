### Descripción
Can you read files in the root file?The system admin has provisioned an account for you on the main server:`ssh -p 55487 picoplayer@saturn.picoctf.net`Password: `j4ks-9nxB-`Can you login and read the root file?

### Solución
se ejecuto un 
```bash
sudo -l
``` 
que muestra los permisos que tengo para ejecutar, en este caso aparecio vi
ahora nos fuimos a gftoBins
https://gtfobins.github.io/gtfobins/vi/#shell

Y aqui nos daba el como podiamos leer archivos

Al ejecutar 
```bash
sudo vi /root
``` 
Nos apareció los archivos y ya podía navegar por los archivos existentes de la capeta indicada, ahí estaba la flag, solo se le dio enter y me daba la flaggg