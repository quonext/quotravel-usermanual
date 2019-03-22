####################
Webs Cliente Final
####################

QuoTravel cuenta con una aplicación para la gestión de las webs de la agencia.

Estrictamente hablando, más que un gestor de contenidos es un gestor de webs.

Podemos crear todas las webs que queramos, asociarlas con urls, activarlas o desactivarlas a voluntad.

Podemos crear por ejemplo webs personalizadas para eventos, para clientes, o aprovechar este gestor de webs para tener diferentes versiones de nuestra web (por ejemplo para temporada alta y temporada baja).

Podemos aprovechar también el gestor para tener un borrador de la web sobre la que ir haciendo cambios, mientras mantenemos otra versión de la web en producción.

Internamente QuoTravel utiliza un generador de sitios estáticos (Hugo).

Esto proporciona varias ventajas sobre un gestor de contenidos clásico:

- La web es extremadamente rápida.
- Permite una personalización más fácil de nuestra web, además de ayudar a externalizar.

****************
Tipos de website
****************

Actualmente podemos crear los siguientes tipos de web:

=====================  ==============================================
Web de venta           Corporativa y venta a cliente final
Confirmación horarios  Conf. horarios recogida traslados salida
=====================  ==============================================


***********************
Web venta / corporativa
***********************

La web de venta puede suplir la función de web corporativa, web de venta a cliente final.

Permite proporcionar información a nuestros clientes, consultar disponibilidad y precios de nuestros productos y realizar reservas.

Las características de la web de venta son:

- Responsive: Las webs son responsivas y adaptadas a dispositivos móviles.
- SEO friendly: Optimización SEO, páginas mejor posicionadas y más fáciles de encontrar.
- CDN friendly: Aceleración de las webs y mejora la velocidad de navegación.
- CMS: Gestión de contenidos.
- Aceleradores reserva: Indicadores de habitaciones disponibles, ...
- Multilenguaje: Traducida y adaptada a distintos lenguajes.
- Webs muy rápidas: Sistemas de precargas de datos para un rápido funcionamiento ahorrando tiempos de accesos.
- Reserva de diferentes servicios: hotel, traslado, excursiones, circuitos y otros.
- Consulta y gestión de reservas.
- Integrada con pasarela de pago.

  - Sermepa.
  - Webpay.
  - Paypal.


Es importante recalcar que este sistema separa la parte de la vista de la parte de la lógica de negocio, pudiendo hacerse diversas configuraciones de vistas (veremos los Themes más adelante) y servicios prestados en cada web.

Información Corporativa
=======================
Gracias al generador de sistemas estatáticos (Hugo) y a la personalización através de nuestros temas el usuario puede añadir la información coorporativa que desee dentro de la web.
Para ello dentro de cada tema se le proporcionará una serie de lugares donde podrá mostrar esta información como por ejemplo en el pie de página, diversos artículos editables dentro de cada página, o páginas completas con información de la empresa.

De hecho mediante la configuración que separa la parte lógica de la parte visual es posible utilizar el generador de webs  para crear una web solo con información corporativa sin añadir ninguna funcionalidad de servicios, reservas, etc..

Estos contenidos se pueden gestionar directamente desde el backoffice de Quotravel, sin tener que modificar el código de la web.

Para ello cada vez que se genere una web, se crearán una serie de contenidos desde el propio backoffice. Vease apartado Gestión de contenidos

Servicios
=========

A parte de separar la lógica del diseño como hemos comentado anteriormente, los servicios  que se pueden reservar a traves de la web son módulos independientes unos de otros, esto quiere decir que puedo añadir en cada web los servicios que quiera o necesite dar soporte.
Estos servicios ofrecidos podrán ser propios de cada usuario que tenga cargados en su sistema o se puede dar la posibilidad de usar productos de terceros (por ejemplo Hotelbeds).

Hoteles
-------

Para la consulta / reserva de hoteles se seguiran los siguientes pasos.

Búsqueda destino
~~~~~~~~~~~~~~~~

Se intoducirán los siguientes datos.

.. figure:: /_static/cms/hotel/formulario.png
    :align: center
    :figwidth: 600px

- Destino: Para la búsqueda del destino tendremos cargado un portofolio de hoteles y se realizará una búsqueda con datos pre-cargados en el sistema haciendo que estas búsquedas sean extremadamente rápidas.
- Fechas: Entrada y Salida.
- Ocupación: Nº de habitaciones y Pax. por habitación.


Selección de hotel
~~~~~~~~~~~~~~~~~~

Se mostrará un listado de hoteles que cumplen los criterios de búsqueda mostrando el precio mas barato entre todas las opciones disponibles en el hotel, destacandose en el precio si existe alguna oferta aplicada.

.. figure:: /_static/cms/hotel/dispo.png
    :align: center
    :figwidth: 600px


En el caso de que un hotel no tenga disponibilidad para las fechas indicadas por el cliente, en vez de indicar el menor precio obtenido se indicará que existen disponibilidad para otras fechas mostrando en el paso posterior un calendario de disponibilidad.

Vease calendario de disponibilidad.


Selección Habitación/Régimen
~~~~~~~~~~~~~~~~~~~~~~~~~~~~

Una vez seleccionado el hotel pasaremos a la selección de habitación y regimen deonde se mostrará:

- Los detalles del hotel (Fotos, caracteristicas, descipción y localizacion en el  mapa).
- Calendario de disponibilidad, donde se pueden realizar cambios de fechas para la estancia.
- Listado de la ocupación seleccionada. Donde se mostrará los tipos de habitaciones disponibles junto con sus regimenes para cada opción para elegir la combinación deseada, cada opcion reflejrá su precio y si existe alguna oferta aplicada en el mismo.
  finalmente se reflejará el precio total de las opciones seleccionadas.

.. figure:: /_static/cms/hotel/rates.png
    :align: center
    :figwidth: 600px

Detalles de reserva
~~~~~~~~~~~~~~~~~~~
La siguiente pantalla nos mostrará tanto los detalles de la reserva como apartados para terminar de informar la reserva antes de su tramitación

.. figure:: /_static/cms/hotel/details.png
    :align: center
    :figwidth: 600px

Los detalles son:

    - Desglose de los precios por habitación
    - Gastos de cancelación,
    - Lineas de pago
    - Comentarios adicionales (estos incluyen comentarios del hotel, tasas aplicadas o cualquier información relevante no incluida en los apartados anteriores).

Datos a informar:

    - Tomador de la reserva (Obligatorio)
    - Ocupantes de las habitaciones ( En los casos que sean necesario no es obligatorio pero según que plataformas utilicemos o países de destino sería conveniente)
    - Peticiones especiales:

Confirmación de reserva
~~~~~~~~~~~~~~~~~~~~~~~

Se pasará a confirmar la reserva que nos devolverá el identificador de la misma seguidamente. La aplicación nos dará la posibilidad de realizar el pago mediante una pasarela de pago o añadir más servicios.

.. figure:: /_static/cms/hotel/confirm.png
    :align: center
    :figwidth: 600px


Traslados
---------

Para la consulta / reserva de hoteles se seguiran los siguientes pasos.

Búsqueda transfers
~~~~~~~~~~~~~~~~~~

Se intoducirán los siguientes datos:

.. figure:: /_static/cms/traslado/formulario.png
    :align: center
    :figwidth: 600px

- Destino/Hotel : Para la búsqueda del destino tendremos cargado un portofolio de hoteles y se realizará una búsqueda con datos pre-cargados en el sistema haciendo que estas búsquedas sean extremadamente rápidas
- Origen/Aeropuerto: Listado de aeropuertos disponibles.
- Fecha de llegada.
- Fecha de salida.
- Trayecto: Llegada, salida o ambos.
- Pax: Numero de personas
- Trnasporte Especial: Adaptado, Bicis o Palos de Golf, diferentes checks de selección.


Selección de Transfer
~~~~~~~~~~~~~~~~~~~~~

Se mostrará un listado de transportes que cumplen los criterios de búsqueda mostrando el precio mas barato entre todas las opciones disponibles.

.. figure:: /_static/cms/traslado/dispo.png
    :align: center
    :figwidth: 600px

En el caso de que no exista disponibilidad de transportes para las fechas indicadas por el cliente, en vez de indicar el menor precio obtenido se indicará que existen disponibilidad para otras fechas mostrando un calendario de disponibilidad.

vease calendario de disponibilidad.

Detalles de Traslado
~~~~~~~~~~~~~~~~~~~~

La siguiente pantalla nos mostrará tanto los detalles de la reserva como apartados para terminar de informar la reserva antes de su tramitación.

.. figure:: /_static/cms/traslado/details.png
    :align: center
    :figwidth: 600px


Los detalles son:
  - Comentarios:
  - Gastos de cancelación:
  - Totales: Desglose de importes


Datos a informar:
    - Tomador de la reserva (Obligatorio)
    - Teléfono de contacto:
    - Email de contacto:
    - Peticiones especiales.
    - Nº vuelo llegada.
    - Hora de llegada.
    - Fecha de llegada.
    - Nº vuelo salida.
    - Hora de salida.
    - Fecha de salida.

Confirmación de reserva
~~~~~~~~~~~~~~~~~~~~~~~
Se pasará a confirmar la reserva que nos devolverá el identificador de la misma seguidamente la aplicación nos dará la posibilidad de realizar el pago mediante una pasarela de pago o añadir más servicios.

Excursiones
-----------

Para la consulta / reserva de excursiones se seguiran los siguientes pasos.

Búsqueda excursiones
~~~~~~~~~~~~~~~~~~~~

Se intoducirán los siguientes datos:

.. figure:: /_static/cms/excursion/formulario.png
    :align: center
    :figwidth: 600px

- Destino: Para la búsqueda del destino tendremos cargado un portofolio de destinos y se realizará una búsqueda con datos pre-cargados en  le sistema haciendo que estas búsquedas sean extremadamente rápidas
- Fecha inicio: Fecha búsqueda para la excursón.


Selección de excursiones
~~~~~~~~~~~~~~~~~~~~~~~~

Se mostrará un listado de todas las excursiones que cumplen los criterios de búsqueda mostrando el precio mas barato entre todas las opciones disponibles para cada excursion. Se indicara en el precio si corresponde a alguna oferta

.. figure:: /_static/cms/excursion/dispo.png
    :align: center
    :figwidth: 600px

En el caso de no existir disponibilidad  de alguna excursión para las fechas indicadas por el cliente, en vez de indicar el menor precio obtenido se indicará que existen disponibilidad para otras fechas mostrando un calendario de disponibilidad.

vease calendario de disponibilidad.

Configurador de excursión
~~~~~~~~~~~~~~~~~~~~~~~~~

Una vez seleccionado la excursión deberemos configurar nuestras opciones y el sistema nos irá mostrando si existe disponibilidad para la excursión que vayamos configurando dinamicamente. La pantalla nos mostrara

.. figure:: /_static/cms/excursion/config.png
    :align: center
    :figwidth: 600px

- Detalle de la excursión: Imagenes, descripción , caracteristicas.
- Calendario de disponibilidad: Podremos ver las fechas disponibles de cada actividad e ir cambiando esta fecha.
- Configuración de la excursión: Se configuran las opciones de cada excursión, detalladas a continuación.

    - Hotel: Donde esta alojado cliente.
    - Idioma: Idioma del cliente para la excursión.
    - Variantes: Variante si existen sobre la misma excursión en la misma fecha. Se muetran los precios de cada variante.
    - Turno: diferentes turnos en caso de que los tenga.
    - Pax: incluye adultos, niños.
    - Suplementos: En caso de que la excursión posea complementos. ej Menus incluidos etc. mustra nombre del complemento precio y opcion para seleccionarlo.

- Desglose de precios: En este bloque se desglosan los precios de las opciones y suplementos seleccionados mostrando el total y si existe disponibilidad para la combinación.


Detalles de Excursión
~~~~~~~~~~~~~~~~~~~~~

La siguiente pantalla nos mostrará tanto los detalles de la reserva como apartados para terminar de informar la reserva antes de su tramitación.

.. figure:: /_static/cms/excursion/detail.png
    :align: center
    :figwidth: 600px

Los detalles son:
  - Comentarios.
  - Gastos de cancelación: en caso de que existiesen
  - Totales: Desglose de importes.

Datos a informar:
    - Tomador de la reserva (Obligatorio).
    - Numero de habitación.
    - Teléfono de contacto.
    - Email de contacto.
    - Peticiones especiales.

Confirmación de reserva
~~~~~~~~~~~~~~~~~~~~~~~

Se pasará a confirmar la reserva que nos devolverá el identificador de la misma seguidamente la aplicación nos dará la posibilidad de realizar el pago mediante una pasarela de pago o añadir más servicios.

Circuitos
---------

La tramitación de los circuitos a pesar de ser bastante parecida a la de excursiones se tratará a parte por su pequeñas particularidades.


Selección de circuito
~~~~~~~~~~~~~~~~~~~~~

En la página inical se mostrará un listado de todos los circuitos disponibles mostrando el precio mas barato entre todas las opciones disponibles para cada circuito, como en casos anteriores se destacará en el precio si existe una oferta aplicada

.. figure:: /_static/cms/circuitos/dispo.png
    :align: center
    :figwidth: 600px

En el caso de no existir disponibilidad de alguno de los circuitos para las fechas indicadas por el cliente, en vez de indicar el menor precio obtenido se indicará que existen disponibilidad para otras fechas mostrando un calendario de disponibilidad.

vease calendario de disponibilidad.

Configurador de circuito
~~~~~~~~~~~~~~~~~~~~~~~~

Una vez seleccionado el circuito deberemos configurar nuestras opciones y el sistema nos irá mostrando si existe disponibilidad para el circuito que vayamos configurando dinamicamente.

.. figure:: /_static/cms/excursion/config.png
    :align: center
    :figwidth: 600px

- Detalles del circuito: Imagenes, descripción , caracteristicas.
- Calendario de disponibilidad: Podremos ver las fechas disponibles de cada circuito e ir cambiando esta fecha.
- Configuracion del circuito: Se configuran las opciones de cada circuito, detalladas a continuación.

    - Variantes: Variante si existen sobre el mismo circuito en la misma fecha. Se muestran los precios de cada variante.
    - Pax: incluye adultos, niños.
    - Suplementos: En caso de que el circuito posea complementos. ej Menus incluidos etc. mustra nombre del complemento precio y opcion para seleccionarlo.


- Desglose de precios: En este bloque se desglosan los precios de las opciones y suplementos seleccionados mostrando el total y si existe disponibilidad para la combinación.


Detalles del circuito
~~~~~~~~~~~~~~~~~~~~~

La siguiente pantalla nos mostrará tanto los detalles de la reserva como apartados para terminar de informar la reserva antes de su tramitación.

.. figure:: /_static/cms/excursion/detail.png
    :align: center
    :figwidth: 600px

    Los detalles son:
      - Comentarios.
      - Gastos de cancelación: Si existiesen.
      - Totales: Desglose de importes.

    Datos a informar:
        - Tomador de la reserva (Obligatorio).
        - Numero de habitación.
        - Teléfono de contacto.
        - Email de contacto.
        - Peticiones especiales.

Confirmación de reserva
~~~~~~~~~~~~~~~~~~~~~~~

Se pasará a confirmar la reserva que nos devolverá el identificador de la misma seguidamente la aplicación nos dará la posibilidad de realizar el pago mediante una pasarela de pago o añadir más servicios.


Otros Servicios
---------------

En este apartado se aglomeran el resto de servicios que se pueden ofrecer que no esta englobado en ninguno de los servicios anteriores. (Venta de entradas, Rent a car, etc...).

Para la consulta / reserva de otros servicios se seguiran los siguientes pasos.

Búsqueda Otros servicios
~~~~~~~~~~~~~~~~~~~~~~~~

Se intoducirán los siguientes datos.

    - Destino: Lugar donde se desea la prestación del servicio.

.. figure:: /_static/cms/otros/formulario.png
    :align: center
    :figwidth: 600px


Para la búsqueda del destino tendremos cargado un portofolio de destinos y se realizará una búsqueda con datos pre-cargados en el sistema haciendo que estas búsquedas sean extremadamente rápidas.

Selección de Servicio
~~~~~~~~~~~~~~~~~~~~~

Se mostrará un listado de servicios que cumplen los criterios de búsqueda mostrando el precio mas barato entre todas las opciones disponibles para este servicio.

En el caso de no existir disponibilidad de alguno de los circuitos para las fechas indicadas por el cliente, en vez de indicar el menor precio obtenido se indicará que existen disponibilidad para otras fechas mostrando un calendario de disponibilidad.

vease calendario de disponibilidad.


Detalles de Servicio
~~~~~~~~~~~~~~~~~~~~

La siguiente pantalla nos mostrará tanto los detalles de la reserva como apartados para terminar de informar la reserva antes de su tramitación.

Los detalles son:
  - Desglose de los precios por Servicios.
  - Gastos de cancelación: si los hubiera.
  - Comentarios: sobre el servicio.

Datos a informar:
    - Tomador de la reserva (Obligatorio).
    - Datos de otros pax: En caso de ser necesario.
    - Lista de suplementos.


Confirmación de reserva
~~~~~~~~~~~~~~~~~~~~~~~

Se pasará a confirmar la reserva que nos devolverá el identificador de la misma seguidamente la aplicación nos dará la posibilidad de realizar el pago mediante una pasarela de pago o añadir más servicios.

Consulta Reservas
-----------------

El cliente accederá a cada una de sus reservas con la cuenta de correo con la que hizo su reserva y el localizador de la misma. A partir de esta reserva podra ver todos los servicios asociados al mismo localizador y/o cancelar algunos de las mismas.


Calendario de disponibilidad
============================

Durante la búsqueda de disponibilidad en los diferentes servicios ofrecidos, si no existiese disponibiliddad en alguno de los resultados obtenidos, el sistema ofrece la posibiliadad de mostrar la disponibilidad en fechas próximas a la indicada. Para ello se indicara en los productos (Hoteles, excursiones, circuitos, etc..) que se puede consultar otras fechas. Dando paso al calendarios de fechas.

Este calendario mostrará las fechas próximas a la seleccionada por el cliente pintando en diferentes colores la disponibilidad de los servicios solicitados.

Es importante señalar que este servicio de calendario solo será posible con los productos propios que tenga el cliente cargados en QuoTravel, para productos de terceros no tendremos esta posibilidad disponible.


Configuración
=============

Como se indica en este capitulo la generación de las distintas webs que puede hacer cada cliente se realizará desde el backoffice directamente sin llegar a ser necesario tocar el código de esta web directamente. A continuación  mostraremos los pasos necesarios para crear una web.

Creación de webs
----------------

Iremos al menu del Backoffice  CMS / Gestion de Webs Externas --> Webs Venta --> Añadir web e informaremos los siguientes campos:


- Nombre del sitio: Nombre de la web para identificarla y nombre del título de la web.
- Url externa: URL del dominio externo que tendra nuestra web.
- Tema: Se seleccionará un tema de un listado de temas disponibles tanto propios de Quotravel como generados por el usuario( Estos últimos disponibles solo para el usuario que los crea). ver Creación de temas.
- Activa: Seleccionaremos si la web estará disponible o no para su acceso
- Idiomas: Se indicarán los distintos idiomas en los que estará disponible la web de un listado de lenguajes disponibles en la plataforma.
- Servicios: Aquí seleccionaremos de un listado cuales son los servicios que se prestarán en la web. (Hoteles, excursiones, circuitos, traslados, otros).

Una vez añadido estos datos tendremos dos opciones.

- Guardar: Guarda los datos de la página y genera el código sin desplegar.
- Guardar y desplegar: A parte de los pasos anteriores se realizará el despliegue de la web. Ver despliegue.


Gestión de contenidos
~~~~~~~~~~~~~~~~~~~~~

Dentro de cada web tendremos una serie de contenidos disponibles que serán totalmente editables por el usuario desde el backoffice para ello tendrá un aparatado dentro de la configuración de gestión de contenidos, donde se irán dando de alta los diferentes artículos con estos campos.

- Idioma: Idioma del contenido, seleccionado de un listado de lenguajes disponibles.
- Título: Título del artículo en el idioma seleccionado.
- Contenido: Contenido del artículo en el idioma indicado.
- Tipo: Seleccionaremos el tipo de artículo de un desplegable y según esto ira situado en diferentes sitios de la web (Hotel, traslados, excursiones, circuitos, otros, Pie de pagina, Inicio. etc..).
- Activo: Indicará si el artículo esta activo para publicarse o no. (En cada página se podran mostrar un número de artículos máximo según el tema seleccionado con esta opcion podremos tener los articulos guardados que deseemos y activar solo los que queramos mostrar).
- Peso: Es un indicativo númerico en relación con el apartado anterior para colocar los artículos según orden de importancia.

Cuando se realice el despliegue de la página el sistema irá recopilando los distintos ficheros de contenidos e introduciendolos en la web.


**********************************
Web confirmación horarios recogida
**********************************

También configuraremos aquí la web de confirmación de horarios de recogida.

La web para la confrimación de horarios de recogida permite a nuestros clientes de traslado conocer su hora de recogida, para los traslados de salida.

El cliente proporciona el identificador de su reserva y la fecha del traslado y, si son correctos, se le informa de la hora de recogida.

Esto queda registrado en el servicio, de manera que podemos saber que el cliente vió la hora de recogida utilizando la web.

Al igual que pasa con la web de venta, es totalmente personalizable utilizando los temas que veremos a continuación.


.. figure:: /_static/cms/horarios/horario1.png
    :align: center
    :figwidth: 600px


.. figure:: /_static/cms/horarios/horario2.png
    :align: center
    :figwidth: 600px


*****
Temas
*****

Los temas nos permiten cambiar la imagen de nuestra web. Gracias a Hugo el sistema gestor de contenido que utilizamos que permite la carga de diferentes temas y a la separación de la lógica de negocio podemos implementar el mismo sitio web con diferentes aspectos visuales mediante el desarrllo de diferentes temas.

Los temas se alojan en Github, y podemos crear tantos como queramos para la personalización lde las diferentes webs de cada usuario. Incluso permite a los clientes con equipos de IT generar sus propios temas desde cero o extendiendo los temas disponibles.

Esto nos permiten personalizar nuestra web no solo con css y javascript, sino que también nos permiten modificar el html mismo de la página, pudiendo cambiar la estructura de la mismo y no solo los estilos visuales.
Se puede cambiar menus, que servicios ofrecer, número de artículos a mostrar y disposición de los mismos.

Ejemplos de la misma web con distintas plantillas.


.. figure:: /_static/cms/theme/web1.png
    :align: center
    :figwidth: 600px

.. figure:: /_static/cms/theme/web2.png
    :align: center
    :figwidth: 600px


Creación temas
==============

Para crear temas para las diferentes webs que queramos generar habra que tener en cuenta una seria de generalidades a mantener de cara al desarrollo de las plantillas.

En primer lugar tenemos que tener claro que la gestión de temas se realiza mediante el gestor de contenidos Hugo con lo cual tendremos que basarnos en el modelo estructural de este. Otro aspecto importante a tener en cuenta es que tanto el diseño de los temas de Quotravel como el de los componentes de los diferentes servicios (Hotel, traslados, ...) están diseñados con el framework Materialize por lo cual es conveniente al menos incluir los esstilos para la correcta visualizacion de las diferentes app.

Para la creación de temas se puede realizar empezando complentamente desde cero y extendiendo alguno de los temas propios de Quotravel disponibles en github y haciendo una copia de los mismos.

Básicamente una vez teniendo el diseño web de la página siguiendo la estructura de Hugo, simplemente habría que

Añadir una etiqueta con un identificador específico para cada uno de los servicios de la app. Estas etiqietas son

.. code-block:: html
    :linenos:

    <div id="hotel"></div>
    <div id="traslados"></div>
    <div id="circuitos"></div>
    <div id="excursion"></div>
    <div id="otros"></div>
    <div id="reservas"></div>

Finalmente solo quedaría añadir en cada web las referencias a los script que contienen las aplicaciones anteriores.

- CSS:

.. code-block:: html

   <link rel="stylesheet" href="/css/{{.Params.appdest}}.app.css">
   <link rel="stylesheet" href="/css/{{.Params.appdest}}.generic.css">

- JS:

.. code-block:: html
    :linenos:

    <script type="text/javascript" src="/js/{{.Params.appdest}}.manifest.js"></script>
    <script type="text/javascript" src="/js/{{.Params.appdest}}.vendor.js"></script>
    <script type="text/javascript" src="/js/{{.Params.appdest}}.app.js"></script>

Estas referencias son paquetes que se instalarán automaticamente durante el despliegue de la web.


Una vez creado el tema en el propio Backoffice deberemos subir el tema en el apartados de temas para poder seleccionarlo en el momento de la creación de las webs. Este tema estará solo disponible para su creador, es decir, a cada usuario le aparecerán los temas propios de Quotravel, mas los temas propios que suba en su cuenta.

Para subir los temas accederemos al menu del Backoffice  CMS / Gestion de Webs Externas --> Añadir tema.

*****************
Despliege de Webs
*****************

Para el despliegue de las webs generadas a producción utilizaremos Netlify, que es una plataforma que nos permite realizar depliegues continuos de nuestros sitio webs a partir de nuestros repositoriso en github. El despliegue se hará generalmente desde el backoffice accediendo a el menu CMS / Gestion de Webs Externas --> Webs Venta. Seleccionamos la web que queremos desplegar y pulsamos el botón de guardar y desplegar.

Aún así es posible realizar este despliegue a mano teniendo en cuenta que Netlify despliega nuestra aplicación web desde un repositorio Github una vez que tengamos nuestra pagina lista podemos acceder a Netlify indicandole a partir de que repositorio queremos desplegar y este generará la web proporcionandonos una URL interna de netlify.

************
Unit Testing
************

El sistema esta montado basandose en Unit Testing. Resumidamente es una técnica que divide un proyecto en unidadades independientes para comprobar posteriormente mediante procesos de pruebas que funcionen correctamente y eficientemente por separado cumpliendo una serie de requisitos.

- Automatizable: No debe requerirse una intervención manual.
- Completas: Deben cubrir la mayor cantidad de código.
- Reutilizables: No se deben crear pruebas que sólo puedan ser ejecutadas una sola vez.
- Independientes: La ejecución de una prueba no debe afectar a la ejecución de otra.

Esto permite realizar una integración continua, es decir, cada vez que modifiquemos algo en el sistema (Webs, aplicaciones de servicios). Se ejecutan automaticamente una serie de test de pruebas que aseguran el correcto funcionamiento de la aplicación y que los cambios realizados no afectan a otras partes del sistema.


**********************************************
Instalación de motores de reservas en terceros
**********************************************

Los motores de reservas utilizados en la web de venta, estan publicados individualmente como paquetes npm, esto quiere decir, que existe un paquete independiente para cada uno de ellos para poder ser utilizados de forma totalmente autónoma. Los paquetes actualmente publicados son:

    - Hotel: publicado como quotravel-hotel-engine
    - Traslado: publicado como quotravel-transfer-engine
    - Excursión: publicado como quotravel-excursion-engine
    - Circuito: publicado como quotravel-circuit-engine
    - Genericos: publicado como quotravel-generic-engine
    - Consulta de reservas: publicado como quotravel-query-engine

PROXIMAMENTE: Debido al uso extendido del framework Boostrap tambien se ha lanzado una versión de los distintos motores sobre boostrap para complementar la aplicación. Estas publicaciones sobre boostrap estan publicadas con los siguientes nombres:

    - Hotel: publicado como quotravel-hotel-bs-engine
    - Traslado: publicado como quotravel-transfer-bs-engine
    - Excursión: publicado como quotravel-excursion-bs-engine
    - Circuito: publicado como quotravel-circuit-bs-engine
    - Genericos: publicado como quotravel-generic-bs-engine
    - Consulta de reservas: publicado como quotravel-query-bs-engine

.. note:: La versión de boostrap empleada para esta adaptación es 4.3.1. Vease la compatibilidad con otras versiones del `framework <https://getbootstrap.com/docs/4.0/migration/>`_

A continuación desarrollaremos los pasos a seguir para para la instalación completa de la aplicación desde la instalación del núcleo de la aplicación a su personalización pasando por algunos detalles necesarios para su correcto funcionamiento. AL final del apartado podremos encontrar un html ejemplo de la configuración básica de la página que contenga cada motor.

Instalacion del motor
=====================

El núcleo o core de cada uno de los motores de reserva mencionados en el punto anterior consta de los siguientes ficheros principales para el funcionamiento de cada una de las app, divididos en 2 css y 3 js.


====== ================
 CSS    \*.app.css
        \*.generic.css
 JS     \*.manifest.js
        \*.vendor.js
        \*.app.js
====== ================

Cada fichero anterior tendrá la nomencaltura correspondiente al motor que estemos utilizando según la siguiente tabla:

================= ============
Hotel             hotel
Traslado          traslado
Excursión         excursion
Circuito          circuito
Genericos         otros
Consulta reservas reservas
================= ============

Es decir si decidimos instalar el motor de traslados los ficheros anteriores serian:

====== ======================
 CSS    traslado.app.css
        traslado.generic.css
 JS     traslado.manifest.js
        traslado.vendor.js
        traslado.app.js
====== ======================

Gracias al uso de paquetes npm tendremos 3 opciones para utilizar estos objetosen nuestros proyectos web:

Instalando el paquete npm en nuestro proyecto web
-------------------------------------------------

Tomando como ejemplo la instalación del motor de reservas de traslados.

	npm i quotravel-transfer-engine

Este comando instalará la siguiente estructura de carpetas en nuestro proyecto y lo único que tendremos que hacer será referenciar en nuestro html las rutas locales donde se instaló el paquete:





Utilizando los enlaces al CDN de npmjs
--------------------------------------

Fichero CSS:

.. code-block:: html

    <link href=https://unpkg.com/quotravel-transfer-engine@0.0.2/static/css/traslado.app.css rel=stylesheet>
    <link href=https://unpkg.com/quotravel-transfer-engine@0.0.2/static/css/traslado.generic.css rel=stylesheet>

Ficheros JS:

.. code-block:: html
    :linenos:

    <script type=text/javascript src=https://unpkg.com/quotravel-transfer-engine@0.0.2/static/js/traslado.manifest.js></script>
    <script type=text/javascript src=https://unpkg.com/quotravel-transfer-engine@0.0.2/static/js/traslado.vendor.js></script>
    <script type=text/javascript src=https://unpkg.com/quotravel-transfer-engine@0.0.2/static/js/traslado.app.js></script>


Descarga de ficheros alojandolos en nuestro servidor directamente.
------------------------------------------------------------------

Se descargan los ficheros mencionados anteriormente tanto los ficheros .CSS como los 3 . JS guardandolos en el servidor local y haciendo referencia a ellos.


.. note:: Indepentientemente del sistema utilizado de los 3 anteriores es muy importante el orden en el que se incluyan los ficheros JS para su correcto funcionamiento:

          #. manifest.js
          #. vendor.js
          #. app.js

Configuración de dependencias
=============================

Aparte de la configuracion del motor de reservas es necesarío incluir una serie de librerias y scripts para el correcto funcionamiento de la app. Algunas de estas librerias se han sacado fuera para poder personizarlas y/o reutilizarlas en el resto de la web.

Framework CSS
-------------

La implementación de los motores de reservas estan realizados sobre Materialize un framework css muy potente y versatil y es la opción principal para la implementación. Debido al uso extendido del framework Boostrap tambien se ha lanzado una versión sobre boostrap para complementar la aplicación.

Materialize
~~~~~~~~~~~

Para la correcta visualización de la app sobre el framework de Materialize es imprescindible incluir tanto la hoja de estilo como el fichero js de Materialize. que serían las siguientes líneas.

.. code-block:: html
    :linenos:

    <link rel="stylesheet" href="https://cdnjs.cloudflare.com/ajax/libs/materialize/1.0.0-beta/css/materialize.min.css">
    <script src="https://cdnjs.cloudflare.com/ajax/libs/materialize/1.0.0-beta/js/materialize.min.js"></script>

Como veremos en apartados posteriores para la personalización del diseño de las apps podremos modificar el sass de Materialize e incluir los ficheros resultantes de esta modificacion.

Boostrap (Proximamente)
~~~~~~~~~~~~~~~~~~~~~~~

Como se ha comentado anteriormente se ha desarrollado una versión de los motores en Boostrap para poder integrar de una manera optima en sitios web basados en este framework evitando asi conflictos provocados por el uso de distintos frameworks css en la misma web.
Para incluir los ficheros necesarios para añadir Boostrap solo habría insertar las siguientes líneas en vez de las indicadas en el apartado de Materialize.


- CSS:

.. code-block:: html
    :linenos:

    <link href="https://stackpath.bootstrapcdn.com/bootstrap/4.3.1/css/bootstrap.min.css" rel="stylesheet" integrity="sha384-ggOyR0iXCbMQv3Xipma34MD+dH/1fQ784/j6cY/iJTQUOhcWr7x9JvoRxT2MZw1T" crossorigin="anonymous">

- JS:

.. code-block:: html
    :linenos:

    <script src="https://code.jquery.com/jquery-3.3.1.slim.min.js" integrity="sha384-q8i/X+965DzO0rT7abK41JStQIAqVgRVzpbzo5smXKp4YfRvH+8abtTE1Pi6jizo" crossorigin="anonymous"></script>
    <script src="https://cdnjs.cloudflare.com/ajax/libs/popper.js/1.14.7/umd/popper.min.js" integrity="sha384-UO2eT0CpHqdSJQ6hJty5KVphtPhzWj9WO1clHTMGa3JDZwrnQq4sF86dIHNDz0W1" crossorigin="anonymous"></script>
    <script src="https://stackpath.bootstrapcdn.com/bootstrap/4.3.1/js/bootstrap.min.js" integrity="sha384-JjSmVgyd0p3pXB1rRibZUAYoIIy6OrQ6VrjIEaFf/nJGzIxFDsf4x0xIM+B07jRM" crossorigin="anonymous"></script>


Iconos y fuentes
----------------

Iconos para la app.

.. code-block:: html
    :linenos:

    <link rel="stylesheet" href="https://use.fontawesome.com/releases/v5.4.1/css/all.css" integrity="sha384-5sAR7xN1Nv6T6+dT2mhtzEpVJvfS3NScPQTrOxhwjIuvcA67KV2R5Jz6kr4abQsz" crossorigin="anonymous">
    <link href="https://fonts.googleapis.com/icon?family=Material+Icons" rel="stylesheet">

Mapbox
------

Libreria para utilizacion de la API de MapBox para renderizar mapas y localizaciones en la APP añadir solo en: Hoteles, Excursiones, Circuitos y Otros.

.. code-block:: html
    :linenos:

    <link href='https://api.tiles.mapbox.com/mapbox-gl-js/v0.50.0/mapbox-gl.css' rel='stylesheet' />

Para el uso de Mapbox es necesario tener un token proporcionado por `Mapbox <https://www.mapbox.com/pricing/>`_ que se configura posteriormente en el apartado de variables globales.



Configuración de variables globales
===================================

El sistema necesita configurar una serie de variables globales tanto para poder configurar la propia app como para mantenerse en contacto con el contendor web que embeba esta app. Existen una serie de variables comunes a todos los motores de reserva y otros específicos de cada motor. Para ello insertaremos el siguiente Script que iremos desglosando a continuación

.. code-block:: html
    :linenos:

    <script>
        //Setup Localstorage:

        // EasyTravelApi implementation server (DEMO URL change for own API URL) COMMON
        localStorage.setItem("baseurl", 'https://demo.quotravel.eu/resources/eyAiY3JlYXRlZCI6ICJUaHUgRGVjIDI3IDE1OjE5OjQ0IENFVCAyMDE4IiwgInVzZXJJZCI6ICJ3ZWJ4IiwgInBhcnRuZXJJZCI6ICI0In0=');

        //language (ISO code)  Supported => es, en  Spanish default in no language COMMON
        if (!localStorage.getItem("language")) {
            localStorage.setItem("language", 'es');
        }

        //main url site COMMON
        localStorage.setItem("siteurl", 'http://www.mywebsite.com')

        //contact mail ONLY TRANSFER
        localStorage.setItem("contactmail",'demo@contactemail.com')

        //Creating golbal variable
        var globaldata = {
        baseurl: localStorage.getItem("baseurl"), // EasyTravelApi implementation server. COMMON
        siteurl: localStorage.getItem("siteurl"), // URL Base from the site. COMMON
        language: localStorage.getItem("language"), //Current Language for ML system (ISO code). COMMON
        contactmail: localStorage.getItem("contactmail"), // Email for contact when bikes on transfer. TRANSFER ONLY
        };
    </script>

Añadiendo motores al html
=========================

Finalmente como vimos en el apartado anterior de creaciones de temas una vez añadidas todas las dependencias necesarias para utilizar los motores solo quedaría incristar el motor dentro de nuestro html. Para ellos simplemente basta con añadir las siguientes etiquetas html donde queramos incluirlos.

.. code-block:: html
    :linenos:

    <div id="hotel"></div>
    <div id="traslados"></div>
    <div id="circuitos"></div>
    <div id="excursion"></div>
    <div id="otros"></div>
    <div id="reservas"></div>

Aunque los motores se adaptan al diseño de cualquier web en las que sean incrustadas es aconsejable que las etiquetas anteriores esten contenidas dentro de un contenedor de materialize para mantener su estructura

<div class="container"></div>

.. code-block:: html
    :linenos:

    <div class="container">
        <div id="hotel"></div>
    </div>

Personalización del motor
=========================


Modificación del sass
---------------------

Los frameworks CSS que utilizamos tienen disponible su codigo SCSS y SASS para poder personalizar sus estilos css. Modificando estos estilos y sobreescribiendo las hojas css tanto de materialize como boostrap tendremos una potente herramienta para cambiar los estilos fácilmente.
En las siguientes direcciones tenemos acceso al SASS de cada framework

Materialize:

https://materializecss.com/getting-started.html

Boostrap:

https://getbootstrap.com/docs/4.0/getting-started/theming/#sass

Sobreescribir estilos
---------------------

Es posible crear nuestras propias hojas de estilos y sobreescribir los estilos aplicados por los framework de css pudiendo hacer modificaciones puntuales en los estilos aplicados en los motores de reserva. Es importante tener en cuenta el orden de colocación de las hojas de estilos para un correcto funcionamiento de las mismas.


