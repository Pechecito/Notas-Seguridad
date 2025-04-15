### Descripcion
Welcome to the challenge! In this challenge, you will explore a web application and find an endpoint that exposes a file containing a hidden flag.The application is a simple blog website where you can read articles about various topics, including an article about API Documentation. Your goal is to explore the application and find the endpoint that generates files holding the server’s memory, where a secret flag is hidden.The website is running [picoCTF News](http://verbal-sleep.picoctf.net:58519/).
### Solucion
Buscamos el endpoint correcto que esta en el enlace de API Documentation en uno de los post.
Se lo agregas a la ur 
http://verbal-sleep.picoctf.net:58519/heapdum
y descaragra un archivo de una snaphost
le haces un cat 
```bash
cat heapdump-1744737812378.heapsnapshot | grep picoCTF{
```
y procede a darte la flag
### Tags
