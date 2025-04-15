### Descripcion
Can you win in a convincing manner against this chess bot? He won't go easy on you!You can find the challenge [here](http://verbal-sleep.picoctf.net:51112/).
### Solucion
De los retos mas raros jajajajaj
La verdad al estarlo haciendo durante la competencia, dure como unos dos dias estancado aqui, buscando cosas que me pudieran servir para esto, probe demasiadas cosas, que al final fue algo facilisimo

De entrada, quise ganarle por otros lados, le di mate por varios lados, y no se hacia, ya que mis movimientos solo se hacian en el front, por lo que en el backend o websocket, pues no los verificaba, asi que trate de enviarle cosas al websocket a traves de una consola del navegador.

Analizamos este script haciendo un control U
```javascript

|<script>|
||var ws_address = "ws://" + location.hostname + ":" + location.port + "/ws/";|
||const ws = new WebSocket(ws_address);|
|||
||ws.onmessage = (event) => {|
||const message = event.data;|
||updateChat(message);|
||};|
|||
||function sendMessage(message) {|
||ws.send(message);|
||}|
|||
||function updateChat(message) {|
||const chatText = $("#chatText");|
||chatText.text(message);|
||}|
||</script>|
|||
```
Esto era el cmomo se comunicaria con el websocket, pero mas abajo, habia una funcion que llamaba la atencion 
```javascript
|stockfish.onmessage = function (event) {|
||var message;|
||// console.log(event.data);|
||if (event.data.startsWith("bestmove")) {|
||var bestMove = event.data.split(" ")[1];|
||var srcSq = bestMove.slice(0, 2);|
||var dstSq = bestMove.slice(2, 4);|
||var promotion = bestMove.slice(4);|
|||
||game.move({ from: srcSq, to: dstSq, promotion: promotion });|
||board.position(game.fen());|
||} else if (event.data.startsWith(`info depth ${DEPTH}`)) {|
||var splitString = event.data.split(" ");|
||if (event.data.includes("mate")) {|
||message = "mate " + parseInt(splitString[9]);|
||} else {|
||message = "eval " + parseInt(splitString[9]);|
||}|
||sendMessage(message);|
||}|
||};|
```
ahi hacia la validacion de los movimientos
Entonces procedi a enviarle comandos 
```js
ws.send("mate 4");
undefined
ws.send("eval 99");
undefined
ws.send("eval -99");
undefined
ws.send("eval 9999");
undefined
ws.send("eval -9999");
undefined
ws.send("eval -99999999");
undefined
```
Fue prueba y error a partir de las funciones que utilizaba en la función
Y hasta en el ultmimo Eval 
![[Pasted image 20250415144015.png]]

### Tags
#websockets
