### Descripción 
Matryoshka dolls are a set of wooden dolls of decreasing size placed one inside another. What's the final one? Image: [this](https://mercury.picoctf.net/static/b6205dd933ec01c022c4e6acbdf11116/dolls.jpg)

### Solucion
Primero usar un unzip a la imagen y pasa lo siguiente y se crea una carpeta con otra imagen
```
┌──(Peche㉿Kali)-[~/pico/forensic3/matryoshka]
└─$ unzip dolls.jpg 
Archive:  dolls.jpg
warning [dolls.jpg]:  272492 extra bytes at beginning or within zipfile
  (attempting to process anyway)
  inflating: base_images/2_c.jpg     
```
Seguir asi con los unzip hasta conseguir una mas pequeña y conseguir la flag
```
┌──(Peche㉿Kali)-[~/…/matryoshka/base_images/base_images/base_images]
└─$ cat flag.txt      
picoCTF{4f11048e83ffc7d342a15bd2309b47de}  
```

### Tags