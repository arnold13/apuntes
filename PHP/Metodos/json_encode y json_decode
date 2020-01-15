Al igual que toArray , permiten guardar objetos en sus formatos definidos (JSON) guardando solo los atributos

(Solo atributos, esto es muy importante ya que en un objeto puede haber información delicada)

$saludo = JSON encode( array(’saludo’ => ‘mundo'))

Traducción:  {[ ’saludo’ = ‘mundo'   ]}

Después a la hora de querer ver el saludo:


$saludo = json_decode($saludo)->saludo //* Esto devolverá mundo
