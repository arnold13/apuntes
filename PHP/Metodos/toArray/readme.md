toArray es un metodo simple y util, ya que, como su nombre lo dice, su función base es convertir los objetos en array, sin embargo, no coge todos sus parámetros, sino convierte array los atributos del objeto/objetos

Por ejemplo:

#user => Un usuario tiene bastante parámetros, ademas de sus atributos, claro podríamos pasarlos todos O simplemente pasar el dato exacto que nosotros queremos.

Por ejemplo: {{Auth::user()->get(’name’)}} 

Este comando me devolvera todos los parámetros del usuario actualmente conectado, métodos, constructores,etc….., pero yo solo quiero su nombre, tenemos 2 opciones

{{Auth::user()->get()->first()->name)}} = Este simplemente nos recogera el primer objeto anidado y nos mostrara el nombre adjudicado a este (El nombre es reconocido por laravel gracias a que creamos un modelo de usuario)

O

{{  Auth::user()->get(’name’)->toArray()  }} = Esto me devolved un array en el cual su primera posición sera el atributo nombre (Otro array en la cual como llave tendrá ’nombre’ y su valor)

 Auth::user()->get(’name’)->toArray()[0][’nombre']

Array 1 {array 1 = nombre => ’name'}


json_encode y json_decode hacen exactamente lo mismo pero con formato JSON 
