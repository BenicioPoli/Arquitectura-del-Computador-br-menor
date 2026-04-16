# Arquitectura-del-Computador-br-menor


Me fue solicitado en el sorteo de numeros la instrucción br menor

Esta instrucción funciona de la siguiente manera se le pasan dos registros R1 y R2 y si R1 < R2 salta hacia donde le indica la constante que se le manda con la función. Por lo entendido de la clase la instrucción se forma con el Codigo de operación,R1,R2 y la constante,ocupando cada una de las partes cuatro bits.

En circuitverse realize un circuito en el cual ingresas los dos registros a traves de numeros de 4 bits y compara de la siguiente forma.

Si el bit de mayor significancia de R1 es menor que el de R2 ya esta,esto se hace negando el bit de mayor significancia de A y haciendole un and con el de B (esto debido a que si sucede el caso el bit de A seria 0 y el bit de B 1).

Luego si esto no ocurre puede ocurrir que si los dos bits de mayor significancia son iguales (esto se compara con el not xor) entonces si el segundo bit mas significativo es menor en R1 ahi ya esta ya son menores (para ver cual es menor se hace mismo procedimiento que con el de mayor significado)

Y asi con el resto de bits viendo que los de mayor significado sean iguales y en el que estoy parado sea menor.

Si sucede uno de estos casos devolvemos 1 sino 0.

Devolvemos 1 0 ya que aca nos excede totalmente adonde saltamos si bien podriamos simular la constante y que devuelva eso si es 1 en realidad no tendriamos que devolver en el caso que no se cumpla la condición ya que no disponemos de lo que seguiria en el codigo.

Lo anterior rige para la versión unsigned,la versión signed en lo unico que cambia es que en el primer bit se le hace un not para compararlo al de R2 (ya que se tiene bit de A 1 y de B 0,siendo 1 menor por representar los negativos).Todo el resto de los bits se comporataran de la misma manera que en la versión unsigned.
