# Notificaciones

Tal y como indica el nombre, aqui se analizara el funcionamiento del sistema de notificaciones en laravel.


# Notas 

Primera revision{

to mail, to array, variables publicas, privadas en este .

}


Primera revision:  6 de junio de 2019 -> 12:32 


Las notificaciones en laravel funcionan de la misma manera que las demás classes,
la función construct es el constructor, por lo que obviamente, todo parámetro que metamos dentro del método de notificaciones ida a parar ahi,

Sin embargo los métodos que mas deberemos revisar son las de toMail y via y to Array
,

En via escogeremos por que veas enviaremos esta notificación, sin por solo por DB o por Correo electrónico (También se puede enviar por SMS y por Broadcast pero eso ya lo descubriremos mas tarde)

Via [‘database’] = Para esta opción deberemos primero haber migrado la base de datos de notificaciones de laravel por defecto

php artisan notifications:table

php artisan migrate

Ahora como lo usamos?

Primero obviamente deberemos crear una notificación para usarlo

                        php artisan make:notification nombre_noti

Después retocar la función via para que apunte a database y toArray

en las notificación por DB tendremos que tener en cuenta el método toArray, porque el contenido de nuestro array se encontrara ahi


Bien para lanzar la notificación:

Envés de auth:user() puede ser cualquier usuario.

Auth::user()->notify(new nombre_notificacion($variable));


Para ver las notificación del usuario:

//Auth::user()->notifications()

Notificación no leidas

Auth::user()->unreadNotifications()

Notificación leídas

Auth::user()->readNotifications()

Las ultimas 5 notificaciones no leídas

Auth::user()->unreadNotifications()->latest()->limit(5)













