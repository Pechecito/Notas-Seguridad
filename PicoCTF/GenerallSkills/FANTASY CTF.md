Play this short game to get familiar with terminal applications and some of the most important rules in scope for picoCTF. Connect to the program with netcat: `$ nc verbal-sleep.picoctf.net 61243`

Hints:
	When a choice is presented like [a/b/c], choose one, for example: `c` and then press Enter.

# Solución
Jugamos el juego, eligiendo primero la opción C de registrar solo una cuenta, despues A para jugar, seguimos dando enter y se muestra la flag:
```
"Thanks, Nyx! Here's the flag I found: picoCTF{m1113n1um_3d1710n_8dcbda00}"
```