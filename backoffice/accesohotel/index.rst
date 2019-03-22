.. QuoOn user manual documentation master file, created by
   sphinx-quickstart on Tue Dec  5 09:46:59 2017.
   You can adapt this file completely to your liking, but it should at least
   contain the root `toctree` directive.

Acceso para el hotel
=============================================

El acceso para agencias tiene una url propia.

En el caso del entorno de test esta url es http://hotel.test.quoon.net .

========  =====
User      h
Password  1
========  =====

.. warning:: deberíamos poner el entorno de demo. Pendiente de conseguir servidor.

La funcionalidad que el usuario de una agencia puede encontrar en este acceso queda resumida en el siguiente diagrama:

.. figure:: /_static/img/backoffice/back04.png
    :align: center
    :figwidth: 700px

En los siguientes capítulos revisaremos cada una de las funcionalidades que aparecen en el diagrama.

Las diferentes opciones que ofrece este acceso para hoteles se agrupan en :

- Producto
- Call center
- CMS
- Mapeado
- Administración




Producto
---------------------------

EN este apoartado agrupamos las funcionalidades relacionadas con lo que vendemos: hoteles, habitaciones, regímenes, cupos, precios y paros de ventas.

Hoteles
~~~~~~~~~~~~~~~~~~~~~~

Para mantener la lita de hoteles hay que utilizar la opción "Hotels" del menú.

Nos aparecerá en pantalla una lista de los hoteles que tenemos en base de datos, con varias opciones para afinar la búsqueda y, para cada hotel, un link para poder entrar y editarlo.

Para cada hotel podemos editar su nombre, categoría, localización, id en QuoHotel y edades para cada tipo de niño (bebé, niño y júnior).


Tipos de habitación
~~~~~~~~~~~~~~~~~~~~~~

Para mantener los tipos de habitación deberemos utilizar la opción "Rooms" del menú.

Recodar que estos tipos de habitación son propios de cada hotel, mientras que las definiciones de tipos de habitación (básicamente el nombre) se hace a nivel general de la plataforma por el personal de Quonext.

Así, las definciciones de los tipos de habitación (mantenidas por Quonext) serán del tipo:

- doble
- doble vista mar
- suite
- junior suite
- ...

con sus respectivas traducciones a los diferentes idiomas.

A partir de estas definiciones, comunes para todos los usuarios de la plataforma, nosotros crearemos los tipos de habitación particulares de cada uno de nuestros hoteles.


Así, nosotros crearemos nuestro tipo de habitación doble para cada uno de nuestros hoteles, añadiendo las características de ese tipo de habitación en ese hotel concreto.

Las características que definimos en nuestros tipos de habitación son: hotel, definición del tipos de habitación, capacidades máximas expresadas en forma de adultos, niños y bebes, mñinimo pax, mínimos adultos para apliar descuento niño, si permite bebés, si permite niños, si los bebés ocupan cama y si consume el cupo asignado a otro tipo de habitación.


Tipos de régimen
~~~~~~~~~~~~~~~~~~~~~~

Para mantener los tipos de régimen deberemos utilizar la opción "Boards" del menú.

Recodar que estos tipos de rñegimen son propios de cada hotel, mientras que las definiciones de tipos de régimen (básicamente el nombre) se hace a nivel general de la plataforma por el personal de Quonext.

Así, las definciciones de los tipos de régimen (mantenidas por Quonext) serán del tipo:

- solo alojamiento
- alojamiento y desayuno
- media pensión
- pensión completa
- ...

con sus respectivas traducciones a los diferentes idiomas.

A partir de estas definiciones, comunes para todos los usuarios de la plataforma, nosotros crearemos los tipos de régimen particulares de cada uno de nuestros hoteles.


Así, nosotros crearemos nuestro tipo de régimen alojamiento y desayuno para cada uno de nuestros hoteles, añadiendo las características de ese tipo de régimen en ese hotel concreto.

Las características que definimos en nuestros tipos de régimen son: hotel, definición del tipo de régimen y una descripción del mismo.



Paros de ventas
~~~~~~~~~~~~~~~~~~~~~~

Para mantener los paros de ventas deberemos utilizar la opción "Stop sales" del menú.

Nos aparecerá un listado de los hoteles (solo hay un paros de ventas por hotel) y deberemos seleccionar uno de ellos.

A partir de aquí nos aparecerá una pantalla con los paros de ventas por día, marcando en color verde si ese día está abierto, en rojo si está cerrado y en amarillo si está cerrado parcialmente.

Recordar que los paros de ventas pueden hacerse por tipo de habitación y por contrato.

En la pantalla podemos utilizar uno de los filtros justamente para visualizar los paros que afectan a un tipo de habitación o contrato particulares.

Además de visualizar los paros de ventas, desde esta pantalla podemos abrir y cerrar ventas y ver el registro de todas las operaciones que se han realizado.

Recordar que el paro de ventas está relacionado con el cupo. Esto quiere decir que si cerramos un tipo de habitación "padre" cuyo cupo es consumido por otro tipo de habitación, también cerramos el tipo de habitación "hijo".


Inventario
~~~~~~~~~~~~~~~~~~~~~~

Para mantener los inventarios (o cupos) debemos utilizar la opción "Inventory" del menú.

Al contrario de lo que ocurre con los paros de ventas, sí que podemos tener varios cupos para un mismo hotel.

Recordar que, para cada hotel, siempre veremos al menos un cupo general, que es el cupo real del hotel. Luego podemos tener otros cupos que están ligados a uno o varios contratos, pero al final siempre se verifica que haya habitaciones disponibles en el cupo general del hotel.

En la pantalla de cupos vemos el cupo por día para cada tipo de habitación, y podemos filtrar los resultados por tipo de habitación.

En esta pantalla podemos además realizar operaciones sobre el cupo (añadir, fijar o restar cupo) y ver el registro de operaciones sobre el mismo.

Recordar que una habitación puede coger cupo de otra. Solo vemos el cupo real (el de la habitación "padre"), no veremos el cupo de las habitaciones "hijo".

Contratos
~~~~~~~~~~~~~~~~~~~~~~

Las tarifas y contratos que tenemos en QuoHotel se transforman en contratos en la plataforma.

Para mantener los contratos debemos utilizar la opción "Contracts" del menú.

A partir del listado podemos consultar los contratos, crear nuevos contratos o eliminarlos.

A partir del listado podemos pedir también un pdf con las condiciones del contrato en un formato imprimible, o para mandarlos a la agencia o tourooperador.

Recordar que los contratos están organizados jerárquicamente en la forma Hotel -> Contratos -> ... -> Contratos, de manera que podemos ir extendiendo contratos para crear un nuevo contrato que sobreescribe una parte de las condiciones del anterior.

Los contratos siempre son de un mismo hotel.


Para cada contrato podemos editar los siguientes valores:

- Título, que identifica el contrato
- Concepto de facturación (equivalente al centro de producción de QUoHotel)
- Iva incluido (siempre)
- Fechas de validez (estancia, desde - hasta)
- Booking window (desde - hasta)
- Condiciones especiales (texto libre que aparece en el pdf del contrato)
- Comentarios privados (texto libre que solo aparece al editar el contrato)
- Proveedor
- Destinatarios (agencias que pueden ver / comprar este contrato)
- Hotel
- Contrato que sobreescribe
- Ofertas relacionadas con este contrato
- Condiciones
  - Generales
    - Divisa
    - Tipo de precios (netos o brutos)
    - Comisión por fecha de estancia
    - Si es PVP obligatorio
    - Máx pax por reserva
    - Máx habitaciones por reserva
    - Máximo release salida (para liberar cupo)
    - Precios cero permitidos (caso garantías)
    - Ordenar los niños de menor a mayor edad (por defecto se ordenan de mayor a menor)
  - Precios
    - Para cada tarifa
      - Fehas de estancia
      - Precio por habitación
        - Precio por régimen
          - Precio estancia (importe, suplemento/descuento y porcentaje)
          - Precio régimen (importe, suplemento/descuento y porcentaje)
          - Descuentos pax, junior, niño y bebé
  - Estancia mínima
    - Fechas estancia (desde - hasta)
    - Mínimo moches (por debajo de este número de noches se aplica la restricción)
    - Dejar la reserva on request (si no se cumple)
    - Suplemento porcentual (si no se cumple)
    - Suplemento importe (si no se cumple)
    - Sobre que aplicar el suplemento (pax, habitación o reserva)
  - Release
    - Fechas estancia (desde - hasta)
    - Release mínimo
  - Entrada / salida / estancia obligatoria
    - Fechas estancia (desde - hasta)
    - Dejar la reserva on request si no se cumple
    - Días de la semana obligatorios
    - Aplicar a la entrada
    - Aplicar a la salida
    - Aplicar a la estancia
  - Suplementos
    - Fechas estancia (desde - hasta)
    - Si es opcional (por defecto su aplicación es obligatoria)
    - Si está sujeto a ofertas
    - Descripción del suplemento
    - Aplicación (por habitación, pax o reserva)
    - Alcance (por noche, por estancia completa)
    - Porcentaje suplemento
    - Importe suplemento
    - Proveedor
    - Órden aplicación
    - Clave facturación (equivalente al centro de producción de QuoHotel)
    - Habitaciones afectadas
    - Regímenes afectados
    - Aplica sobre adultos, juniors, niños y/o bebés
  - Galas
    - Fecha
    - Importe por pax
    - Descuentos para niños, juniors y bebés
    - Regímenes afectados
  - Cupo
    - Tipo de habitación
    - Fechas de estancia (desde - hasta)
    - Nº de habitaciones de este tipo
  - Condiciones de cancelación
    - Fechas de estancia (desde - hasta)
    - Release cancelación
    - Importe
    - Porcentaje
    - Nº primeras noches
  - Clausulas
    - Texto

Al grabar un contrato la plataforma realiza una serie de verificaciones para asegurarnos de que es correcto. En cualquier caso, el sistema solo nos avisa. Es nuestra decisión si finalmente grabamos el contrato (y lo ponemos a la venta) o no.

Para cada contrato podemos pedir una simulación, que nos enseñará un calendario con los precios estimados para una reserva de acuerdo con los parámetros que le indiquemos (ocupación y duración de la estancia). Esta funcionalidad es útil para comprobar si el contrato es correcto.


Ofertas
~~~~~~~~~~~~~~~~~~~~~~

Las ofertas (tanto las de tarifas como las de contratos) se unifican en la plataforma en una misma entidad oferta.

Para mantener las ofertas debemos utilizar la opción "Offers" del menú.

Aquí veremos un listado de las ofertas que hemos subido a la plataforma.

La plataforma soporta los siguientes tipos de oferta:

- 7 x 6
- Suite por habitación doble
- Descuento
- Precio
- Rolling early booking
- Pensión completa por media pensión
- Niños gratis


Todas las ofertas comparten una serie de campos:

- Un nombre, para identificarla
- Si debe incluirse en el pdf del contrato
- Si su aplicación implica prepago
- Si está activa
- Booking window (desde, hasta)
- Fechas de entrada
- Fechas de estancia
- Último checkout
- Mínimo noches para su aplicación
- Máx. noches para su aplicación
- Release mínimo para su aplicación
- Sobreescribe la estancia mínima del contrato (y valor)
- Sobreescribe el release del contrato (y valor)
- Sobre el precio de la habitación
- Sobre el precio del régimen
- Sobre descuentos
- Tiene extras (ofertas paquete)
- Descripción de los extras
- Hotel
- Contratos
- Agencias
- Habitaciones
- Regímenes
- Acumulable con (lista de ofertas)


Además, según el tipo de oferta:

- 7 x 6: número de noches a pagar y número de noches base
- Suite por habitación doble: habitación a paga y habitación utilizada
- Descuento: porcentaje y valor y, en el caso de ser un importe, la regla de aplicación (por pax, habitación o reserva y por noche o estancia completa)
- Precio: tarifas y descuentos a utilizar. Si un campo está en blanco se utilizan los valores indicados en el contrato
- Early booking: lista de porcentajes según release
- Pensión completa por media pensión: régimen pagado y régimen real
- Niños gratis: no tiene campos adicionales


Notar que algunas ofertas (como niños gratis) podemos indiacarlas utilizando las ofertas de tipo precio.

Call center
---------------------------

En este apartado encontraremos las funcionalidades relacionadas con el call center: mantenimiento de reservas y pagos.


Reservas
~~~~~~~~~~~~~~~~~~~~~~

Para revisar las reservas confirmadas en el sistema debemos utilizar la opción "Bookings" del menú.

Aquí encontraremos un listado con las reservas confirmadas, y podremos revisarlas y cancelarlas.

También podemos consultar disponibilidad y confirmar reservas, utilizando para ello la opción "New Booking".

A partir de aquí podremos consultar disponibilidad y confirmar reservas en nombre de cualquier agencia.

Esta opción la poodemos utilizar también para confirmar que los precios que hemos cargado son correctos, antes de publicar un contrato. Basta utilizar el check "Preview".



Pagos
~~~~~~~~~~~~~~~~~~~~~~

Utilizando la opción "Payments" del menú podemos consultar los pagos relacionados con las reservas.

Los pagos están disponibles únicamente en modo consulta. No podemos modificarlos, crear ni eliminar pagos.

De cada pago podemos ver la fecha y hora, la pasarela de pago, la reserva relacionada, el importe y el estado.

Más que pagos, podríamos llamarlos transacciones.

Los pagos se crean cuando una agencia (o un cliente de nuestra web) confirma una reserva y la agencia no está marcada como "crédito". En ese momento se crea un transacción o pago y se habilita un link a la pasarela de pago pertinente.

Esto significa que podemos ver varios pagos o transacciones relacionados con una reserva, que pueden estar confirmados o no.

Como hemos visto desde la plataforma no podemos crear pagos confirmados, pero sí que podemos crear una transacción y enviar el link a nuestros clientes.

Desde la plataforma podemos retroceder los pagos confirmados, aunque esta funcionalidad depende de si la pasarela de pago soporta esta funcionalidad.


Gestor de contenidos (CMS)
---------------------------

En este apartado encontraremos las funcionalidades relacionadas con el gestor de contenidos. Esto es, para la gestión de las webs.

Sitios web
~~~~~~~~~~~~~~~~~~~~~~

Para mantener nuestras webs deberemos seleccionar la opción "Webs" del menú.

Entonces veremos un listado con nuestras webs, con la posibilidad de crear nuevas webs, duplicarlas, eliminarlas, etc.

En el listado veremos para cada web su nombre, la url, y el estado.

Al entrar en una web podremos editar los siguientes valores a nivel general:

- Nombre, para identificar el sitio web
- Título, que aparece com título en el navegador
- Si está activa o no
- Urls asociadas con esta web
- Lista de repositorios Github de los cuales cogemos los contenidos
- TPV o pasarela de pago a utilizar para cobrar las reservas de esta web
- Authtoken, o credenciales utilizadas por esta web para atacar el motor de reservas

Y luego podemos indicar también los siguientes valores para cada página:

- En todas las páginas los campos relacionados con SEO y layout
  - Title
  - Keywords
  - Description
  - Author
  - Layout
- Home
  - Mensaje principal
  - Mensaje secundario
  - Lista de mensajes
    - Cabecera
    - Texto
- Ofertas
  - Lista de ofertas
    - Cabecera
    - Texto
- Tipos de habitación
  - No tiene campos propios
- Servicios
  - Lista de servicios
    - Cabecera
    - Texto
- Fotos
  - No tiene campos propios
- Contacto y mapa
  - Dirección
  - Teléfono
  - Email
- Reservas
  - Lista de mensajes
    - Cabecera
    - Texto

Temas
~~~~~~~~~~~~~~~~~~~~~~

Un tema es la apariencia que queremos darle a nuestra web. Consiste básicamente en definiciones de colores, fuentes, posicionamiento de los diferentes componentes de la página, imágenes y otros elementos que dan estilo a nuestra web.

Además de utilizar los temas proporcionados por Quonext, podemos añadir nuestros propios temas para nuestras webs.

Para ello seleccionaremos la opción "Themes" del menú.

Para cada tema podemos indicar:

- Nombre, para identificar el tema
- Si está activo o no
- Url del repositorio en Github que contiene los archivos del tema
- Rama del repositorio Github a utilizar
- Submódulo (o directorio) del repositorio Github a utilizar

Recordar que los temas podemos indicarlos luego en cada web, permitiéndonos cambiar el aspecto de nuestra web.

Recordar también que podemos crear nuestros propios temas, por ejemplo haciendo un fork de alguno de los repositiorios con los temas proporcionados por Quonext y modificando los ficheros que hagan falta.


Mapeado
---------------------------

En este apartado encontraremos las funcionalidades relacionadas con el mapeado entre códigos de QuoHotel y entidades de la plataforma.

Tripletas
~~~~~~~~~~~~~~~~~~~~~~

En QuoHotel utilizamos las tripletas para identificar los destinatarios de una tarifa o contrato.

Las tripletas son una combinación de agencia, touroperador y cliente.

En la plataforma QuoOn estas entidades no tienen relevancia, y simplemente tenemos agencias, a las que proporcionamos unas credenciales para acceder al sistema y comprar.

Es por ello que debemos mapear nuestras tripletas de QuoHotel a agencias de QuoOn.

El mantenimiento de este mapeado lo hacemos utilizando la opción "Triplets" del menú.

Para ello es necesario rellenar una tabla del tipo:


+----+---+---+---+---+
|Agencia|Touroperador|Cliente|Agencia en QuoOn|
+====+===+===+===+===+
|1|*|*|Muchoviaje|
+----+---+---+---+---+
|2|*|*|Logitravel|
+----+---+---+---+---+
|2|*|1|Logitravel DE|
+----+---+---+---+---+
|2|*|2|Logitravel ES|
+----+---+---+---+---+


Cuando los contratos se importan, o cada vez que modificamos este mapeado, se acualizan los contratos que tenemos en la plataforma con la agencia indicada.

En caso de que haya 2 mapeados que colisionen la plataforma puede utilizar cualquiera de ellos. Es nuestra reponsabilidad comprobar que no existen ambigüedades en el mapeado.


Tipos de régimen
~~~~~~~~~~~~~~~~~~~~~~
En la entidad tipo de régimen hay un campo en el que podemos indicar a que código de régimen (código y nombre multiidioma) pertenece nuestro tipo de régimen.

Los códigos de régimen son mantenidos por Quonext, en la modalidad compartida de la plataforma.

Tipos de habitación
~~~~~~~~~~~~~~~~~~~~~~

En la entidad tipo de habitación hay un campo en el que podemos indicar a que código de habitación (código y nombre multiidioma) pertenece nuestro tipo de habitación.

Los códigos de habitación son mantenidos por Quonext, en la modalidad compartida de la plataforma.

Divisas
~~~~~~~~~~~~~~~~~~~~~~

Las plataforma utiliza los códigos ISO 4217 (la versión de 3 letras. Ej: EUR, USD) para identificar las divisas. La plataforma espera que esos mismos códigos se utilicen en QuoHotel.

Los códigos de divisa son mantenidos por Quonext, en la modalidad compartida de la plataforma.


Administración
---------------------------

En este apartado encontraremos funcionalidades que afectan a la configuración general de nuestra plataforma.

TPV
~~~~~~~~~~~~~~~~~~~~~~

Para mantener las pasarelas de pago debemos seleccionar la opción "TPV" del menú.

Aquí podremos crear, modificar o eliminar las pasarelas de pago que utilizaremos para que nuestros clientes efectúen los pagos de sus reservas.

QuoOn soporta actualmente 3 pasarelas de pago:

- Sermepa
- Webpay
- Paypal

Para todas ellas podemos editar los siguientes campos:

- Tipo: Sermepa, Webpay, Paypal
- Nombre, para identificarla
- Email paypal: par identificar la cuenta en el caso de paypal
- Merchant code (sermepa y webpay)
- Merchant name (sermepa y webpay)
- Merchant secret (sermepa y webpay)
- Private key (webpay)
- Merchant terminal (sermepa y webpay)
- Action url
- Notification url
- Url OK
- Url ERROR

Salvo el nombre, todos los datos son proporcionados por la pasarela de pago o por Quonext.

Recordar que luego podemos indicar la pasarela de pago a utilizar en cada web.