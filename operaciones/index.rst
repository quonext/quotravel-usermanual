###########
Operaciones
###########

Aquí veremos la parte de QuoTravel relacionada con la organización de los servicios y el envío de los mismos a los proveedores.

Hay servicios que no hay que organizar, sino que simplemente los enviamos a los proveedores tal cual, mientras que hay tipos de servicio que sí que queremos organizar anmtes de mandarlos al proveedor.

Por ejemplo, un servicio de estancia siempre lo mandaremos tal cual al proveedor mientra que los servicios de traslado, dependiendo del tipo y de nuestra manera de trabajar, querremos organizarlo nosotros antes de mandarlo al transportista.

En el caso de los paquetes igual decidimos no realizar el servicio porque no llegamos a una rentabilidad mínima, y lo reenviaremos a un pool o cancelaremos el servicio.


***************
Modelo de datos
***************

Para entender la parte de operaciones es necesario entender un poco el modelo de datos.

::


  Reserva --> Servicio --> Pedido compra --> Tarea
                 |
                 v
                Tour


La reserva es una solicitud que nos hace el cliente. Puede ser por ejemplo una petición de traslado de entrada y salida, o una estancia con traslado, o un ticket de una excursión.

Una reserva puede generar varios servicios.

El servicio es la unidad básica de la parte operativa de QuoTravel. Es un servicio individual que debemos proporcionar y que normalmente pediremos a un proveedor.

Desde el servicio podemos llegar al tour con el que está relacionado, lo que nos permite saber que precio debemos aplicar.

El pedido de compra es la petición de servicio que hacemos a un proveedor. Puede ser una petición de un servicio concreto, o puede por ejemplo ser un bus que incluye varios servicios de traslado.

Lo importante aquí es que el nº que identifica el pedido de compra es la referencia que esperamos del proveedor en sus facturas, y que luego utilizaremos para validar la factura del proveedor.

Es importante entender que una rooming que mandamos a un hotel y que contiene varias estancias no es en este caso un pedido de compra. El envío de los pedidos de compra al proveedor es una entidad aparte, de manera que podemos enviar varios pedidos de compra al proveedor al mismo tiempo, que es lo que sería una rooming, o el mismo pedido de compra varias veces.



Servicio
========

Un servicio es la unidad mínima de gestión para operaciones.

No para cada tipo de reserva existe un tipo de servicio, sino que en ocasiones una reserva se resuelve con otros tipos de servicio (por ejemplo un paquete).

No editamos servicios directamente, sino que eso lo hacemos desde las reservas.


Para cada servicio podemos indicar:

Reserva
  Reserva que ha originado este servicio

Fechas
  Fecha de inicio y de final del servicio

Titular
  Titular del servicio

Validación
  Estado y mensaje

Cancelado
  Si el servicio ha sido cancelado

No show
  Si el cliente no se ha presentado. Este campo tiene especial relevancia para los traslados de llegada, ya que puede llevar a no hacer el servicio de salida

Retenido
  Si no queremos enviar el servicio al proveedor

Oficina
  Oficina responsable del servicio

Comentarios cliente
  Observaciones del cliente

Comentarios operaciones
  Observaciones que pone el departamento de operaciones. Van al proveedor

Comentarios privados
  Comentarios que no van a ningún lado. Solo para registro

Log cambios
  Histórico de cambios sobre el servicio

Precio
  Datos relativos al precio del servicio

  Precio venta


  Precio compra
  Valorada
  Totales neto, pvp y comisión
  Informe valoración
  Coste cancelación
  Compra valorada
  Total coste

Líneas de cargo


Compra
Servicio



Y luego tenemos campos específicos para cada tipo de servicio.

Hotel
-----

Un servicio de hotel añade el hotel en cuestión y las estancias.

Para cada estancia podemos indicar las fecha, tipo de habitación y tipo de régimen, la ocupación (nº habitaciones, pax y edades) y los suplementos opcionales deseados.


Traslado
--------

Un servicio de traslado añade el punto de recogida y entrega, los datos del vuelo de llegada y de salida, y los pax, edades y bultos y si necesita transporte adaptado (silla de ruedas).


Genérico
--------

Un servicio genérico tan solo añade una referencia al concepto reservado, el nº de unidades, pax y edades, y una lista de los suplementos seleccionados.


Texto libre
-----------

El servicio de texto libre solo añade un campo con el texto indicado en la reserva.



Pedido de compra
================

Los servicios que pedimos a un proveedor se materializan en pedidos de compra.

Un pedido de compra puede incluir varios servicios.

En ocasiones puede tener un significado extra. Es el caso de un traslado en el que el pedido está asociado a un autocar. En este caso, el pedido tiene campos extra para indicar los letreros y tiene un tratamiento especial desde la parte de operativa de traslados, como veremos más adelante.

Para cada pedido tenemos los siguientes campos:

Auditoría
  Quien y cuando ha creado esta tarea, y quien y cuando la ha modificado por última vez

Oficina
  Oficina que ha realizado el pedido

Proveedor
  Proveedor objeto del pedido

Cancelado
  Si el pedido ha sido cancelado

Comentarios
  Comentarios para el proveedor

Servicios
  Lista de servicios incluidos en este pedido

Entrega
  Datos relacionados con la entrega y la respuesta del proveedor

  Enviado
    Si se ha enviado o no

  Fecha y hora último envío
    Fecha y hora del último envío

  Fecha y hora de la última respuesta
    Fecha y hora de la última respuesta

  Estado
    Puede ser:

    - PENDIENTE
    - CONFIRMADO
    - RECHAZADO

  Comentario proveedor
    Comentarios del proveedor

Precio
  Datos relacionados con la valoración de este pedido

Cargos
  Líneas de cargo (previsión) relacionados con este pedido


Task
====

En QuoTravel todos los envíos quedan registrados como una tarea.

Así luego tenemos un histórico de los envíos que hemos realizado, podemos ver si hay envíos que hayan ido mal por alguna razón, podemos relanzarlos, etc.


Para cada tarea tenemos:

Auditoría
  Quien y cuando ha creado esta tarea, y quien y cuando la ha modificado por última vez

Comienzo
  Cuanodo se ha ejecutado esta tarea

Fin
  Cuando ha finalizado la ejecucuión de esta tarea

Estado
  Puede ser

  - Pendiente
  - En ejecución
  - Finalizada

Resultado
  Puede ser

  - OK
  - ERROR

Log
  Traza que ha dejado la tarea

Oficina
  Oficina a la que está ligada esta tarea

Proveedor
  Proveedor (partner) que está relacionado con esta tarea

Método
  Normalmente será EMAIL

Coletilla
  Coletilla que hemos añadido al email

A
  Destinatario principal

CC
  Con copia a

Contenido
  Contenido del email


Tour
====

El tour es la materialización de un paquete (excursión o evento).

Para cada tour tenemos

Paquete
  Paquete al que hace referencia este tour

Fecha
  Fecha del tour

Turno
  Turno en el caso de que el paquete sea una excursión

Listado de reservas
  Listado de reservas asociadas a este tour

Listado de servicios
  Listado de servicios asociados a este tour

Listado de compras
  Listado de componentes del paquete, y a quien hemos comprado el servicio

Estado
  Estado del tour. Se cancela cuando no hay ninguna reserva activa asociada al mismo.

Total coste
  Total coste para este tour (campo salida)

Total venta
  Total venta para este tour (campo salida)

Rentabilidad
  Margen que deja este tour (campo salida)

Comentarios
  Comentarios internos


***********************************
Común a todos los tipos de servicio
***********************************

Hay algunas operaciones que son comunes a todos los servicios

Calendario
==========

El calendario es en realidad un listado, que nos permite ver de manera rápida como tenemos el trabajo en el departamento de operaciones.

Para cada día y tipo de servicio nos muestra con colores muy claros si tenemos trabajo pendiente o si lo tenemos todo hecho (organizado, enviado al proveedor y confirmado).

Desde este listado podemos acceder al listado de servicios, para ver que servicios están pendientes y gestionarlos.


Listado de servicios
====================

Existe un listado de servicios que nos permite consultar los servicios que se han creado en el QuoTravel.

Desde este listado podemos filtrar por tipod e servicio, expediente, reserva, fechas, cliente, proveedor, y estado.

Desde este listado podemos tambien revisar, editar, y mandar al proveedor los servicios, ver los vouchers y mandarlos al cliente o cambiar el estado de los servicios de manera masiva.

En el caso de los servicios de traslado, podemos acceder a la organización de los mismos.


Operación automática
====================

Si así lo hemos marcado en el proveedor los servicios se enviarán automáticamente así como se vayan generando y asignando al proveedor en cuestión.

Si no hemos seleccionado el envío automático, los servicios se quedarán pendientes hasta que decidamos enviarlos.

Si hemos marcado que los servicios quedan automáticamente confirmados en cuanto se envían, los servicios quedarán como OK en cuanto los hayamos enviado.



Confirmación del servicio por parte del proveedor
=================================================

La operativa se cierra cuando el proveedor confirma el pedido.

Como hemos visto antes esta confirmación puede ser automática.

En caso contrario quedarán como pendiente y necesitarán que el proveedor los confirme, a través del link que viaja en el email o a través de la extranet.

Naturalmente nosotros también podemos darlos como confirmados desde el listado de pedidos a proveedor.


Recordatorio automático al proveedor en caso de servicio no confirmado
----------------------------------------------------------------------

En caso de que un pedido no haya sido confirmado lo vemos claramente con colores en los listados que tenemos en QuoTravel.

De todas formas, existe en QuoTravel la podisbilidad de enviar un recordatorio automático al proveedor en caso de que esto suceda.

Dicho recordatorio lo activamos en la ficha del proveedor y podemos indicar, para cada tipo de servicio, el nº de días de antelación para el envío del mismo.

El contenido de los recordatorios es personalizable, al igual que el resto de docuemntos que generamos en QuoTravel.


Comunicación a los clientes
===========================

En el caso de una modificación del servicio podemos activar desde aquí el envío de un sms o email a todos los clientes afectados.



*********
Traslados
*********

Aquí veremos los aspectos particulares para las operaciones de traslados.

Organización de traslados
=========================

La pantalla de organización de traslados es una versión específica para traslados del listado de servicios.

Añade algunos filtros como la ruta, el aeropuerto, el vuelo y a que bus ha sido añadido el servicio.

De esta manera podemos ir seleccionando servicios y añadirlos a un bus, ya sea uno existente o uno nuevo.

Por defecto el listado nos muestra los servicios que están pendientes y, a medida que los vamos metiendo en buses, el listado va decreciendo.

El sistema nos ayuda en la medida en que lo hemos alimentado.

Si hemos definido las rutas podremos pedirle al sistema que nos organice los traslados.

Si hemos introducido los horarios entre localidades (o las tablas de horarios de recogida de los autocares) el sistema podrá además rellenar los horarios de recogida para las salidas.

La organización automática de traslados es parametrizable según tiempo antelación a salida vuelo, nº máximo de paradas, tiempo máximo de espera en autocar y tipo de traslado.

Operativa habitual
------------------

La operativa normal es ir al calendario, desde allí ir a la pantalla de organización de traslados si vemos que el día que nos interesa no está en verde.

En la pantalla de organización de traslados vemos los servicios pendientes, y utilizamos la opción "Organizar" para que QuoTravel nos organice los traslados.

Si siguen quedando servicios sin bus, entonces los asignamos manualmente.

Una vez que tenemos el listado limpio (no quedan servicios sin un bus asignado) iremos al listado de buses.

En cada momento siempre tenemos a la vista el coste total de los traslados que tenemos en pantalla.

Desde el listado de buses, seleccionaremos los que no estén en verde y los mandaremos al proveedor.


Algoritmo
---------

QuoTravel utiliza un algoritmo para calcular la mejor combinación de traslados, que es el que explicamos en este apartado.

El algoritmo persigue concentrar a los pasajeros, para evitar las largas esperas en el autobús.

Así, el algritmo va repartiendo los pasajeros desde el vuelo con más pax hasta el vuelo con menos pax, hasta que no queda ningún pax sin repartir.

El algoritmo vigila que siempre se cumplan las restricciones que hemos indicado: tiempo máximo espera, nº paradas y tiempo facturación.

Podemos pedirle a QuoTravel que organize los traslados tantas veces como queramos, variando los parámetros en cada ocasión, hasta lograr la combinación que más nos convenza.

Luego podemos seguir ajustando el planing moviendo clientes de un bus a otro.

En cada caso siempre tenemos a la vista el coste total de los traslados que tenemos en pantalla.


Hay otros tipos de restricción al algoritmo:

Naturalmente los traslados privados van siempre en 1 único vehículo.

Para el caso de los traslados de touroperador, el sistema no junta nunca vuelos en la llegada aunque sí que lo hace en la salida.

Para el caso de los traslados de touroperador no juntamos clientes de diferentes touroperadores, a no ser que lo hayamos indicado en la ficha de cada touroperador.


Importación de horarios de recogida
===================================

En QuoTravel podemos importar los horarios de recogida de los clientes simplemente mandándolos a una dirección de correo.

También existe una pantalla para subir el excel con los horarios.

El excel debe tener el formato adecuado, y contener al menos las columnas con nuestro id de servicio, fecha y hora de recogida.



*****
Tours
*****

En el caso de los paquetes (excursiones y circuitos) QuoTravel crea automáticamente una entidad Tour cuando se existen reservas para ese paquete.

Existe un listado de Tours con filtros por fecha, tipo de paquete, paquete, cliente, etc desde el que podemos ver todos los tours que tenemos que gestionar.

Para cada tour podemos pedir un listado de recogidas, un listado de entregas, el itinerario, el conjunto de vouchers necesarios, un informe previo a la realización del tour (que incluye todo lo anterior y una previsión de costes para saber el dinero que hay que entregar a la guía) y acceder a la liquidación del mismo (donde la guía justifica los costes reales del tour).

Desde el tour podemos ver también las diferentes compras (elementos del paquete) y enviarlas a los proveedores.

Desde esta pantalla podemos ver también la rentabilidad de cada tour, y decidir desviarlo a un pool o cancelar el servicio.


En el caso de una modificación del servicio (por ejemplo al cancelar el tour) podemos activar desde aquí el envío de un sms a todos los clientes afectados.



