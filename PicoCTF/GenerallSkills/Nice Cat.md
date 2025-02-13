### Description

There is a nice program that you can talk to by using this command in a shell: `$ nc mercury.picoctf.net 35652`, but it doesn't speak English...

## Hints

1-. You can practice using netcat with this picoGym problem: [what's a netcat?](https://play.picoctf.org/practice/challenge/34)

You can practice reading and writing ASCII with this picoGym problem: [Let's Warm Up](https://play.picoctf.org/practice/challenge/22)

## Solution
```bash
PecheZ-picoctf@webshell:~/retos$ nc mercury.picoctf.net 35652 > hola.txt

PecheZ-picoctf@webshell:~/retos$ vi hola.py
PecheZ-picoctf@webshell:~/retos$ python hola.py 
picoCTF{g00d_k1tty!_n1c3_k1tty!_9b3b7392}

```

```python
#Este es el codigo de hola.py
texto = ""
with open('hola.txt', 'r') as f:
    for linea in f:
        texto += chr(int(linea.strip()))
print(texto)
```

