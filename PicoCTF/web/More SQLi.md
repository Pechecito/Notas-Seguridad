### Description
Can you find the flag on this website.Try to find the flag [here](http://saturn.picoctf.net:62763/).
### Solution
Primero vemos que puede haber una SQLI
![[Pasted image 20250329152128.png]]
Vemos que esto lanza un error y que primero valida la contraseña, entonces verificamos 
![[Pasted image 20250329152203.png]]
Probamos con un payload sencillo y nos da el acceso 
![[Pasted image 20250329152347.png]]
Ahora tenemos que probar el campo que hay para buscar, ya que sabemos que es vulnerable a sqli, hay que probar payloads basicos en el campo
![[Pasted image 20250329152607.png]]
entonces vemos que si da resultado

ahora en https://github.com/swisskyrepo/PayloadsAllTheThings/blob/master/SQL%20Injection/SQLite%20Injection.md#sqlite-enumeration
buscamos payloads para sacar
![[Pasted image 20250329152809.png]]

Probamos estos dos, en alguno de los campos
![[Pasted image 20250329152836.png]]
Verificamos que hay una tabla que contiene tabla como columna, por lo que tendremos que volcar esta informacion
Con el siguiente comando, sacamos la info que guarda en la tabla
```sql
' UNION ALL SELECT 1,id,flag from more_table-- 
```
![[Pasted image 20250329153459.png]]

Y nos da la flag