### Descripcion
Can you break into this super secure portal? `https://jupiter.challenges.picoctf.org/problem/6353/` ([link](https://jupiter.challenges.picoctf.org/problem/6353/)) or http://jupiter.challenges.picoctf.org:6353
### Solucion
Hice un Ctrl U, e inspeccione el codigo de la pagina, ahi estaba la funcio, con la que se  verificaba la password, y estaba ofuscada, por lo que la deofusque paso a paso, para poder armar la contraseña que era la bandera, y funciono
```js
< script type = "text/javascript" > //Recordar que cuando un hexa empiece con un _ es una variable, si no lo tiene, el lenguaje lo intepreta como numero
  var diccionarioPrimario = ['0a029}', '_again_5', 'this', 'Password\x20Verified', 'Incorrect\x20password', 'getElementById', 'value', 'substring', 'picoCTF{', 'not_this'];
(function (diccionarioARotar, numeroDeRotaciones) { //FuncionAutoejecutable
  var funcionRotaciones = function (ContadorRotaciones) {
    while (--ContadorRotaciones) {
      diccionarioARotar['push'](diccionarioARotar['shift']()); //Este primero hace el shift, que extrae el primer elemento y lo saca del array
    }                               //y despues se ejecuta el push, que es meter un elemento al final, enotnces, solo cambia el primero por el ultimo
  };        //Esto lo hace hasta que el contador llegue a 0, disminuyendo un
  funcionRotaciones(++numeroDeRotaciones);
}(diccionarioPrimario, 0x1b3)); //Aqui Cierras la funcion autoejecutable

var   = function (posicionDelArregloAObtener) {
  posicionDelArregloAObtener = posicionDelArregloAObtener -  0;
  var valorDeDiccionarioObtenido = diccionarioPrimario[posicionDelArregloAObtener];
  return valorDeDiccionarioObtenido;
};

//Arreglo Rotado
// ['getElementById', 'value', 'substring', 'picoCTF{', 'not_this', '0a029}', '_again_5', 'this', 'Password Verified', 'Incorrect password']

function verify() {
  checkpass = document[ ('getElementById')]('pass')[ ('value')];
  if (checkpass[ ('substring')](0,8) ==  ('picoCTF{')) {
    if (checkpass[ ('substring')](7,9) == '{n') {
      if (checkpass[ ('substring')](8,16) ==  ('not_this')) {
        if (checkpass[ ('substring')](3,6) == 'oCT') {
          if (checkpass[ ('substring')](24,32) ==  ('0a029')) {
            if (checkpass['substring'](6,11) == 'F{not') {
              if (checkpass[ ('substring')](16,24) ==  ('_again_5')) {
                if (checkpass[ ('substring')](12,  16) ==  ('this')) {
                  alert( ('Password Verified'));
                }
              }
            }
          }
        }
      }
    }
  } else {
    alert( ('Incorrect password'));
  }
} <
/script>

```
### Tags
#ofuscacion
