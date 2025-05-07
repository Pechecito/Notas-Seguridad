### Descripcion
Find the flag being held on this server to get ahead of the competition [http://mercury.picoctf.net:15931/](http://mercury.picoctf.net:15931/)
### Solucion
Hacer un curl a la página y usar la opción -I para que nos muestre los headers de la página y ahi ver la flag
```js
❯ curl -I http://mercury.picoctf.net:15931
HTTP/1.1 200 OK
flag: picoCTF{r3j3ct_th3_du4l1ty_82880908}
Content-type: text/html; charset=UTF-8
```
### Tags
