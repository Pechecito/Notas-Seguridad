Decrypt this [message](https://jupiter.challenges.picoctf.org/static/7d707a443e95054dc4cf30b1d9522ef0/ciphertext).

# Solucion
Tenemos un mensaje que se tiene que decifrar por el algoritmo cesar, que funciona relacionando el abecedario con este mismo pero desplazado n numero de posiciones
```
mensaje: picoCTF{gvswwmrkxlivyfmgsrhnrisegl} 
```
Podemos usar cyberchef para intentar descifrarlo, usando ROT13 que rota el mensaje para descifrar
```
Input: ynkooejcpdanqxeykjrbdofgkq

Recipe: ROT13 - 30 rotaciones

Output: picoCTF{crossingtherubiconvfhsjkou}
```