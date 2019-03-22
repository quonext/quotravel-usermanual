###
XML
###

Uno de los puntos clave de QuoTravel es facilitar el acceso de sus clientes a su producto, y la inclusión del producto de terceros en su portfolio.

Para ello se ha dotado a QuoTravel de un motor de reservas con un tiempo de respuesta de primer orden y absolutamente escalable, capaz de absober cualquier exigencia de tráfico con un coste mínimo.

QuoTravel se ha diseñado para poder extender fácilmente el sistema, y el xml no es una excepción.

Para añadir nuevas integraciones de compra o para publicar nuevos xml tan solo hay que escribir los traductores pertinentes y conectarlos a QuoTravel, y esta es una tarea que tanto puede realizar su departamento de IT, como encargarlo a Quonext o a una empresa externa de su confianza.


*********
Xml venta
*********

QuoTravel soporta los estándares `Caval
<http://caval.travel>`_ y el más moderno `EasyTravelAPI
<http://easytravelapi.org>`_.

Eso quiere decir que cualquier empresa que soporte estos estándares puede conectarse sin necesidad de ningún desarrollo. Desde el momento en que le damos acceso al sistema, tan solo necesita mapear el producto.

Tood el producto que tenemos en QuoTravel es accesoble a través de los xml.

Para soportar una nueva especifiación tan solo hay que desarrollar un traductor y conectarlo a uno de los xmls de QuoTravel.

El estándar OTA no está soportado por defecto, ya que en la práctica no es un estándar (no hay 2 empresas que hayan implementado igual la especificación) y necesita de un desarrollo ad hoc para cada conexión.

**********
Xml Compra
**********

Cualquier proveedor que soporte EasyTravelAPI o Caval está directamente soportado.

Eso quiere decir que, una vez que nos han dado acceso, tan solo necesitamos dar de alta la conexión en QuoTravel y mapear el producto.

En QuoTravel el mapeado es opcional en diferentes grados. Podemos mapear desde tipos de habitación y régimen concretos, hoteles y hasta destinos completos.

Esto quiere decir que para publicar el producto de un proveedor basta dar de alta la conexión, sin necesidad de mapear nada.

Naturalmente, si no mapeamos nada ofreceremos a nuestros clientes tanto los destinos de nuestro proveedor como los nuestros propios, pudiendose dar el caso de que ofrezcamos el mismo destino varias veces.

A partir de ahí, podemos por ejemplo ir mapeando solo destinos, hoteles, o llegar a mapear tipos de habitación y de régimen si queremos llegar al punto de ofrecer la opción más económica de la misma habitación.

QuoTravel incluye por defecto un traductor con Hotelbeds para la compra de camas de hotel.


*****
Otros
*****

Además de los xmls de venta y compra, QuoTravel tiene otras integraciones desarrolladas, que son:

- Islandbus para el envío de traslados e importación de horarios de recogida
- Google translator para traducir contenidos
- Google maps
- Flightstats para actualizar los horarios de los vuelos
- Clickatell para enviar SMS a los clientes
- Dropbox / Google Drive para almacenar ficheros de gran tamaño
- Google Calendar para exportar las reservas al calendario de Google
- Github para actualizar las webs de cliente final
- Voxel para facturación electrónica y VCC
- Fichero SEPA para el envío de remesas al banco
- Fuentes de datos para PowerBI, Qlik y similares

