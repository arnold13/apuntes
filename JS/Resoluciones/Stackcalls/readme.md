StackCalls (Multiples llamadas a funciones)

Este fallo suele aparecer cuando usamos una función dentro de otra función, y esta la ejecutamos mas de 1 vez, al ejecutarla por 2 vez, la función se ejecutara 2 veces 

Ejemplo:

Función hola
    Funcion mundo
        return ‘hola mundo'

boton_saludo {{Al click = ejecutar hola.mundo() }}

Entonces si yo realizo 2 clicks en el botón, este me devolverá ‘hola mundo hola mundo’, si ejecuto 3 clicks, lo mismo, por eso, para evitar este error tan molesto usaremos el método

stopImmediatePropagation

Lo haríamos tipo

on click, function(e) => {e.stopinmediatepropagation}

De esta manera todas las funciones planeadas para realizarse después de este se cancelan. (Obviamente si quieres hacer un callback, tendrás que instanciarlo DESPUES de llamar ’stopinmmediatepropagation’ porque sino no funcionara. )


DIFERENCIAS

StopPropagation = Evitar para propagación de los demás eventos anidados a este, por ejemplo, si yo quiero pulsar un div y que salga un mensaje pero pulsando ese div también pulso otro div anidado al que saldrá otro mensaje, para evitar que ambas funciones se ejecuten usare este método

stopinmediatepropagation= Es un apaga y vamos, Ejecutar, limpiar todas las funciones y eventos posteriores y a seguir. (Util para parchear stackcalls)




(Mas que solucionarlo seria un parche, ya que las llamadas se siguen haciendo solo que la función solo ejecuta 1 vez.)
