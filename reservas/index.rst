######################
Reservas / Call center
######################

Aquí explicaremos toda la parte relacionada con la entrada y la gestión de las reservas, en cuanto a la relación con los clientes se refiere.

Desde la prereserva (gestión de presupuestos), hasta la confirmación de horarios de recogida de los traslados.

No entra en este capítulo la gestión operativa de los servicios, que veremos en otro capítulo más adelante.


******
Grupos
******

En este capítulo vemos la gestión de las peticiones de cotización para grupos.


Tipos de grupos
===============

Es un dato que sirve únicamente a nivel estadístico.

Para cada tipo de grupo indicaremos simplemente un nombre.


Solicitud de cotización
=======================

Para cada solicitud de cotización de un grupo podemos tenemos los siguientes campos:

Auditoría
  Quien y cuando ha creado esta petición, y quien y cuando ha hecho la última modificación

Agencia
  Agencia que hace la petición.

Punto de venta
  Punto de venta relacionado con este presupuesto

Título
  Título del presupuesto, para identificarlo

Tipo de grupo
  Tipo de este grupo. Para utilizarlo después en informes

Divisa
  Moneda en que están expresados los precios en este presupuesto

Hoteles
   Servicios de hotel incluidos en este presupuesto

Traslados
   Servicios de traslado incluidos en este presupuesto

Excursiones
  Excursiones incluidas en este presupuesto

Genéricos
  Servicios genéricos incluidos en este presupuesto

Líneas
  Líneas de texto libre incluídas en este presupuesto

Fecha
  Fecha del presupuesto

Fecha de opción
  Fecha de fín de validez del presupuesto

Texto
  Texto de la solicitud

Comentariso privados
  Comentarios para uso interno

Nombre contacto
  Nombre del contacto

Email
  Email del contacto

Teléfono
  Teléfono de contacto

Comentarios
  Histórico de comentarios adscritos a este presupuesto

Pagos
  Prepagos relacionados con este presupuesto

Tareas
  Envíos relacionados con este presupuesto


Integración con el email
========================

Desde la misma petición de contización podemos enviar emails que quedan automáticamente registrados y relacionados con la solicitud de cotización en cuestión.

Las respuestas a nuestros emails quedan automáticamente ligadas a la solicitud, y recibimos un email con la respuesta original.

También podemos adjuntar cualquier email a una solicitud de cotización reenviádolo a xxx@yyy.zz con el texto [QUOTRQ-<id de la solicitud>] en el asunto.



********
Reservas
********

En este apartado revisaremos la reserva y su operativa.


Modelo de datos
===============

Para entender la reserva vamos a repasar un momento como es el modelo de datos que la soporta.

En QuoTravel las entidades que conforman la reserva son:

Expediente --> Reserva --> Servicio

El expediente es como una carpeta donde vamos metiendo todas las peticiones que nos hace un cliente, que agrupamos bajo un mismo localizador.

La reserva es una solicitud que nos hace el cliente. Puede ser por ejemplo una petición de traslado de entrada y salida, o una estancia con traslado, o un ticket de una excursión.

Un expediente puede contener varias reserva, y una reserva puede generar varios servicios.


Expediente
----------

El expediente viene a ser una carpeta en al que metemos todo lo relacionado con un conjunto de reservas.


Para cada expediente tenemos

General
  Aquí tenemos algunos campos. Básicamente la cabecera del expediente

  Nº
    Nº que identifica a este expediente

  Autitoría
    Quien y cuando ha creado este expediente, y quien y cuando lo ha modificado por última vez

  Agencia
    Agencia a la que pertenece este expediente

  Título
    Un título para este expediente

  Referencia agencia
    Nº de vuelo, id tour, ...

  Titular
    El titular de este expediente

  Email
    Email de contacto

  Teléfono
    Teléfono de contacto

  Abierto
    Mientras un expediente está abierto pueden añadirse y/o modificarse servicios.

  Cancelado
    Indica si todos los servicios incluidos en este expediente han sido cancelados

  Comentarios internos
    Texto libre para nuestras anotaciones

Datos de facturación
  Si queremos sobreescribir los datos de facturación de la agencia. Por ejemplo en el caso de un contado.

  Nombre
    Nombre que debe aparecer en la factura

  Nombre fiscal
    Nombre fiscal

  Nif
    Nif del cliente

  Dirección
    Dirección del cliente

  Población
    Población del cliente

  CP
    Código postal

  Provincia
    Provincia

  País
    País

Peticiones de cotización
  Lista de peticiones de cotización (tanto de la agencia como a proveedores) relacionadas con este expediente.

Reservas
  Lista de reservas incluidas en este expediente.

Servicios
  Lista de servicios relacionados con este expediente

Líneas de cargo
  Líneas de cargo relacionadas con este expediente

Pagos
  Pagos relacionados con este expediente

Incidencias
  Lista de incidencias, emails y comentarios relacionados con este expediente


Naturalmente a nivel de expediente tenemos siempre un total, el margen que ha dejado y un saldo con sus respectivos desgloses / extractos.

Recordar que el valor de una reserva no tiene por que corresonderse con el valor a facturar. Sería el caso por ejemplo de una reserva de facturación directa, o de una reserva donde nosotros actuamos como representante y solo nos llevamos una comisión, aunque el cliente debe ver el valor real del servicio.

Reserva
-------

Para cada reserva debemos indicar

Expediente
  Expediente al que está adscrito esta reserva. Es obligatorio

Venta directa
  Si esta reserva es venta directa (el contrato lo ha firmado el touroperador con el proveedor).

Punto de venta
  Punto de venta para esta reserva

Mercado
  Mercado al que pertenece el pasajero

Representante
  Quien se lleva la comisión

Cancelada
  Si la reserva está cancelada

En firme
  Si la reserva es en firme. En caso contrario estamos ante un presupuesto

Fecha de caducidad
  Si la indicamos, la reserva se cancelará automáticamente en esa fecha y hora si para entonces la reserva no es en firme.

Confirmada
  Si hemos confirmado el servico al cliente. Si no está marcado, esta reserva está on request, pendiente de contestación.

Bloqueada
  Si bloqueamos la reserva entonces el sistema de importación no la tocará

Ya facturado
  Si esta reserva ya la hemos facturado fuera de QuoTravel



Y, en función del tipo de reserva:

Llegada vuelo
^^^^^^^^^^^^^

Esta es una plantilla para meter el conjunto de reservas de una llegada de un touroperador.


Aeropuerto
  Aeropuerto en el que recogemos (y desde donde luego saldrán) a los clientes

Fecha y hora
  Fecha y hora del vuelo de llegada

Nº vuelo
  Nº del vuelo

Origen
  Origen del vuelo

Lista de hoteles
  Lista de hoteles en que dejaremos a los clientes

  Titular
    Titular de este servicio

  Hotel
    Hotel en el que se alojan

  Estancias
    Lista de habitaciones, fechas, ocupación (nº de pax y edades niños) y tipo de régimen

  Observaciones
    Observaciones sobre esta reserva

  Salida
    Cuando se marchan estos clientes

    Vuelo
      Nº de vuelo

    Fecha y hora
      Fecha y hora del vuelo

    Destino
      Destino del vuelo

Texto libre
^^^^^^^^^^^

Esta es una plantilla para meter una reserva de un servicio de texto libre.

Esto es, que no hemos cargado ningún producto en el sistema pero queremos mandar el servicio al proveedor y generar la operativa y el flujo de facuración pertinentes.

Fechas
  Inicio y fin del servicio

Descripción del servicio
  Texto libre describiendo el servicio

Observaciones
  Observaciones que deben llegar al proveedor y aparecer en la rooming, etc


Hotel + traslado
^^^^^^^^^^^^^^^^

Esta es una plantilla para meter una reserva que incluye hotel y opcionalmente traslado.


Llegada
  Datos relativos a la llegada del cliente

  Fecha y hora
    Fecha y hora de llegada del vuelo

  Nº vuelo
    Nº vuelo de llegada

  Origen
    Origen del vuelo

  Aeropuerto
    Aeropuerto, puerto, estación de tren, ...

  Tipo traslado
    Tipo de traslado

Hotel
  Datos relativos a la estancia

  Hotel
    El hotel

  Estancias
    Lista de estancias (habitaciones + pax + regímenes)

Salida
  Datos relativos a la salida

  Queremos la salida
    Si queremos el traslado de salida. Si no lo queremos, deberemos indicar la fecha de salida del hotel.

  Fecha y hora
    Fecha y hora del vuelo

  Nº vuelo
    Nº del vuelo

  Aeropuerto
    Aeropuerto, puerto, estación de tren, ...

  Destino
    Destino

  Tipo traslado
    Tipo de traslado



Genérico
^^^^^^^^

Esta es una plantilla para reservas de producto que hemos metido como genérico

Producto
  Producto reservado

Fechas
  Fecha inicio y final de la reserva

Pax
  Nº pax

Edades niños
  Edades de los niños

Suplementos
  Lista de suplementos elegidos (cantidad)


Traslado
^^^^^^^^

Esta es una plantilla para meter reservas de traslados.

En la misma plantilla metemos el traslado de llegada y el de salida.

Fecha y hora
  Fecha y hora el vuelo de llegada

Nº vuelo
  Nº del vuelo

Origen / destino
  Origen del vuelo. Destino si es un traslado de solo salida

Desde
  Punto de recogida de los clientes

Hasta
  Punto de entrega de los clientes

Tipo
  Tipo de traslado

Vuelta
  Datos relativos a la vuelta

  Fecha y hora
    Fecha y hora del vuelo

  Nº vuelo
    Nº del vuelo

  Destino
    Destino


Hotel
^^^^^

Plantilla para una reserva de solo hotel.

Hotel
  El hotel

Estancias
  Lista de estancias (fechas, pax, edades, nº habitaciones, habitaciones y regímenes)

Suplementos
  Suplementos opcionales elegidos



Paquete
^^^^^^^

Plantilla para una reserva de un tour / paquete

Tour
  El tour

Fecha
  Fecha

Turno
  El turno

Variante
  La variante

Suplementos
  Lista de suplementos opcionales elegidos


Ticket
^^^^^^

Plantilla para meter la venta de un ticket (excursión, por un representante)


Fecha venta

Representante

Nº ticket

Fecha servicio

Excursión

Turno

Confirmación proveedor

Pax

Nombre cliente

Hotel / punto de recogida

Hora recogida

Nº habitación

Observaciones

Gratuidades (compra y venta)

No comisionable





    Fecha venta
    Nº Ticket
    Guía venta / Representante
    Fecha servicio
    Excursión
    Turno
    Confirmación proveedor
    Nombre cliente (pasajero)
    Idioma
    Personas
    Hotel / Punto de recogida
    Hora recogida
    Num. Habitación
    Observaciones
    Gratuidades (Compra y Venta)
    No comisionable






>>>>>>>>>>>> NOTA: considerar cambiar Booking por File y BookingPart por Booking


Identificación de una reserva
=============================

La referencia que nos da la agencia para una reserva figura, igual que el titular y otros datos, en la BookingPart que es la entidad que se corresponde con la petición que nos ha hecho el cliente. Esa referencia es la que figurará en las facturas que emitimos a la agencia, para que pueda validar nuestras facturas.

El nº de la Purchase order es el que esperamos que el proveedor incluya en sus facturas, para que podamos validarlas.

El nº que identifica a la Booking y al Service son solo para uso interno nuestro.

Estados de la reserva
=====================

La verdad es que la reserva incluye varios estados, cada uno para indicar un estado de la reserva desde un punto de vista diferente, y que están repartidos entre las diferentes entidades que conforman la reserva.

Estos son los diferentes estados relacionados con la reserva:

- Booking

  - Estado del expediente:

    - Abierto
      Admite modificaciones, nuevas reservas, cancelaciones, etc
    - Cerrado
      No admite más reservas ni modificación de las existentes

- BookingPart

  - Petición cliente cliente
    Puede ser una petición en firme o un presupuesto

  - Respuesta al cliente
    Puede estar en estado confirmada o no confirmada

  - Servicios
    Puede estar en estado "Servicios confirmados" o en estado "Servicios no confirmados"

- Service

  - Activo
    Puede estar on activa o cancelada
  - Gestión
    Puede estar pendiente, en proceso o gestionada
  - Compra
    Puede estar on request o confirmada

- PurchaseOrder

  - Estado
    Puede estar pendiente, enviada, leída, rechazada o confirmada

- Task

  - Estado
    Puede estar pendiente de enviar o enviada


Presupuesto / reserva de cupo
=============================

Mientras una reserva no ha sido confirmada por el cliente se entiende que es un presupuesto.

En este estado, la reserva puede reservar cupo o no.

Para las reservas en este estado podemos indicar una fecha de caducidad que, al vencer, cancelará automáticamente la reserva y devolverá el cupo en caso de que estuviese reservado.

En el momento en que el cliente confirme la reserva se reserva el cupo si es que no ha sido reservado todavía.

Naturalmente, puede pasar que ese cupo ya no esté disponible, o que el precio haya cambiado desde entonces.

En ese caso el cliente recibe el aviso de la circustancia y puede reconfirmar la reserva o desecharla.


Reserva multi servicio
======================

En QuoTravel podemos incluir en la misma reserva varios servicios.

Es lo que a veces llamamo paquete dinámico, en el que el usuario puede ir añadiendo diferentes servicios a su reserva.

El que lo junta todo es el expediente.

Servicios compuestos
====================

Como hemos comentado ya, una reserva de un cliente puede convertirse en varios servicios que hay que gestionar y comprar.

La demultiplexación se realiza entre la reserva y los servicios.

Algunos ejemplos:

  - Ejemplo 1: reserva hotel con cena en restaurante externo
  - Ejemplo 2: traslado IBZ - Formentera

Recordar que el servicio es la unidad base de la gestión operativa. Para un servicio siempre tendremos en cada momento una única compra activa a un único proveedor.


Separación de venta y compra
============================

En QuoTravel la gestión de la venta es independiente de la gestión de la compra.

Esto quiere decir que podemos vender servicios independientemente de a quién se los compremos después.

O cambiar el proveedor de un servicio en cualquier momento.

>>>>> Poner ejemplos.


Frees
=====

En cualquier reserva podemos indicar pax free.

Lo podemos hacer tanto en la venta como en la compra.

El pax free aparece como un línea de cargo en negativo en la factura y en la previsión.


Entrada de reservas desde disponibilidad
========================================

Todos los servicios son reservables desde la consulta de disponibilidad.

Para cada servicio disponemos de una consulta de disponibiidad donde, a partir de las fechas, pax y zona, el sistema nos dice que opciones hay disponibles.

A partir de ahí seleccionamos la opción que nos interesa, suplementos opcionales en caso de que los haya y, finalmente, confirmamos la reserva.

Es exactamente el mismo procedimiento que tenemos en la web, solo que un poco más abierto.


Entrada manual de reservas
==========================

Además de realizar una reserva desde la disponibilidad, en QuoTravel podemos crear una reserva manualmente.

Esto quiere decir que nosotros indicamos lo que estamos reservando, independientemente de que exista contrato o cupo.

A la hora de hacer la reserva podemos indicar si es necesario que haya precios (contrato) o cupo.

Si existiese un paro de ventas que afecte a nuestra reserva el sistema nos avisará, pero podremos realizar la reserva igualmente.


Entrada masiva de reservas
==========================

En QuoTravel hay algunas pantallas para facilitar la entrada masiva de reservas.

Es el caso de la entrada de un vuelo de un touroperador.


Generar excel --> modificar --> subir excel.


Control rentabilidad
====================

Para cada reserva tenesmo un saldo que nos indica el beneficio o pérdida.

Ese saldo se registra a nivel de expediente, a nivel de reserva y a nivel de servicio.


Reservas on request
===================

Si no hay cupo, si estamos fuera de release o bajo otras circunstancias un servicio puede estar on request.

Si un servicio está on request el proveedor debe confirmarlo y, tanto si al final lo confirma como si no, nosotros debemos trasladar el resultado final al cliente.

Si un proveedor no confirma un servicio naturalmente podemos buscar un proveedor que si que lo confirme, y cambiar la compra de ese servicio.


Calculadora
===========

El precio de una reserva puede venir dado porque hayamos cargado un contrato, porque estemos comprando el servicio a un tercero a través de una integración, o porque metamos nosotros el precio manualmente.

En este caso podemos ayudarnos de la calculadora que nos aparece cuando seleccionamos precio manual.

La calculadora es un campo de texto libre que nos permite indicar una fórmula para calcular el precio de la reserva.


Hay variables predefinidas, y podemos poner comentarios.


>>>>>>> explicar la sintaxis.


Visibilidad total
=================

En QuoTravel desde la reserva podemos aceder a toda la información relacionada con la misma.

Es como un árbol que se va abriendo que nos permite llegar hasta la contabilidad incluso.

Así, desde la reserva podemos acceder a:

  - Ficha del cliente
  - Facturas emitidas
  - Cobros
  - Pedidos al proveedor
  - Ficha del proveedor
  - Facturas recibidas
  - Pagos
  - Asientos contables

>>>>>>>>> Ojo permisos a nivel de entidad


Operativa automática
====================

En este apartado hacemos referencia a la operativa automática de la reserva de cara al cliente, no a la operativa de cara a la compra que se explica en el capítulo dedicado a operaciones.


Así, el flujo general de una reserva es:

Cotización? --> reserva --> organizar servicios / mandar al proveedor --> fin


En el caso de una reserva de cliente final el flujo de la misma es:

Reserva --> email confirmación --> email aviso 1er pago --> email aviso 2o pago --> voucher / reserva cancelada



En el caso de una reserva de una agencia a credito el flujo es el siguiente:

Reserva --> email confirmación / voucher --> reserva cancelada


>>>>>>>>> pensar si incluimos algunos gráficos



Emails aviso pagos
==================

Es un email que se manda automáticamente al cliente si así lo hemos configurado.

También lo podemos mandar en cualquier momento desde la reserva.

El email contiene la información de la reserva, información para el pago de la misma y un link para pagar la reserva utilizando la pasarela de pago que hayamos configurado.


Voucher
=======

Para cada servicio se entrega un voucher al cliente.

El voucher es completamente personalizable.

Recordar que una reserva del cliente puede generar varios servicios, así que para una misma reserva podemos enviar varios vouchers al cliente.

Hay un campo en el contrato de compra que afecta directamente al voucher y es el campo "Pagadero por", que siempre aparece en el voucher.


Cancelación automática
======================

Si en una reserva indicamos una fecha de caducidad la reserva se cancelará automáticamente al llegar a esa fecha.

El sistema mandará un email tanto al cliente como a la delegación como al proveedor (si ya le habíamos enviado la reserva).

Esta operativa es propia de reservas que utilizamos para reservar cupo.

Registro cambios
================

Todas las reservas registran los cambios que hacemos sobre las mismas, y podemos consultar ese registro de cambios desde la misma reserva.

Si los cambios que realizamos sobre una reserva afectan al servicio se dispara la operativa para que esos cambios lleguen al proveedor.

Promo codes
===========

Los promo codes son ofertas especiales, muy sencillas, que podemos crear para después aplicar un descuento especial a un cliente.

Para cada promo code definimos

Code
  Si queremos indicarlo nosotros (opcional)

Nombre
  Descripción de la oferta

Porcentaje
  Porcentaje descuento

Importe
  Importe descuento

Divisa
  Divisa para el caso de que hayamos indicado un importe

Cupo
  Nº de veces que podemos aplicar esta oferta / descuento (no sobre la misma reserva)

Concepto de facturación
  A utilizar cuando se aplique este descuento

Caducidad
  Fecha y hora hasta las que es válido este decuento

El sistema nos dará un código que es el que debemos utilizar cuando hacemos la reserva, si queremos aprovecharnos de la oferta.

Para cada promo code podemos ver las reservas en que se ha utilizado y el importe total del descuento aplicado.



Gastos de cancelación
=====================

Los gastos de cancelación de una reserva quedan registrados cuando confirmamos la reserva.

Para cada gasto de cancelación podemos indicar

Fecha y hora aplicación
  Fecha y hora a partir de la cual son aplicables estos gastos

Importe
  Importe de la cancelación si se cancela después de la fecha y hora indicadas

Moneda
  Moneda en que está indicado el importe de cancelación


Tenemos gastos de cancelación tanto para la compra como para la venta.


Cobros
======

Dese una reserva podemos ver todos los cobros que relacionados con la misma, así como introducir nuevos cobros.

Podemostambién enviar un email a un cliente con un link a una pasarela de pago, para que realice un pago con tarjeta.

Cuando ese pago se confirma queda registrado automáticamente en la reserva y se actualiza el saldo de la misma.


*********************
Otras funcionalidades
*********************

Aquí vemos otras funcionalidades que tenemos en el call center.


Confirmación de horarios de recogida de clientes
================================================

Desde el call center podemos responder a un cliente que ha llamado para confirmar la hora de recogida de su traslado de salida.

Tras localizaqr el servicio, podemos indicar que hemos informado al cliente del horario de recogida.

También podemos acceder al servicio, por si tuviésemos que modificar algún dato del mismo.

Si la modificación afecta al servicio se dispara la operativa necesaria.


Gestión de incidencias
======================

En QuoTravel podemos registrar incidencias relativas a un servicio.

Para cada incidencia podemos indicar:

Autitoría
  Creador y fecha de creación de la incidencia

Servicio
  Servicio al que está asociada esta incidencia

Texto
  Texto explicativo de la incidencia

Cargo a la venta
  Líneas de cargo asociadas a la venta. Puede ser en positivo o en negativo.

Cargo a la compra
  Líneas de cargo asociadas a la compra (al proveedor). Puede ser en positivo o en negativo.



Consultas varias
================

La información que hemos introducido con las reservas es mucha y muy variada.

Para poder gestionarla de manera adecuada disponemos en Quonext de varias consultas que nos permiten, además de poder tener una visión adecuada y completa de nuestras reservas, realizar operaciones sobre conjuntos de ellas.

Las consultas disponibles son:

- Vuelos
- Grupos
- Llegadas
- Salidas
- Excursiones
- Circuitos
- Pax en destino



***********************
Importación de reservas
***********************

La importación de reservas de clientes es un componente clave en QuoTravel.

Lo es especialmente en la parte de traslados, en la que el volúmen de reservas es tan grande que sería inviable intruducir y mantener las reservas manualmente.

La importación de reservas normalmente precisa de web scraping, conectarnos al servidor de correo para leer los correos que nos ha mandado la agencia, etc. Cada agencia es diferente pero lo bueno es que, con QuoTravel, basta desarrollar un pequeño módulo para importar las reservas de una nueva agencia.


QuoTravel va integrando las reservas tal cual nos las proporciona el proveedor, con la frecuencia que deseemos.

Esas reservas del cliente se transforman en las correspondidentes reservas dentro de QuoTravel.

Cada cambio de la reserva en el client se refleja en nuestra reserva en QuoTravel y, si es necesario avisa de que es necesario realizar alguna acción como volver a organizar el servicio, o volver a mandar la reserva al proveedor.

Si es necesario, se envía la confirmación al cliente cuando el servicio es confirmado, pero eso ya forma parte de la operativa habitual de las reservas.

Actualmente en QuoTravel están funcionando sin incidencias la integración de reservas de traslados de Travelrepublic, Traveltino y de ShuttleDirect.


