### Descripción  
Can you get the flag? Go to this [website](http://saturn.picoctf.net:63258/) and see what you can discover.
### Solución
Entrar a ver el código HTML de la página. Ahí para el formulario llama a un archivo llamado login.php, entramos a este y vemos que tiene un archivo Javascript donde podemos ver las credenciales del admin con las que podemos ingresar
```
function checkPassword(username, password)
{
  if( username === 'admin' && password === 'strongPassword098765' )
  {
    return true;
  }
  else
  {
    return false;
  }
}
```
Con esto ingresamos las credenciales y vemos la flag en el sitio web
```
picoCTF{j5_15_7r4n5p4r3n7_05df90c8}
```