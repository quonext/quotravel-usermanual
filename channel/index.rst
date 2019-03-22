Introducción
====


La plataforma incluye la funcionalidad de channel manager.

Esto es, la plataforma permite actualizar precios, cupos y paros de ventas en Booking.com, Expedia y similares. También recoge las reservas hechas en estas agencias y las "baja" a QuoHotel.

La operación en modo channel manager ("push") tiene una serie de desventajas con respecto a la operación con servicios web ("pull"), en la que la agencia obtiene precios y disponibilidad en tiempo real.

Las principales desventajas de la operación en modo "push" son:

- no es posible "subir" a la agencia todas las condiciones de precios que tenemos en QuoHotel
- la integración es menos fiable
- necesita más recursos (a nivel de servidores)

Estas desventajas se traducen normalmente en pérdida de competitividad (no podemos transmitir descuentos o ofertas porque el destinatario no los contempla en su lógica), en más trabajo y en mayores costes.


No obstante, QuoOn soporta la operación de channel manager con aquellas agencias (Booking.com, Expedia, etc) que no trabajan en modo "pull".


Para trabajar con una agencia en modo "push" simplemente hay que darla de alta en la plataforma y habilitarla en modo "push". También es necesario un pequeño "mapeo" de nuestros códigos a los códigos de la agencia.

A partir de ahí, cualquier tarifa/contrato que tengamos en QuoHotel al que tenga acceso esa agencia se le enviará, utilizando los servicios que para ello ha pulicado.


Es importante observar que no todas las condiciones que tenemos en QuoHotel se podrán transmitir a la agencia. Por ejemplo, es normal que descuentos que dependan de la edad del niño no se puedan transmitir.

En estos casos la plataforma utilizará siempre la peor opción para asegurar que no hay reservas que se confirmen con un precio por debajo del coste. Siguiendo con el ejemplo anterior, en el caso del descuento de niños el sistema publicará siempre el descuento para el niño de más edad.


Las integraciones para la operación de channel manager se irán desarrollando bajo petición de los usuarios de la plataforma.