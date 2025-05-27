### Descripción 
We have several pages hidden. Can you find the one with the flag? The website is running [here](http://saturn.picoctf.net:55572/).
### Solución
Al ver el código de la página principal, podemos ver que un archivo css se encuentra en una carpeta secret
```
http://saturn.picoctf.net:55572/secret/
```
Despues en el codigo de esa ruta podemos ver otra carpeta hidden
```
http://saturn.picoctf.net:55572/secret/hidden/
```
Despues ahi podemos ver la carpeta superhidden
```
http://saturn.picoctf.net:55572/secret/hidden/superhidden
```
Donde finalmente podemos ver la flag
```
    <h3 class="flag">picoCTF{succ3ss_@h3n1c@10n_39849bcf}</h3>
```