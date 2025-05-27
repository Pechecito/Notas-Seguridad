### Descripción 
Try [here](http://titan.picoctf.net:51037/) to find the flag
### Solución
Utilizamos BurpSuite para interceptar los paquetes que se mandan, de esta manera podemos interceptar los datos que se mandan al llenar el formulario con los datos y de llenar la casilla para el OTP.
De esta manera podemos modificar los datos de manera que eliminemos la necesidad del OTP en la vista donde pide este código único.
Así accediendo y obteniendo la flag una vez adentro
```
Welcome, Gomez you sucessfully bypassed the OTP request. Your Flag: picoCTF{#0TP_Bypvss_SuCc3$S_2e80f1fd}
```