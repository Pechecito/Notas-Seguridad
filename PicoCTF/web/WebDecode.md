### Descripción 
Do you know how to use the web inspector? Start searching [here](http://titan.picoctf.net:62861/) to find the flag
### Solución
Entramos al código de la página y vemos que hay diferentes interfaces que visitar. En el código de la página de About podemos ver un código encodeado:
```
<section class="about" notify_true="cGljb0NURnt3ZWJfc3VjYzNzc2Z1bGx5X2QzYzBkZWRfMTBmOTM3NmZ9">
```
Podemos usar la herramienta de cyberchef para descifrarla con base 64
```
Input: cGljb0NURnt3ZWJfc3VjYzNzc2Z1bGx5X2QzYzBkZWRfMTBmOTM3NmZ9

Recipe: From Base64

Output: picoCTF{web_succ3ssfully_d3c0ded_10f9376f}
```
O podemos usar la terminal con:
```
┌──(Peche㉿Kali)-[~]
└─$ echo "cGljb0NURnt3ZWJfc3VjYzNzc2Z1bGx5X2QzYzBkZWRfMTBmOTM3NmZ9" | base64 --decode
picoCTF{web_succ3ssfully_d3c0ded_10f9376f}   
```
