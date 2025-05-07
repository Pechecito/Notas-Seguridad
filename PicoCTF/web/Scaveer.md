### Descripcion
There is some interesting information hidden around this site http://mercury.picoctf.net:55079/. Can you find it?
### Solucion
Primero analizar el código de la página para ver la primera parte de la flag en el HTML
```
<!-- Here's the first part of the flag: picoCTF{t -->
```
Después ir a la hoja de estilos
```
/* CSS makes the page look nice, and yes, it also has part of the flag. Here's part 2: h4ts_4_l0 */
```
Después tenemos la pista de indexación por parte de google y checamos el robots.txt para encontrar la tercera parte de la flag
```
User-agent: *
Disallow: /index.html
# Part 3: t_0f_pl4c
# I think this is an apache server... can you Access the next flag?
```
Después vemos el archivo de .htaccess ya que es un servidor apache para ver la cuarta parte de la flag
```
# Part 4: 3s_2_lO0k
# I love making websites on my Mac, I can Store a lot of information there.
```
Finalmente nos dice que es de una Mac, por lo que buscamos el archivo de .DS_Store para ver la parte final de la flag
```
Congrats! You completed the scavenger hunt. Part 5: _7a46d25d}
```
Flag:
picoCTF{th4ts_4_l0t_0f_pl4c3s_2_lO0k_7a46d25d}
### Tags
