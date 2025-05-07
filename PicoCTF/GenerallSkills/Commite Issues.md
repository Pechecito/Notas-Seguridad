### Descripcion
I accidentally wrote the flag down. Good thing I deleted it!You download the challenge files here:
- [challenge.zip](https://artifacts.picoctf.net/c_titan/75/challenge.zip)
### Solucion
Ya que descargue el repositorio en .zip, empece a usmear con los comanditos que se mencionan abajo
```bash
❯ unzip challenge.zip
❯ ls
 message.txt
❯ cat message.txt
───────┬──────────────────────────────────────────────────────────────────────
       │ File: message.txt
───────┼──────────────────────────────────────────────────────────────────────
   1   │ TOP SECRET
❯ ls -la
drwxr-xr-x peche peche 4.0 KB Sat Mar  9 15:09:58 2024  .
drwxrwxr-x peche peche 4.0 KB Tue Apr  1 18:17:15 2025  ..
drwxr-xr-x peche peche 4.0 KB Sat Mar  9 15:09:58 2024  .git
.rw-r--r-- peche peche  11 B  Sat Mar  9 15:09:58 2024  message.txt

❯ grep -r "pico" ./
./logs/refs/heads/master:0000000000000000000000000000000000000000 6603cb4ff0c4ea293798c03a32e0d78d5ab12ca2 picoCTF <ops@picoctf.com> 1710018598 +0000	commit (initial): create flag
./logs/refs/heads/master:6603cb4ff0c4ea293798c03a32e0d78d5ab12ca2 3899edb7f3110d613c72ad40083fd8feeef703d0 picoCTF <ops@picoctf.com> 1710018598 +0000	commit: remove sensitive info
./logs/HEAD:0000000000000000000000000000000000000000 6603cb4ff0c4ea293798c03a32e0d78d5ab12ca2 picoCTF <ops@picoctf.com> 1710018598 +0000	commit (initial): create flag
./logs/HEAD:6603cb4ff0c4ea293798c03a32e0d78d5ab12ca2 3899edb7f3110d613c72ad40083fd8feeef703d0 picoCTF <ops@picoctf.com> 1710018598 +0000	commit: remove sensitive info
❯ cd logs
❯ ls
 refs   HEAD
❯ cat HEAD
───────┬──────────────────────────────────────────────────────────────────────
       │ File: HEAD
───────┼──────────────────────────────────────────────────────────────────────
   1   │ 0000000000000000000000000000000000000000 6603cb4ff0c4ea293798c03a32e0
       │ d78d5ab12ca2 picoCTF <ops@picoctf.com> 1710018598 +0000    commit (in
       │ itial): create flag
   2   │ 6603cb4ff0c4ea293798c03a32e0d78d5ab12ca2 3899edb7f3110d613c72ad40083f
       │ d8feeef703d0 picoCTF <ops@picoctf.com> 1710018598 +0000    commit: re
       │ move sensitive info
```

Encontre el id del commit donde se hizo la creacion de la flag, entonces lo que tenia que hacer, era volver a recuperar el archivo, por lo que me fue a la raiz de la carpeta e inicie el repositorio 
 ```bash
 ❯ git init
Reinicializado el repositorio Git existente en /home/peche/picoctf/generalSkills/CommitmentIsues/drop-in/.git/
 ```
 y como decia en el picopremier, para poder recupearar un archivo se hace un checkout
 ``` bash
 ❯ git checkout 6603cb4ff0c4ea293798c03a32e0d78d5ab12ca2
Nota: cambiando a '6603cb4ff0c4ea293798c03a32e0d78d5ab12ca2'.

Te encuentras en estado 'detached HEAD'. Puedes revisar por aquí, hacer
cambios experimentales y hacer commits, y puedes descartar cualquier
commit que hayas hecho en este estado sin impactar a tu rama realizando
otro checkout.

Si quieres crear una nueva rama para mantener los commits que has creado,
puedes hacerlo (ahora o después) usando -c con el comando checkout. Ejemplo:

  git switch -c <nombre-de-nueva-rama>

O deshacer la operación con:

  git switch -

Desactiva este aviso poniendo la variable de config advice.detachedHead en false

HEAD está ahora en 6603cb4 create flag
❯ ls
 message.txt
❯ cat message.txt
───────┬───────────────────────────────────────────────────────────────────────────────────────────────
       │ File: message.txt
───────┼───────────────────────────────────────────────────────────────────────────────────────────────
   1   │ picoCTF{s@n1t1z3_9539be6b}
 ```
### Tags
#git