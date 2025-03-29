
### Description
Check the admin scratchpad! `https://jupiter.challenges.picoctf.org/problem/61864/` or http://jupiter.challenges.picoctf.org:61864

### Solution
Entramos y tratarnos de meternos con admin, pero no nos deja, nos dice que tenemos que ser especiales, por lo que mejor nos logueamos con Carlos, y vemos que da un token
![[Pasted image 20250329155613.png]]
Lo analizamos con JWT.io y nos da la siguiente informacion
![[Pasted image 20250329155907.png]]
Tratamos de cambiar solo el nombre a admin, pero no funciono, por lo que vemos que en la pagina principal del reto menciona sobre algo de john, por lo que lo tratamos de crakear con rockyou, para poder obtener la otra parte que nos falta que es la parte de la firma

```bash
❯ john jwt --wordlist=/usr/share/wordlists/rockyou.txt
Using default input encoding: UTF-8
Loaded 1 password hash (HMAC-SHA256 [password is key, SHA256 256/256 AVX2 8x])
Will run 12 OpenMP threads
Press 'q' or Ctrl-C to abort, almost any other key for status
ilovepico        (?)     
1g 0:00:00:01 DONE (2025-03-29 15:48) 0.7936g/s 5870Kp/s 5870Kc/s 5870KC/s iluve.p..ilovemymother@
Use the "--show" option to display all of the cracked passwords reliably
Session completed. 
```

Por lo que obtenemos la palabra con la forma que se firmo y ahora lo firmamos
![[Pasted image 20250329160300.png]]
Ahora lo cambiamos
![[Pasted image 20250329160423.png]]
y refrescamos la pagina
![[Pasted image 20250329160558.png]]