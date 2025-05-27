Python scripts are invoked kind of like programs in the Terminal... Can you run [this Python script](https://mercury.picoctf.net/static/325a52d249be0bd3811421eacd2c877a/ende.py) using [this password](https://mercury.picoctf.net/static/325a52d249be0bd3811421eacd2c877a/pw.txt) to get [the flag](https://mercury.picoctf.net/static/325a52d249be0bd3811421eacd2c877a/flag.txt.en)?

Hints:
- Get the Python script accessible in your shell by entering the following command in the Terminal prompt: `$ wget https://mercury.picoctf.net/static/325a52d249be0bd3811421eacd2c877a/ende.py`
- $ `man python`

# Solución
Copiamos los archivos con wget a nuestro directorio de trabajo, al analizar el código python vemos que acepta las opcioens de -d y -e. Lo que queremos es decodificar la flag, por lo que hacer lo siguiente:`
```
┌──(Peche㉿Kali)-[~/pico/Parcial1GS/PythonWrangling]
└─$ python ende.py -d flag.txt.en 
Please enter the password:
```
Nos pide una contraseña por lo que pegamos lo que hay dentro del archivo pw.txt y vemos la flag
```
┌──(Peche㉿Kali)-[~/pico/Parcial1GS/PythonWrangling]
└─$ python ende.py -d flag.txt.en       
Please enter the password:ac9bd0ffac9bd0ffac9bd0ffac9bd0ff
picoCTF{4p0110_1n_7h3_h0us3_ac9bd0ff}
```