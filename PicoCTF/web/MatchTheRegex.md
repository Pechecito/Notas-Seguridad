### Descripcion
How about trying to match a regular expressionThe website is running [here](http://saturn.picoctf.net:56510/).
### Solucion 
Inspeccionando el codigo encontramos esta funcion que valida lo que se le pasa, para ver si conincide con una expresion regular que en este caso, era que empezara con p y luego 5 caracteres y terminara con F
```java
function send_request() {
	let val = document.getElementById("name").value;
	// ^p.....F!?|
	fetch(`/flag?input=${val}`)
		.then(res => res.text())
		.then(res => {
			const res_json = JSON.parse(res);
			alert(res_json.flag)
			return false;
		})
	return false;
}
```
Vemos que si le pasamos algo como p12345F sirve
![[Pasted image 20250403122339.png]]
### Tags
#regex 
