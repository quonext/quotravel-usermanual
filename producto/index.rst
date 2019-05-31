########
Producto
########

Por producto nos referimos a los servicios que vendemos y cuyas condiciones mantenemos en QuoTravel.

Para cada producto normalmente introduciremos su definición, precios, condiciones y disponibilidad.

Aquí explicaremos toda la parte relacionada con la definición y carga de nuestro producto.

En QuoTravel podemos cargar cuatro tipos de producto:

- Genérico
- Hotel
- Traslado
- Excursiones y circuitos


El hotel, traslado y las excursiones / circuitos tienen una carga específica dadas sus características, mientras que el resto de productos (entradas, guía oficial, transporte, ...) los podemos meter como genéricos.

Para todos ellos podemos indicar una descripción, precios, paros y de ventas y cupos.

No obstante, veremos que la carga de producto se va especializando en cada caso concreto.


***********
Parte común
***********

En este apartado veremos la parte que es común a todos los productos.

Tarifario
=========

En cualquier momento podemos generar un tarifario para enviarlo a un potencial cliente o a un cliente ya existente.

El tarifario genera un pdf incluyendo los contratos de venta y el resultado de aplicar el margen pertinente a los contratos de compra.

Para generar el tarifario debemos seleccionar un cliente de referencia, para que el sistema sepa que margen debemos aplicar.

También podemos seleccionar que producto queremos que aparezca en el tarifario.

También podemos indicar un título para el tarifario, y un porcentaje y un importe adicionales a añadir a los precios.

El tarifario puede incluir precios de diferentes productos.

El resultado es un pdf con una portada y con un índice para que sea fácil inspeccionar su contenido y llegar a un producto concreto dentro del mismo.

Contrato
========

Todos los contratos tienen una parte común, que es la que describimos a continuación:

General
  Campos generales del contrato

  Título
    Título del contrato. Para identificarlo

  Tipo
    Venta o compra

  Contrato base
    Contrato que extiende. Podemos indicar también si lo extiende o si lo sobreescribe.
    Lo utilizamos para extender un contrato a la temporada siguiente, o para ofercer unas condiciones concretas a una agencia, o para un tour.

  Concepto de facturación
    Concepto de facturación a utilizar por defecto

  Línea de producto
    Según hemos definido en negocio. Lo utilizamos para aplicar markup y para saber si se puede vender

  Impuestos incluidos
    Si los precios expresados en este contrato son con iva incluido o no

  Moneda
    La moneda en que están indicados los precios

  Fechas validez
    Fecha de servicio. Desde - hasta, incluidas

  Booking window
    Fechas de confirmación de reserva. Desde - hasta, incluidas

  Condiciones especiales
    Texto que aparece en el pdf del contrato

  Comentarios internos
    Comentariso privados de uso interno

  Precio medio
    Campo de salida, para controlar si nos han subido los precios de un año a otro y como control adicional para verificar que los precios están bien introducidos.

Relaciones
  Quien nos provee estos servicios y a quien se los podemos vender

  Proveedor
    El partner que nos provee estos servicios

  Agencias
    Lista de agencias a las que se pueden frecer estas condiciones

  Mercados
    Lista de mercados que pueden comprar este producto

  Empresas
    Lista de empresas que pueden "ver" este contrato

Tour
  Campos relacionados con la venta de este servicio como parte de un tour

  Tours
    Lista de tours en los que se puede utilizar este contrato

  Desde nº pax
    Este contrato es válido para tours desde este nº de pax (incluido)

  Hasta nº pax
    Este contrato es válido para tours hasta este nº de pax (incluido)

Firma
  Datos relacionados con la firma que aperecen en el pdf del contrato

  Firmado en
    Donde se ha firmado el contrato

  Firmado por
    Nuestra empresa

  Firmante por el partner
    Quien por parte del partner

  Nuestro firmante
    Quien por nuestra parte

  Fecha de la firma
    Fecha de la firma

Comisiones
  En el caso de que este contrato indique precio brutos

  Reglas de comisiones
    Referencia a las reglas de comisiones a utilizar. Las reglas se han definido en el módulo de negocio. Si no se indican reglas de comisiones son precios netos.

Pago
  Datos relativos al pago

  Pago
    Términos de pago a utilizar en las reservas que utilicen este contrato, definidos en el módulo de negocio.

Condiciones de cancelación
  Datos relativos a la cancelación de reservas

  Reglas de cancelación
    Referencia a las condiciones de cancelación, definidas en el módulo de negocio.



Al grabar un contrato la plataforma realiza una serie de verificaciones para asegurarnos de que es correcto. En cualquier caso, el sistema solo nos avisa. Es nuestra decisión si finalmente grabamos el contrato (y lo ponemos a la venta) o no.

Para cada contrato siempre podemos duplicarlo, o duplicarlo para el año siguiente, incrementando los precios en un porcentaje o importe fijo.


Pdf contrato
============

Para todos los contratos podemos generar un pdf que podemos utilizar para firmarlo, para nuestro archivo, para revisar el contrato o para enviarlo a quien sea necesario.

La opción está disponible desde cualquier contrato.

Podemos también generar un pdf con varios contratos desde el listado de contratos, seleccionándolos y utilizando la opción "Generar pdf".

Tipo de producto
================

Nos sirve para agrupar los productos.

Lo podemos utilizar a la hora de hacer la reserva para llegar a producto que queremos contratar, y comparar precios.

También lo utilizamos en informes varios.

Para acada tipo de producto debemos indicar una descripción y una mara ara indicar si este tipo de prodycto está activo.

Los tipos de producto hotel, traslado y tour ya están predefinidos.

Segmentación
============

Para todos los contratos podemos indicar para que empresas, mercados, y agencias está disponible dicho contrato.

También es posible para cada contrato indicar que esas condiciones solo son aplicables cuando son utilizadas cuando son utilizadas en un tour concreto.

Estos parámetros se comprueban en tiempo de disponibilidad y para cada reserva que confirmamos.

Tarifas
=======

Para todos los contratos y, en algunos casos, líneas de precio podemos indicar para que tarifa son aplicables.

Casos típicos de tarifas pueden ser *estándar*, *estudiantes*, *imserso*, ....

En todas las reservas indicamos siempre la tarifa que queremos utilizar, con lo que sabemos que precios tenemos que aplicar.


Observaciones
=============

Podemos definir observaciones que deben aparecer automáticamente al hacer una reserva.

Para cada observación podemos indicar uns serie de filtros (que se utilizan si esta observación debe aparecer):

- Tipo de producto
- País
- Destino
- Resort
- Fecha inicio
- Fecha fín
- Activa

Y un texto en multiidioma.



Etiquetas
=========

En QuoTravel podemos crear etiquetas que podremos luego asociar a los productos (una excursión, un hotel, un genérico, ...) y utilizarlas como filtros en el proceso de reserva.

Para cada etiqueta podemos indicar:

- nombre
- descripción en multiidioma


Modelo de precios
=================

En QuoTravel podemos indicar precios netos y precios brutos con una comisión, tanto en la compra como en la venta.

En la parte de financiero veremos que las comisiones pueden ser tratadas como un descuento o como una comisión real, con su IVA correspondiente.

También podemos indicar que es pago directo en el hotel. En este caso nosotros simplemente informamos del precio al cliente, y facturamos después una comisión al hotel.

También es posible indicar en un contrato que es pago directo en referencia a contratos que el touroperador ha hecho directamente con el hotel, y en que nosotros simplemente gestionamos los cupos, paros de ventas etc a cambio de un handling fee.

El modelo de precios es independiente de la forma de pago.


Contratos venta y compra
========================

Para cualquier producto podemos definir contratos de venta y de compra.

Para vender nos basta haber cargado el contrato de venta, o haber cargado el contrato de compra y haber definido un margen para esa línea de producto.

Esto es, podemos vender sin que exista contrato de compra o sin que exista contrato de venta.

Realmente la venta es independiente de la compra, a no ser que en el contrato de venta explicitemos que, para ese contrato de venta, deben utilizarse exactamente uno o varios contratos de compra determinados.

También se puede dar el caso de que para algú producto solo existan contratos de compra. Sería el caso de un servicio de transporte ligado a una excursión, donde nunca vendemos el transporte sino que lo que vendemos es la excursión ya montada.

También puede suceder que exista únicamente el contrato de venta. Sería el caso en el que nosotros somos el productor de ese servicio, por ejemplo si somos nosotros los propietarios de los autocares.

En cada contrato siempre está disponible la rentabilidad del mismo. Esto es, el importe total de venta y el importe total de coste para las reservas asociadas a ese contrato.

También aparece el precio medio para poder compararlo rápidamente con el precio medio de las temporadas anteriores, para ver fácilente cuanto ha subido el precio y para ayudar a controlar que no ha habido fallos en la introducción de los precios de ese contrato.

También en el contrato (y en las ofertas) podemos indicar una forma de pago, que generará las entradas necesarias en la previsión de cobros y pagos.

En el contrato podemos indicar también unas condiciones de cancelación que sobreescribirán las condiciones de cancelación del proveedor.

Los contratos podemos exportarlos a excel, modificarlos e importarlos después.

Fichas
======

Para cualquier producto podemos definir una ficha que lo describe.

Las fichas de todos los productos las mantenemos en una tabla aparte, donde encontramos tanto la ficha de un hotel como la ficha de una excursión o circuito.

Grupos de características
-------------------------

Los grupos de características nos permiten agrupar los valores que aparecen en una ficha.

Para cada grupo indicamos simplemente un nombre.

Características
---------------

En Quotravel podemos definir las características que necesitemos para describir nuestros productos.

Para cada característica indicaremos simplemente un nombre y el grupo de características al que pertenece.


Ficha
-----

Para describir un producto utilizamos las fichas.

En la ficha podemos indicar

Descripción
  La descripción del producto en multiidioma

Coordenadas
  Latiud y longitud, para ubicar el producto

Imágenes
  Imágen principal y resto imágenes

Características
  Valores que damos a cada una de las caraterísticas de nuestro producto, según las hayamos definido previamente.

Grupos de claúsulas
-------------------------

Los grupos de clúsulas nos permiten agrupar un conjunto de claúsulas para añadirlas en grupo a un contrato.

Para cada grupo indicamos simplemente un nombre.

Claúsulas
---------

En Quotravel podemos definir las claúsulas que necesitemos para incluirlas después en nuestros contratos, de manera que aparecerán después en la última página del pdf del contrato.

Una claúsula esta compuesta por un nombre y un orden.

Disponiblidad
=============

Para todos los productos tenemos una pantalla de disponibilidad.

En esta pantalla mostramos un calendario donde juntamos precio, cupo, paros de ventas y release, para tener una vista clara de la disponibilidad de cada producto.

En el caso de hotel esta pantalla es más compleja ya que necesita un desglose por habitación y tipo de régimen.



*********
Genéricos
*********

Aquí veremos como cargar los precios de productos genéricos.

Los productos genéricos son los que no son hotel, traslado, excursiones ni circuitos, ya que para éstos existe una carga específica.

Realmente a las malas podríamos meter en genéricos cualquier cosa, incluso un hotel.


Son productos que tienen una descripción y un precio, control de cupo, paros de ventas y ofertas básicas.


Entrarían en esta categoría por ejemplo una entrada para un espectáculo o un coche de alquiler, para los que no hemos desarrollado una lógica de negocio específica dentro de Quotravel pero sobre los que podemos ejecutar un flujo completo de reserva, desde su contratación hasta la confirmación del servicio con el proveedor, incluyendo la valoración del servicio en base a una lista de precios básica.


Producto
========

Puede ser una entrada para un espectáculo, un coche de alquiler, una guía oficial, un transporte, etc.

Para cada producto debemos indicar a que tipo de producto pertenece, el nombre y si está activo o no.

Un producto se puede contratar si el tipo al que pertenece y eél mismo estan activos, si no existen paros de ventas que afecten a la reserva y si existe precio.


Extras
======

Un extra puede ser un suplemento, un descuento o una oferta.

Un extra puede ser obligatorio u opcional.

Los extras nos sirven para asociar un coste (o descuento) extraordinario a una reserva.

Para cada extra debemos indicar el producto al que está asociado y un nombre.

Los extras pueden no ser contratables directamente por el usuario, sino que los incluimos explícitamente en la reserva desde el call center.

En una reserva podemos indicar varios extras para un mismo producto.

Un extra se puede utilizar si está activo y si existe precio.



Paros de ventas
===============

Para cada paro de ventas indicamos un producto y unas fechas.

Los paros de ventas no actúan sobre contratos, mercados, etc como sí lo hacen en el producto de hotel.

Estudiar si lo ampliamos.


Cupo
====

Para cada producto podemos indicar un cupo para unas fechas determinadas.

Si en el contrato indicamos venta libre entonces no se compueba el cupo.


Release
=======

Para cada producto podemos indicar un release.

Lo indicamos a nivel de producto, en horas, y una hora límite.


Contrato
========

El contrato para los productos genéricos no añade nada al contrato base.

Podemos incluir en el mismo contrato precios para varios productos genéricos.

Precio producto
===============

Los bebés siempre son gratis.

Para cada precio de un producto indicamos:

Contrato
  El contrato al que está asociado este precio

Producto
  Producto al que se aplican estos precios

Variante
  Variante del producto a la que se aplican estos precios

Extra
  El extra al que se aplica este precio

Activo
  Si esta línea de precio está activa

Concepto de facturación
  Concepto de facturación a utilizar para estos precios

Texto
  Texto a utilizar en la línea de cargo que se generará para este precio.

Tour
  Información para incluir utilizar este producto en un tour concreto

  Tour
    El tour

  Zona
    Zona de precios del tour

  Variante
    Variante del tour

  Duración
    Duración del tour

  Desde pax
    Este precio es aplicable cuando el tour se realiza para un nº de pax igual o superior al indicado

  Hasta pax
    Este precio es aplicable cuando el tour se realiza para un nº de pax igual o menor al indicado

Inicio
  Fecha de servicio desde la que es aplicable este precio

Final
  Fecha de servicio hasta la que es aplicable este precio

Inicio booking window
  Fecha de reserva desde la que es aplicable este precio

Final booking window
  Fecha de reserva hasta la que es aplicable este precio

Precio por unidad
  Este precio se añadirá multiplicado por el nº de unidades

Precio por pax
  Este precio se añadirá multiplicado por el nº de pax cualesquiera sea su edad

Precio por bebé
  Este precio se añadirá multiplicado por el nº de bebés

Precio por niño
  Este precio se añadirá multiplicado por el nº de niños

Precio por junior
  Este precio se añadirá multiplicado por el nº de juniors

Precio por adulto
  Este precio se añadirá multiplicado por el nº de adultos

Precio por senior
  Este precio se añadirá multiplicado por el nº de seniors

Precio por unidad y día
  Este precio se añadirá multiplicado por el nº de unidades y por el nº de días

Precio por pax y día
  Este precio se añadirá multiplicado por el nº de pax cualesquiera sea su tipo y por el nº de días

Precio por bebé y día
  Este precio se añadirá multiplicado por el nº de bebés y por el nº de días

Precio por niño y día
  Este precio se añadirá multiplicado por el nº de niños y por el nº de días

Precio por junior y día
  Este precio se añadirá multiplicado por el nº de juniors y por el nº de días

Precio por adulto y día
  Este precio se añadirá multiplicado por el nº de adultos y por el nº de días

Precio por senior y día
  Este precio se añadirá multiplicado por el nº de seniors y por el nº de días

Orden
  Orden de aplicación de este precio

Precio final
  Si marcamos este campo esta es la última línea que vamos a mirar para calcular el precio.



El precio es el resultado de la aplicación de todas las líneas que coinciden con nuestra reserva, en el orden especificado.


*****
Hotel
*****

En este apoartado veremos como cargar el producto de hotel.


Hoteles
=======

Para mantener la lita de hoteles hay que utilizar la opción "Hotels" del menú.

Nos aparecerá en pantalla una lista de los hoteles que tenemos en base de datos, con varias opciones para afinar la búsqueda y, para cada hotel, un link para poder entrar y editarlo.

Para cada hotel podemos editar su nombre, categoría, localización, id en QuoHotel y edades para cada tipo de niño (bebé, niño y júnior).


Codificación general
====================

En este apartado podemos mantener algunos maestros que son comunes a tdos los usuarios de la plataforma.

Categorías de hotel
-------------------

Las categorías de los hoteles: 1 estrella, 2 estrellas, ...

Podemos encontrarlas en la opción "Coding -> Categories" del menú.

Para cada categoría podemos indicar un código y un nombre (multiidioma).


Códigos de habitación
---------------------

Los tipos de habitación: doble, doble vista mar, suite, ...

Podemos encontrarlos en la opción "Coding -> Room Codes" del menú.

Para cada tipo de habitación podemos indicar un código y un nombre (multiidioma).

Recordar que aquí definimos únicamente la descripción del tipo de habitación y que luego cada hotel define sus propios tipos de habitación con sus particularidades (ocupaciones máximas, descripción extendida, etc).


Códigos de régimen
------------------

Los tipos de régimen: solo alojamiento, media pensión, pensión completa, ...

Podemos encontrarlos en la opción "Coding -> Board Codes" del menú.

Para cada tipo de régimen podemos indicar un código y un nombre (multiidioma).

Cada hotel puede luego definir sus propios tipos de régimen, a los que habŕa que asignar uno de estos códigos, extendiéndolos al proporcionar una descripción detallada de lo que incluye cada régimen alimenticio.


Tipos de habitación
===================

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
================

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
===============

Para mantener los paros de ventas deberemos utilizar la opción "Stop sales" del menú.

Nos aparecerá un listado de los hoteles (solo hay un paros de ventas por hotel) y deberemos seleccionar uno de ellos.

A partir de aquí nos aparecerá una pantalla con los paros de ventas por día, marcando en color verde si ese día está abierto, en rojo si está cerrado y en amarillo si está cerrado parcialmente.

Recordar que los paros de ventas pueden hacerse por tipo de habitación y por contrato.

En la pantalla podemos utilizar uno de los filtros justamente para visualizar los paros que afectan a un tipo de habitación o contrato particulares.

Además de visualizar los paros de ventas, desde esta pantalla podemos abrir y cerrar ventas y ver el registro de todas las operaciones que se han realizado.

Recordar que el paro de ventas está relacionado con el cupo. Esto quiere decir que si cerramos un tipo de habitación "padre" cuyo cupo es consumido por otro tipo de habitación, también cerramos el tipo de habitación "hijo".


Inventario
==========

Para mantener los inventarios (o cupos) debemos utilizar la opción "Inventory" del menú.

Al contrario de lo que ocurre con los paros de ventas, sí que podemos tener varios cupos para un mismo hotel.

Recordar que, para cada hotel, siempre veremos al menos un cupo general, que es el cupo real del hotel. Luego podemos tener otros cupos que están ligados a uno o varios contratos, pero al final siempre se verifica que haya habitaciones disponibles en el cupo general del hotel.

En la pantalla de cupos vemos el cupo por día para cada tipo de habitación, y podemos filtrar los resultados por tipo de habitación.

En esta pantalla podemos además realizar operaciones sobre el cupo (añadir, fijar o restar cupo) y ver el registro de operaciones sobre el mismo.

Recordar que una habitación puede coger cupo de otra. Solo vemos el cupo real (el de la habitación "padre"), no veremos el cupo de las habitaciones "hijo".

Contratos
=========

Las tarifas y contratos que tenemos en QuoHotel se transforman en contratos en la plataforma.

Para mantener los contratos debemos utilizar la opción "Contracts" del menú.

A partir del listado podemos consultar los contratos, crear nuevos contratos o eliminarlos.

A partir del listado podemos pedir también un pdf con las condiciones del contrato en un formato imprimible, o para mandarlos a la agencia o tourooperador.

Recordar que los contratos están organizados jerárquicamente en la forma Hotel -> Contratos -> ... -> Contratos, de manera que podemos ir extendiendo contratos para crear un nuevo contrato que sobreescribe una parte de las condiciones del anterior.

Los contratos siempre son de un mismo hotel.


Para cada contrato, además de los valores habituales, podemos editar los siguientes valores:

- Hotel
- Ofertas relacionadas con este contrato
- Condiciones

  - Generales

    - Máx pax por reserva
    - Máx habitaciones por reserva
    - Máximo release salida (para liberar cupo)
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
    - Producto genérico / Proveedor
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


Para cada contrato podemos pedir una simulación, que nos enseñará un calendario con los precios estimados para una reserva de acuerdo con los parámetros que le indiquemos (ocupación y duración de la estancia). Esta funcionalidad es útil para comprobar si el contrato es correcto.


Ofertas
=======

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


Ofertas prepago
===============

Para indicar que una oferta es de prepago lo hacemos con los términos de pago.


Cupo de seguridad
=================

En QuoTravel podemos indicar cupos de seguridad para un contrato.

El cupo de seguridad es un cupo que se activa cuando existe un paro de ventas o cuando se ha pasado el release de un contrato.


Garantías
=========

En QuoTravel podemos gestionar contratos de garantía.

A no ser que indiquemos lo contrario, las garantías incluyen las 2 primeras personas de la habitación. Los extras (terceras personas) y las comidas no están incluidos.

Eso quiere decir que si hemos realizado un pago de una garantía y no indicamos lo contrario como veremos más adelante solo se utilizará dicho anticipo para las 2 primeras personas, no para los extras.

La rentabilidad de la garantía se puede consultar en cualquier momento, exactamente igual que con cualquier otro contrato.

Configuración en el contrato
----------------------------

Para ello indicaremos en el contrato:

Si es garantía
  Si marcamos esta opción este contrato es una garantía y se liquidará

Tipo de garantía
  Puede ser una garantía de ocupación o una garantía de producción.

  Para una garantía de ocupación lo que se garantiza es que habrá un nº de habitaciones reservadas.

  Para una garantía de producción lo que se garantiza es que llegaremos a una facturación determinada.

  En una garantía de producción el importe garantizado se expresa en forma de nº de habitaciones garantizadas por el precio de contrato.

Base liquidación
  Aquí indicamos la base de liquidación. Esto es, cada cuanto liquidamos esta garantía.

  Acepta los siguientes valores:

  - Diario
  - Semanal
  - Mensual
  - Fin de contrato
  - No se liquida

  El sistema comprobará con la frecuencia indicada si se ha cubierto la garantía y generará las líneas de cargo pertinentes por la parte no consumida de la garantía, que luego serán facturadas o utilizadas para validar las facturas del proveedor.

  La base de liquidación marca si podemos compensar días de baja ocupación con días en los que superemos la ocupación garantizada.

Cupo incluido en la garantía
  Aquí indicamos el cupo incluido en la garantía, que puede ser diferente del cupo que nos ha dado el hotel (garantía parcial).

  La liquidación de la garntía se hace en base a este cupo.

Extras incluidos
  Si es una garantía de producción (lo que se garantiza es un importe de facturación, no una ocupación) y marcamos este campo los extras (terceras personas, etc) se incluirán en la liquidación.



Liquidación de las garantías
----------------------------

QuoTravel va generando líneas de cargo a medida que van venciendo la base de liquidación.

En ese momento se valora si se ha cubierto la garantía y, si no es así genera las líneas de cargo necesarias hasta cubrirla.

En el caso de una garantía de venta esas líneas de cargo se facturarán.

En el caso de una garantía de compra esas líneas de cargo serán la previsión contra la que se validarán las fectauras que nos enviará el proveedor.


Búsqueda de cupo agotado
========================

En QuoTravel tenemos una herramienta para controlar si se ha agotado el cupo que hemos contratado con un hotel, para que podamos pedir más habitaciones si lo creemos necesario.

Dicho buscador nos pide el destino, el nº de habitaciones contratadas y el nº de habitaciones restantes.

El resultado es la lista de habitaciones y fechas para las que teníamos un cupo contratado igual o superior al indicado, y de las que restan un nº igual o inferior al indicado.

A partir de ahí podemos marcar las habitaciones que queramos y enviar un email a esos hoteles solicitando más habitaciones para esos periodos.


********
Traslado
********

En este apartado veremos como cargar el producto de traslados.


Puntos de recogida
==================

Los traslados siempre son de un punto de recogida a otro.

Para mantenerlos deberemos ir a Producto --> Traslados --> Puntos de recogida.

Para cada punto de recogida debemos indicar:

Tipo
  Tipo del punto de recogida.
  Puede ser

  - Aeropuerto
  - Puerto
  - Hotel
  - Punto de encuentro
  - Parada de bus
  - Localización
  - TBA
  - Villa
  - Agroturismo

  Este campo es solo informativo

Nombre
  Nombre con el que identificamos este punto de recogida.

  Puede ser el nombre del hotel, una carretera y punto kilométrico, un aeropuerto, etc.

Zona
  Zona en la que está ubicado este punto de recogida.

Punto alternativo para shuttle
  Si lo indicamos, los traslados de tipo shuttle dejarán o recogerán a los clientes en este otro punto.

Punto alternativo para no ejecutivos
  Si está marcado, el punto alternativo funciona también para los traslados privados no executive.

Intrucciones de llegada para shuttle
  Texto con instrucciones relativas a este punto de recogida para reserva de shuttle.

  Aparece después en el voucher y en la web, antes de confirmar la reserva.

Intrucciones de llegada para privados
  Texto con instrucciones relativas a este punto de recogida para reserva de privados y executive.

  Aparece después en el voucher y en la web, antes de confirmar la reserva.


Intrucciones de salida
  Texto con instrucciones relativas a este punto de recogida para salidas por este punto de traslado.

  Aparece después en el voucher y en la web, antes de confirmar la reserva.


Dirección
  Dirección en que está ubicado este punto de recogida.

Email
  Email para ponerse en contacto con este punto de recogida.

  Si está informado, a este email se envían los horarios de recogida.

Teléfono
  Por ejemplo el teéfono de la recepción del hotel.

  Se guarda a título informativo, por si hay algún problema con algún cliente.

Fax
  Por ejemplo el fax del hotel.

  Se empleaba para enviar los horarios de recogida al hotel.

  Actualmente en desuso.

Punto de salida
  Si está informado se pude salir de este destino a otro a través de este punto de recogida.

  Se utiliza por ejempo para los traslados del aeropuerto de Ibiza a hoteles de Formentera.

  En este caso es un traslado de un punto de recogida ubicado en un destino (ibiza) a un punto de recogida ubicado en otro destino (formentera).

  Se generan 3 traslados:

  - del aeropuerto de ibiza al puerto de ibiza (gateway de ibiza)
  - del puerto de ibiza al de formentera (gateways de ibiz y formentera)
  - del puerto de formentera (gw de formentera) al hotel



Rutas
=====

Las rutas agrupan las zonas físicas.

El sistema organiza los traslados separándolos por rutas.

Para cada ruta indicamos el aeropuerto al que pertenece y un nombre.

Las rutas solo son necesarias para organizar los traslados y para cacular los horarios de recogida.

Podríamos no definirlas, pero entonces el sistema no podría organizar los traslados correctamente ni calcular los horarios de salida.

En casos en los que simplemente trasladamos los servicios al transportista y él se encarga de organizar los buses y nos pasa después los horarios de recogida no haría falta indicar las rutas.

Paradas
=======

Las paradas colocan los puntos de recogida en el orden adecuado dentro de una ruta.

El orden se indica en el sentido de llegada (del aeropuerto hacia fuera), que se invierte en el caso de la salida.


Tiempos
=======

Aquí indicamos los tiempos de los trayectos, que utilzamos para calcular los horarios de recogida.

EL tiempo se indica desde una zona física a otra zona física, y se expresa en forma de minutos.

Para calcular la hora de recogida se van sumando los tiempos entre zonas físicas, 5 minutos para el trayecto entre 2 puntos de recogida dentro de la misma zona y 5 minutos por cada punto de recogida por el que pasamos.

Horarios
========

Hay casos en que se acuerda con el transportista unos horarios fijos para los shuttle.

Es el caso por ejemplo de Menorca.

En este caso se establece para cada ruta una lista de horas de inicio de la misma.


Vehículos
=========

Los traslados se realizan utilizando un vehículo.

Para mantenerlos debemos ir a Producto --> Traslados --> Vehículos.

Par acada vehículo debemos indicar:

Nombre
  Para identificar al vehículo

Mínimo pax
  Mínimo pax para utilizar este vehículo

Máximo pax
  Máxima capacidad del vehículo

On request
  Si lo marcamos, las reservas que utilicen este vehículo quedarán on request.

Zonas para precios
==================

Aquí definimos grupos de zonas que tienen el mismo precio, para simplificar la introducción de los mismos.

Para cada zona de precios debemos indicar:

Grupo
  Etiqueta que nos sirve para ayudarnos a visualizar las zonas de precios

Nombre
  Nombre que le damos a esta zona de precios, para identificarla.

Puntos de recogida
  Lista de puntos de recogida individuales que están incluidos en esta zona.

  Lo utilizarenmos cuando no queramos incluir todos los puntos de recogida de una zona física.

Zonas
  Lista de zonas físicas incluidas en esta zona de precio.


Suplementos
===========

También podemos definir suplementos para los traslados.

Para cada suplementos podemos indicar un nombre, que identifica al suplemento.

Para cada suplemento indicaremos también si es seeleccionable por el cliente, o si solo es utilizable desde el backoffice por nuestro personal.


Contratos
=========

Los contratos de traslados están formados por una cabecera y una lista de precios.

La cabecera del contrato de traslado tiene todos los campos comunes a todos los contratos.

Solo añade un campo para indicar el mínimo de pax por reserva, que es lo mínimo que vamos a cobrar cuando los precios están indicados por pax, y un campo para indicar un release.



Precios
=======

Para cada línea de precio de un contrato de traslado debemos indicar:

Contrato
  Contrato al que pertenece este precio

Tarifa
  Tarifa para la que se puede utilizar este precio

Extra
  Si es que esta línea de precio es aplicable a un extra

Tipo de traslado
  Puede ser SHUTTLE, PRIVATE, LUXURY, INCOMING y ADAPTED

Origen
  Punto donde recogemos a los clientes

Destino
  Punto donde dejamos a los clientes

Vehículo
  El vehículo para el que es válido este precio

Precio por
  Puede ser PAX o SERVICE

Desde pax
  Referente al nº de pax que hay en este vehículo, para establecer un escalado dentro de un mismo vehículo.

Hasta pax
  Referente al nº de pax que hay en este vehículo, para establecer un escalado dentro de un mismo vehículo.

Precio one way
  El precio indicado en la moneda del contrato

Precio ida y vuelta
  El precio indicado en la moneda del contrato

Orden
  Para indicar el orden de aplicación

Precio final
  Si marcamos este campo esta es la última línea que vamos a mirar para calcular el precio.



El precio es el resultado de la aplicación de todas las líneas que coinciden con nuestra reserva, en el orden especificado.



***********************
Excursiones y circuitos
***********************

En QuoTravel los tours son, en esencia, una composición de servicios con unas reglas especiales de disponibilidad (turnos, cupos).

Es en realidad un paquete.

Entran en esta categoría las excursiones y circuitos.

En QuoTravel las excursiones no son más que un caso simple de circuito, que básicamente no incluye estancia de hotel ni otras excursiones / circuitos.

Un circuito puede incluir otros circuitos / excursiones. Podemos crear incluso circuitos que extienden otros circuitos añadiendo más días antes y/o después del circuito base.

Luego a nivel de operativa podemos gestionar conjutamente aquellas partes que son comunes, con el consiguiente mejora operativa y ahorro de costes.


Las gestión de la venta de tickets (la gestión de los representantes con sus comisiones, liquidaciones, etc) no está ligado a las excursiones sino que es un punto independiente dentro de QuoTravel.

Los tours (circuitos y excursiones) tienen 3 partes diferenciadas:

- recogida de los clientes
- cuerpo de la excursión / circuito
- entrega de los clientes



Excursión / Circuito
====================

Para cada tour podemos definir:

Oficina
  Para saber quien gestiona esta excursión

Duración
  Este campo se tiene luego en cuenta al calcular algunos costes de la excursión. Puede ser una de las siguientes opciones:

  - Día entero
  - Medio día
  - Nocturna
  - Larga duración (circuito)

Variantes
  Lista de variantes disponibles para esta excursión. Afecta al precio y aparece después en los listados de la gestión operativa de la excursión.

Propia
  Si marcamos este campo entonces es una excursión propia. Nosotros organizamos la excursión.

Recogemos a los clientes
  Si marcamos esta opción pasamos a recoger a los clientes y luego los dejamos en su hotel / aeropuerto. Si no marcamos esta opción los clientes deben presentarse a la hora indicada en el punto de encuentro.

Utilizar el transporte para regoger a los clientes
  Si marcamos este campo recogeremos a los clientes y los dejaremos utilizando el transporte que hemos contratado para el tour

Punto de encuentro
  Punto de recogida donde comienza y termina el cuerpo de la excursión / circuito.

Venta libre
  No controlamos el cupo. Si una excursión no debe estar disponible paramos ventas.

Activa
  Si no marcamos este campo la excursión no estará a la venta.

Edades
  Aquí indicamos la edad a partir de la cual consideramos que una persona es niño y la edad a partir de la cual consideramos que una persona es adulto.

Esqueleto costes
  Aquí indicamos los servicios que necesita esta excursión. Por cada línea de coste podemos indicar:

  Tipo producto
    Puede ser cualquiera de los que hemos definido en QuoTravel.

  Categoría hotel
    En el caso de que sea una estancia en un hotel.

  Zona
    Zona donde debe estar ubicado el producto

  Producto
    Puede ser cualquier otro producto que hayamos definido en QuoTravel, incluso otra excursión / circuito.

  Proveedor
    Aquí indicamos el proveedor que nos puede proporcionar el servicio

  Pago contado
    Aquí indicamos si este servicio tiene que pagarlo la guía al contado, de manera que aparecerá en el resúmen previo de la excursión para entregarle el dinero a la guía (y que firmará conforme se le ha entregado), y posteriormente liquidarlo a la finalización de la misma.

  Coste por ticket
    Si marcamos este campo esperamos una línea por cada ticket en la factura del proveedor. Si no está marcado esperamos un coste por servicio.

  Venta por vehículo
    Solo para el cupo. No tiene ningún efecto sobre el precio.

  Precisa confirmación del proveedor
    Si marcamos este campo los servicios no quedan marcados como confirmados por el simple hecho de mandarlos al proveedor. El proveedor debe confirmar el servicio.

  Día
    En que día del circuito empieza este servicio

  Noches
    Nº de noches para este servicio

  Duración
    En el caso del transporte, el nº de horas que necesitamos el transporte

Turnos
======

Para cada excursión podemos definir diferentes turnos. Para cada turno podemos definir:

Touroperador
  Si este turno es exclusivo para una agencia / touroperador

Mercado
  Si este turno es exclusivo para un mercado concreto

Cupo
  Nº de plazas disponibles en este turno, por fechas

Release
  Antelación necesaria en días para poder hacer una reserva

Hora de inicio
  Hora de inicio del turno

Horarios de recogida
  No se puede vender una excursión si no hay hora de recogida. Aquí indicamos tanto punto de regogida como la hora. Así, para cada línea podemos indicar:

  Punto de recogida
    Se utilizan los puntos de recogida del módulo de traslados

  Hora
    Hora de recogida para este punto

  Orden
    Órden de recogida

Calendario
==========

Aquí indicamos la disponibilidad de esta excursión.

Para cada entrada del calendario podemos definir:

Fecha inicio y fin
  Fechas en las que es aplicable esta línea

Turnos
  Turnos disponibles en estas fechas. Recordar que los turnos pueden ser exclusivos para un touroperador o mercados.

Zonas
  Zonas desde las que se puede hacer la excursión.

Días de la semana
  Durante este periodo, la excursión solo está disponible en los días de la semana marcados


Extras
======

Los extras nos sirven, como en el caso del producto genérico, para indicar tanto suplementos como descuentos y ofertas.

Tiene los mismos campos que en el producto genérico pero, además, podemos indicar que su selección implica contratar un servicio adicional.



Tarifas de venta
================

Para cada excursión podemos definir el precio de venta.

Para definir el precio de venta rellenamos una lista donde, para cada línea, podemos indicar:

Touoperador
  Filtro. Si este precio es exclusivo para un touroperador

Tour
  Filtro. Tour al que corresponden estos precios

Variante
  Filtro. Variante del tour a la que corresponden estos precios

Zona
  Filtro. Para que zona de recogida es aplicable este suplemento

Hotel
  Filtro. Para que hotel de recogida es aplicable este suplemento

Extra
  Filtro. Si esta línea es aplicable para un extra concreto.

Fecha inicio / final
  Filtro. Fechas de la reserva (fecha de servicio) para las que es aplicable este precio

Booking window
  Filtro. Para que fechas de reserva es válida esta oferta

Concepto de facturación
  Acción. Entre otras cosas permite a QuoTravel saber que impuestos debe aplicar

Comisionable
  Acción. Aquí marcamos si este suplemento entra después en el cálculo de las comisiones

Descripción
  Acción. Descripción que aparecerá en la línea de cargo

Porcentaje
  Acción. % sobre el precio acumulado

Porcentaje
  Acción. % sobre el precio de la excursión, una vez aplicado el suplemento de zona?.

Precio adulto
  Acción. Importe con impuestos incluidos

Precio niño
  Acción. Importe con impuestos incluidos

Orden aplicación
  Filtro. En que orden debe aplicarse esta línea de precio

Sustituye al precio
  Acción. Si lo marcamos no se aplica en forma de suplemento, sino que sustituye al precio de la excursión una vez aplicado el suplemento de zona?


********************
Producto de terceros
********************

En QuoTravel podemos integrar producto de terceros.

De momento soportamos integraciones para la compra de camas de hotel.


Integraciones
=============

En este mantenimiento podemos crear todas las integraciones de compra que deseemos.

Para cada integración podemos definir:

Nombre
  Nombre de la integración, para identificarla después en listados, etc.

Línea de producto
  Para segmentar y para saber que markup aplicar a este producto.

Oficina
  Todas las reservas hechas a través de esta integración se asignarán a esta oficina.

URL base
  Url del traductor (o del tercero, si utiliza Easytravelapi)

Activa
  Para indicar si la integración está activa.

Provee hoteles
  Para inidicar si a través de esta integración podemos comprar hoteles.

Máx hoteles por petición
  Lo utilizamos para dividir y paralelizar las peticiones de disponibilidad. Su valor dependerá de cada proveedor.



Mapeados
========

En este mantenimiento podemos gestionar los mapeados que utilizamos en una integración.

Si no indicamos nigún mapeado el producto de este proveedor se mezclará con el resto de productos sumándose.

Si indicamos mapeados entonces el producto se integrará de una manera más inteligente, evitando duplicados.
