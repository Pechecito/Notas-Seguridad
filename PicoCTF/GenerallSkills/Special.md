### Descripcion
Don't power users get tired of making spelling mistakes in the shell? Not anymore! Enter Special, the Spell Checked Interface for Affecting Linux. Now, every word is properly spelled and capitalized... automatically and behind-the-scenes! Be the first to test Special in beta, and feel free to tell us all about how Special streamlines every development process that you face. When your co-workers see your amazing shell interface, just tell them: That's Special (TM)Start your instance to see connection details.

`ssh -p 59279 ctf-player@saturn.picoctf.net`The password is `fd7746b4`

### Solucion
Estuve probando varias cosas, y la verdad nada funciono, y decidi buscar en google lo siguiente

![[Pasted image 20250401180718.png]]
en la parte de
http://trajano.us.es/~fjfj/shell/doc/shellscript34.html#expansion-de-parametros-y-variables
encontre como podria concatenar un comando como una variable y podre varias cosas, hasta que con 

```bash
Special$ ${ola=ls}
${ola=ls} 
blargh
```
Me dio un resultado diferente, y despues le trate de hacer un ls a blargh de la misma manera
```bash
Special$ ${ola=ls blargh}
${ola=ls blargh} 
flag.txt
```
Ahora dije pues care un cat a blargh/flag.txt y funciono
```bash
Special$ ${ola=cat blargh/flag.txt}
${ola=cat blargh/flag.txt} 
picoCTF{5p311ch3ck_15_7h3_w0r57_f578af59}
```
### Tags
#shell 
