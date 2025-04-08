### Descripcion
What was I last working on? I remember writing a note to help me remember...You can download the challenge files here:

- [challenge.zip](https://artifacts.picoctf.net/c_titan/68/challenge.zip)
### Solucion
Solo inicie el repo, vi lo del mensaje y lo de las hints, donde decia que seria un message en un commit, y decidi hacer un grep recursivo con pico, y ahi estaba la flag, en el mensaje de un commit
```bash
❯ git init
Reinicializado el repositorio Git existente en /home/peche/picoctf/generalSkills/TimeMachine/drop-in/.git/
❯ cd .git
❯ grep -r "pico" ./
./logs/refs/heads/master:0000000000000000000000000000000000000000 705ff639b7846418603a3272ab54536e01e3dc43 picoCTF <ops@picoctf.com> 1710018636 +0000	commit (initial): picoCTF{t1m3m@ch1n3_b476ca06}
./logs/HEAD:0000000000000000000000000000000000000000 705ff639b7846418603a3272ab54536e01e3dc43 picoCTF <ops@picoctf.com> 1710018636 +0000	commit (initial): picoCTF{t1m3m@ch1n3_b476ca06}
./COMMIT_EDITMSG:picoCTF{t1m3m@ch1n3_b476ca06}

```
### Tags
#git 
