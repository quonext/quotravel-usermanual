.. QuoOn user manual documentation master file, created by
   sphinx-quickstart on Tue Dec  5 09:46:59 2017.
   You can adapt this file completely to your liking, but it should at least
   contain the root `toctree` directive.

Acceso para DevOps
=============================================

El acceso para devops tiene una url propia.

En el caso del entorno de test esta url es http://admin.test.quoon.net .

========  =====
User      admin
Password  1
========  =====

.. warning:: deberíamos poner el entorno de demo. Pendiente de conseguir servidor.


La funcionalidad que el usuario de una agencia puede encontrar en este acceso queda resumida en el siguiente diagrama:

.. figure:: /_static/img/backoffice/back03.png
   :align: center
   :figwidth: 600px

En los siguientes capítulos revisaremos cada una de las funcionalidades que aparecen en el diagrama.


Configuración inicial de la plataforma
--------------------------------------

La plataforma ya viene configurada con un conjunto de valores por defecto que deberían ser correctos.


Dar de alta un cliente
---------------------------


Para dar de alta un nuevo cliente deberemos seleccionar la opción "Agents" del menú.

Una vez que veamos el listado de agentes deberemnos seleccionar la opción "Create new agent".

Deberemos rellenar los datos que nos pide y seleccionar "Ok". Esto creará un agente y un proveedor configurados con valores por defecto.

Se abrirá el mantenimiento del agente, donde podremos modificar cualquier valor y donde veremos el id del agente.

Ese id del agente es el que debemos utilizar cuando instalemos el agente en el servidor de NAV del cliente.


.. _target_monitor:

Monitorización
---------------------------

La monitorización de la plataforma tiene básicamente 2 componentes: un sistema de alarmas y un panel de control.

El panel de control se encuentra en http://health.quoon.net/


.. figure:: /_static/img/backoffice/mon01.png
   :align: center
   :figwidth: 600px

En el panel de control podemos ver el consumo actual de CPU de la plataforma, y una lista de los agentes conectados con su estado.


Alarmas
---------------------------

La plataforma incluye un sistema de alarmas que controla tanto valores de los sistemas con valores de negocio.

Esto quiere decir que controlamos:

- espacio de disco de los servidores
- consumo de cpu de los servidores
- conectividad de los servidores
- estado de los agentes
- errores en la importación de reservas
- el cálculo de precios
- la disponibilidad
- el estado de las webs
- el tiempo de respuesta de la plataforma
- nº de reservas en la última media hora
- valores sacados de NAV (ej.: versión de QuoHotel. Pendiente de estudio)

.. note:: Estos son los valores que controlaremos inicialmente, aunque hoy por hoy están pendientes de desarrollo.

Para gestionar las alarmas debemos utilizar la opción "Monitoring" del menú.

Esta opción tiene 3 subopciones:

- "Watchdogs"
- "Alarms"
- "Watchers"

Watchdogs
~~~~~~~~~

Un watchdog es un valor del sistema que queremos monitorizar. En esta opción podemos consultar, crear, modificar y borrar nuestros watchdogs.

El funcionamiento de un watchdog es el siguiente:

- cada minuto se comprueban todos los watchdogs
- si un watchdog falla se añade un fallo al watchdog
- si es el 6º fallo entonces se notifica a todos los watchers que tenga configurado
- el aviso se va repitiendo cada media hora hasta que el watchdog vuelve al estaod ok o se desactiva
- si el watchdog devuelve ok entonces el contador de errores se pone a 0
- las alarmas notificadas se quedan registradas y se pueden consultar

Actualmente podemos crear watchdogs de los tipos:

- Http

Para cada watchdog podemos configurar:

- nombre
- estado (activo o no)
- prioridad
- a quien debe notificar en caso de producirse un error

En el caso de un watchdog de tipo http podemos también configurar:

- una url
- método http (POST. GET, PUT, DELETE)
- request body
- código de status http esperado
- texto que debe estar presente en el boy de la respuesta http

Alarms
~~~~~~

Aquí podemos revisar el registro de alarmas que han sido reportadas a los watchers.

Si el watchdog no tiene watchers asociados la alarma se registra igualmente.


Watchers
~~~~~~~~

Aquí podemos mantener los watchers. Esto es, los que reciben notificaciones cuando se dispara una alarma.

Para un watcher podemos definir un nombre, una lista de emails separador por ; y si está activo o no.


Parámetros generales
--------------------

Accedemos a ellos utilizando la opción "AppConfig" del menú.

Podemos modificar los siguientes valores:

- General

  - Nombre de la empresa, que aparece en varios puntos de la aplicación
  - Logo

- Email

  - smtp host
  - smtp port
  - user
  - password
  - from
  - cc
  - pop3 host
  - pop3 port
  - pop3 user
  - pop3 password
  - pop3 email rechazo

- SMS

  - si clickatell está habilitado
  - api key para clickatell

- Templates (plantillas)

  - xslfo para listados
  - xslfo para contratos
  - xslfo para voucher
  - xslfo para facturas emitidas
  - xslfo para portfolio
  - xslfo para objeto genérico
  - xslfo para lista traslados
  - xslfo para pedido de compra
  - freemarker para sms pickup (en)
  - freemarker para email pickup
  - freemarker para sms pickup (es)

- CMS

  - directorio conf.d de nginx
  - comando para recargar la configuración de nginx

- MQ

  - host servidor RabbitMQ
  - usuario RabbitMQ
  - password RabbitMQ




Gestión de usuarios
-------------------

Los usuarios son lo que acceden a la plataforma.

Podemos crearlos, modificarlos, y borrarlos desde la opción "Users" del menú.

Para cada usuario podemos definir:

- nombre
- email
- estado (activo o no)
- actor (agencia o proveedor) al que está asociado
- oficina

Si relacionamos un usuario con un actor de tipo agencia entonces el usuario solo podrá acceder al acceso para agencias.

Si relacionamos un usuario con una oficina entonces solo podrá acceder al acceso para hoteles.

Si no lo relacionamos con una agencia ni con una oficina entonces el usuario solo podrá acceder al acceso para devops.

.. note:: Para cada nuevo usuario el password siempre es `1`.

.. note:: Comprobar esto último. Y si no indicamos nada por error?


Gestión de agencias
-------------------

Una agencia puede ser una OTA (Online Travel Agency), un touroperador o una web. En general, cualquiera a quien queramos dar acceso al sistema para comprar.

Para entrar en el mantenimiento de agencias deberemos utilizar la opción "Actors" del menú.

Para cada agencia podremos definir:

- su nombre
- si está activa
- si actúa como agencia
- si actúa como proveedor
- su dirección
- su NIF
- su email
- comentarios
- moneda

Es importante el tema de la moneda. A una agencia siempre le damos los precios en su moneda.

Como el mantenimiento del cambion de monedas es único, en el caso de la plataforma compartida no podemos calcular precios en una moneda distinta a la del contrato. Esto significa que debemos crear contratos en la moneda de la agencia o, si eso no sucede, no podrá comprar ese producto

Esta restricción no existe si contratamos la plataforma en modo dedicado.

Credenciales XML
----------------

Para que una agencia pueda acceder al sistema por xml, en cualquiera de las modalidades, necesita una credenciales.

Estas credenciales las gestionamos desde la opción "Tokens for XML" del menú.

Aquí podemos activar y/o desactivar tokens, así como crear nuevos tokens.

Para crear un token deberemos proporcionar:

- un usuario (que aparecerá en todas las reservas)
- una agencia (un actor)
- un hotel (si queremos restringir el acceso con estas credenciales a un hotel concreto)

El id del token es el que debe utilizar la agencia para consumir nuestro XML.


Gestión de agentes
------------------

Los agentes se corresponden con las aplicaciones que instalamos en los servidores de QuoHotel, en forma de servicio de Windows, y que se encargan de la sincronización entre QuoHotel y la plataforma QuoOn.

En la opción "Agents" del backoffice podemos consultar los agentes que hems dado de alta, crear nuevos agentes o eliminarlos de la plataforma.

Para cada agente podemos definir:

- Un nombre (que nos resulte cómodo, para identificarlo)
- Si está activo o no
- Un password
- Una oficina asociada
- Servidor MQ
- Cola para subida
- Cola para bajada
- Usuario del servidor MQ
- Password del servidor MQ
- Listado de urls de navision, indicando para cada url
  - Proveedor asociado
  - Url del servicio web de QuoHotel
  - Nombre, que nos resulte cómodo para indentificar este servidor de QuoHotel
  - Usuario de Nav
  - Password de Nav
  - Dominio de Nav
- Emails (lista separada por comas) a quien notificar cuando se produzca un error

En cada agente podremos ver también información relativa a su funcionamiento:

- Fecha y hora del último mensaje enviado
- Fecha y hora del último mensaje recibido
- Estado de la cola de subida
- Estado de la cola de bajada
- Último error de la cola de subida
- Último error de la cola de bajada


Recordar que podemos controlar el estado de los agentes en http://health.quoon.net y que están conectados con el sistema de alarmas de la plataforma, que nos avisa cuando hay problemas con algún agente.


Codificación general
--------------------

En este apartado podemos mantener algunos maestros que son comunes a tdos los usuarios de la plataforma.

Categorías de hotel
~~~~~~~~~~~~~~~~~~~

Las categorías de los hoteles: 1 estrella, 2 estrellas, ...

Podemos encontrarlas en la opción "Coding -> Categories" del menú.

Para cada categoría podemos indicar un código y un nombre (multiidioma).


Códigos de habitación
~~~~~~~~~~~~~~~~~~~~~

Los tipos de habitación: doble, doble vista mar, suite, ...

Podemos encontrarlos en la opción "Coding -> Room Codes" del menú.

Para cada tipo de habitación podemos indicar un código y un nombre (multiidioma).

Recordar que aquí definimos únicamente la descripción del tipo de habitación y que luego cada hotel define sus propios tipos de habitación con sus particularidades (ocupaciones máximas, descripción extendida, etc).


Códigos de régimen
~~~~~~~~~~~~~~~~~~

Los tipos de régimen: solo alojamiento, media pensión, pensión completa, ...

Podemos encontrarlos en la opción "Coding -> Board Codes" del menú.

Para cada tipo de régimen podemos indicar un código y un nombre (multiidioma).

Cada hotel puede luego definir sus propios tipos de régimen, a los que habŕa que asignar uno de estos códigos, extendiéndolos al proporcionar una descripción detallada de lo que incluye cada régimen alimenticio.

Consulta reservas
-----------------

<<<<<<< HEAD
Otros
-----
=======
Como administradores de la plataforma podemos consultar las reservas que se han confirmado en el sistema.

Podemos hacerlo desde la opción "Bookings" del menú.

Desde aquí podemos también consultar disponibilidad y precios, confirmar reservas, consultarlas y cancelarlas.
>>>>>>> 5533008342ab56a2b8a685a37aca6bb5019154c9
