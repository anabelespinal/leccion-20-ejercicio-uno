*****
#  EJERCICIO UNO-LECCIÒN 20:  
###   Tenemos el siguiente codigo:



####  Modificar el sprit usanso closures para que se ejecute sin problemas:

![Sin titulo](http://i66.tinypic.com/dw3v2f.jpg)



+ La var num2 = 0; es una scope global.
+ En la function suma se llama a esta variable, sin darle otro valor, por lo cual cogera el valore del scope global.
+ Dentro de la function suma se retorna una funnction anonima con un parametro "num2".
  dentro de esta function anonima tambien se retorna un aoperacion que es de "num1"(este es el parametro de la function suma) + "num2"(que aun tiene el valor asignado en el scope global).
+ Fuera de la funciones se se crea una var global "suma2" que tiene el valor de "suma(2)"(este '2'     representa al parametro "num1", ahora con un valor de 2).
+ luego se llama con un console.log para verificar el resultado: "(suma2(5))", el cual deberá         mostrar como resultado "7".
+ Este codigo no ejecutará porque num2 esta siendo declarada en scope global, y al llamarlo en la     consola el "(5)" que esta reemplazando a num2, no ejecutara este valor ya que el valor de num2 es   de "0".
+ Lo mismo sucede con el var "suma12".

****

#### Ahora debemos modificar el codigo para que la consola de las repuestas correctas. El codigo corregido es el siguiente.

```javascript   


function suma(num1) {
    return function(num2){
        return num1 + num2;
    }
}

var suma2 = suma(2);
console.log(suma2(5));

var suma12 = suma(12);
console.log(suma12(76));

```
+  Para corregir estos problemas, que principalmente es la variable num2, empezaremos por
   eliminar esta variable.
+  Se borra esta variable ya que es de scope global, y sabemos que si queremos llamar a una variable    global dentro de una function su valor inicial(la del scope global) podra ser modificado, pero su    valor nuevo solo 'servira' dentro de esta function, y si queremos llamarla después (fuera de la      function donde se le v¿cambio el valor) este dará como valor el que se le dio en scope global.
+  Tambien hay otro problema, ya que cuando se llama a las variables que tienen como valor las          funciones anteriores en la consola como: "(suma2(5))", 'suma2' sera igual a la function con 			 parametro (2), pero se le da un parametro que representa a '5'.
+  Para solucionar este problema se elimina la variable "num2", y se le convierte en parametro de la    function anonima.
+  Al llamarlo en la consola cambiara los parametros que son num1(que en el primer caso vale 2) y      num2 (que en la llamada toma como valor 5).
+  De esta forma se ejecutara la operacion de la function suma.
+  Y al llamarlo en la consola este mostrara el resultado correcto en ambos casos.

****













