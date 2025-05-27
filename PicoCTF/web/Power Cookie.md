### Descripción 
Can you get the flag? Go to this [website](http://saturn.picoctf.net:58440/) and see what you can discover.
### Solución
Al entrar al sitio y entrar como invitado vemos que existe una cookie de nombre isAdmin con un valor de 0
Por lo que la solución es entrar al inspeccionar la página y cambiar el valor de la cookie de 0 a 1
Sin utilizar cookie editor porque no funciona de esa manera
```
Flag: picoCTF{gr4d3_A_c00k13_0d351e23}
```