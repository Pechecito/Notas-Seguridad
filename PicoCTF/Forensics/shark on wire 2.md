### Descripcion
We found this [packet capture](https://jupiter.challenges.picoctf.org/static/b506393b6f9d53b94011df000c534759/capture.pcap). Recover the flag that was pilfered from the network.
### Solucion
Se tenia que analizar los paquetes UDP, ahi habia algunos paquetes que contenian las palabras end y start, el de end provenia de la ip "10.0.0.66" por lo que filtre por todos los paquetes que provenian desde esa ip
Vi que todos tenian en comun, que iban desde un puerto 5000 a un 22 es decir habia desde 5102, 5099 y mas. Si poniamos atencion el primero era el 5000, despues el 5112, en la cual se vio que el 112 en assci era la p, y si le seguiamos consecutivamente, decia pico y luego la bandera, por lo que hice un scrip en pytohn que me ayudara a obtener esto.
Sinceramente fue raro encontrarlo, no tiene nada que ver con wireshark, tienes que ser observador a mi parecer.
```python
# Ruta a tu archivo .cap
cap = pyshark.FileCapture('capture.pcap')

# IP que quieres filtrar
ip_origen = '10.0.0.66'

print(f"Analizando paquetes desde {ip_origen}...\n")

for pkt in cap:
    # Verificamos que tenga capa IP
    if 'IP' in pkt:
        try:
            if pkt.ip.src == ip_origen:
                puerto_origen = pkt[pkt.transport_layer].srcport
                puerto_origen = puerto_origen[1:]
                letra = chr(int(puerto_origen))
                print(letra, end="")
        except AttributeError:
            # Paquete sin capa de transporte (ej. ICMP), lo ignoramos
            continue


```
### Tags
#esteganografia 