### Descripción 
We found this [packet capture](https://jupiter.challenges.picoctf.org/static/0c84d3636dd088d9fe4efd5d0d869a06/capture.pcap) and [key](https://jupiter.challenges.picoctf.org/static/0c84d3636dd088d9fe4efd5d0d869a06/picopico.key). Recover the flag.
### Solución
Primero abrir el .pcap con Wireshark y cargar la llave SSH el el protocolo TLS para desencriptar los paquetes. Despues simplemente seguir la ruta o stream HTTP de lo que se desencripto y ahi vemos la flag
```
Pico-Flag: picoCTF{nongshim.shrimp.crackers}
```
