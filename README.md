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

Otra versión realizada la que seria mas bien la "oficial" (utilizando 16 bits) fue haciendo la resta de los dos numeros y luego utilizando las flags en el circuito unicamente hacemos un xor entre flags ingresadas debido a que las flags van a estar dadas por otros compañeros.Por lo que en el circuit verse tenemos la resta no conectada a nada y luego las flags.Esto porque en realidad br < funciona haciendo la resta luego haciendo con el resultado operaciones que sacan las flags y con las flags se ve si se cumple la relación para saltar.

Tenemos tres flags N Z V (si es negativo,si es cero,si desborda) las flags las explicaran en profundidad otros trabajos. Las relaciones son las siguientes si yo resto dos numeros y nos da cero osea Z 1 son iguales asi que no hay salto,
Z sera 0 en todas las otras instancias, si N 0 y V 0 bueno todo salio bien el numero dio positivo por lo que suponemos que A > B, esto porque si resto dos negativos o dos positivos si son mayorse siempre daran todo 0.
Si tengo N1 V 0 es que reste dos numeros y dio negativo porque o reste dos positivos o dos negativos y A es menor que B por lo que el resultado dara un 1.
Antes de seguir vamos a aclarar que si V  es 1 es que hay overflow porque el resultado de N va a ser mentira porque como hubo overflow se afecto el numero de mayor significancia,esto va a pasar al trabajar con numeros muy grandes
Entonces si N 0 y V 1 N es mentira por lo que es 1 y A < B, si N 1 V1 N es mentira por lo que es 0 y A > B

Entonces como vemos Z al final no importa siendo 0 o 1 no nos cambia la vida en nuestra operacion importa el N y V 
0 0 0
0 1 1
1 0 1
1 1 0
Esto se resuelve con un xor y el resultado dira si tenemos que saltar o no
