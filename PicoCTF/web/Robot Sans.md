### Descripción 
The flag is somewhere on this web application not necessarily on the website. Find it. Check [this](http://saturn.picoctf.net:52663/) out.
### Solución
Después de investigar el código, podemos entrar al archivo robots.txt, donde hay varias lineas raras:
```
ZmxhZzEudHh0;anMvbXlmaW
anMvbXlmaWxlLnR4dA==
svssshjweuiwl;oiho.bsvdaslejg
```
Podemos decodificar cada una y en la linea de anMvbXlmaWxlLnR4dA== nos da lo siguiente:
```
┌──(Peche㉿Kali)-[~]
└─$ echo "anMvbXlmaWxlLnR4dA==" | base64 -d                                          
js/myfile.txt                    
```
Que es una ruta a la que podemos ingresar, al ingresar podemos ver ahi la flag
```
http://saturn.picoctf.net:52663/js/myfile.txt

Flag: picoCTF{Who_D03sN7_L1k5_90B0T5_032f1c2b}
```