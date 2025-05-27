The Network Operations Center (NOC) of your local institution picked up a suspicious file, they're getting conflicting information on what type of file it is. They've brought you in as an external expert to examine the file. Can you extract all the information from this strange file? Download the suspicious file [here](https://artifacts.picoctf.net/c_titan/96/flag2of2-final.pdf).
# Solucion
Descargamos el pdf y lo abrimos y vemos una cadena
```
picoCTF{f1u3n7_1n_pn9_&_pdf_1f991f77}
```
Ya que tenemos el archivo podemos usar el comando de convert para convertir el archivo pdf en una imagen png u poder ver otra cadena
```
┌──(Peche㉿Kali)-[~/pico/Tarea3Forensic/SecretOfThePolyglot]
└─$ convert flag2of2-final.pdf imagen.png 
                                                                                                                                                                  
┌──(Peche㉿Kali)-[~/pico/Tarea3Forensic/SecretOfThePolyglot]
└─$ ls
flag2of2-final.pdf  imagen.png
                                                                                                                                                                  
┌──(Peche㉿Kali)-[~/pico/Tarea3Forensic/SecretOfThePolyglot]
└─$ open imagen.png       
```
Ahi en esa imagen vemos la primera parte de la flag
```
picoCTF{f1u3n71n_pn9_&_pdf_1f991f77}}
```
Entonces despues podemos juntar las 2
```
picoCTF{f1u3n7_1n_pn9_&_pdf_1f991f77}}
```