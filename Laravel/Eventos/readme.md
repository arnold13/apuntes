Llamada a eventos:

Cuando llamamos a un evento en algún controlador:

event(new Nombre_evento($Variable_Pasar))


La variable que estamos pasando le llega a la función construct del evento


Evento :




function _Construct($variable_pasada){

dd($variable_pasada) 

<!— La variable pasada llegara dentro de esta función para hacerla global deberemos instanciar una variable global en el controlador similar a JAVA —>

}

|| After =>


$variable_global


function contruct($variable_pasada){  

                   (Básicamente esta función se ejecutante automáticamente al lanzar el evento)

$this->variable_global = $variable_pasada

    (La variable $this es un scope global de todo el controlador, obviamente con ella veras todas las funciones y variables de todo el controlador, aunque básicamente es util para llamar a una variable global en una funcion de este controlador)

}

Nota adicional:


Cuando usamos el broadcast con los eventos,(Para activarlo hay que implementar en la clase ’ShouldBroadcast’)

(class ‘nombre_evento’ implements ShouldBroadcast(


Como seguia, cuando usamos el broadcast y este llegue al escucha (En mi caso larval echo + pusher,  dentro de vue), la información que llega a la función del escucha son todos las variables publicas del evento (Protetected y Private no).

Esas variables pasan a vue en forma de propiedades


evento variable = $hola = ‘hola mundo’

Al llegar al escucha (Echo.listen.private) = 

(data) => { 

data.hola = ‘hola mundo’;  // De la misma manera que se llama la variable se llamara la propiedad.

}

