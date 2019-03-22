#############
Configuración
#############

En esta parte de la documentación explicamos la configuración general de la plataforma


**************
Primeros pasos
**************

Aquí explicaremos los primeros pasos con la plataforma


Acceso al sistema
=================

El sistema se suministra siempre con algunos usuarios ya creados.

Además de algunos usuarios que son necesarios para el funcionamiento del sistema, se proporciona un usuario con privilegios de administrador, que es el que utilizaremos para acceder al sistema por primera vez y para crear otros usuarios:


========  =========
Usuario   **admin**
Password  **1**
========  =========

Naturalmente una de las primeras cosas que tenemos que hacer es cambiar el password.



Configuración general
=====================

En *Admin* -> *AppConfig* encontramos la configuración general del sistema.

Más adelante explicamos más en detalle todas las opciones posibles pero, de momento, nos basta configurar el nombre de la empresa, subir un logo y configurar el servidor de correo saliente.


Crear las divisas
=================

El siguiente paso consiste en crear las divisas que necesitemos.

Para cada divisa deberemos proporcionar su código iso de 3 letras y su código iso numérico (que se utiliza luego en las pasarelas de pago), además de un nombre.

En cada factura se guarda siempre el importe en la divisa de la misma, y también se guarda su contravalor en la divisa contable de la empresa.

En las líneas de cargo y en las reservas se guarda también el contravalor en la divisa de la oficina y en la divisa de la empresa.

Aquí tenemos algunos ejemplos de códigos ISO de divisas:

========  =========
EUR       978
USD       840
GBP       826
RUB       643
========  =========


En el capítulo dedicado al cambio de divisas veremos que el sistema recoge el cambio automáticamente cada día desde el BCE.


Crear los impuestos
===================

En este momento nos conviene crear los impuestos de valor añadido que nos afectan (IVA, IGIC).

Para ello iremos a Finnancials --> VAT y los crearemos.

De momento es suficiente darles un nombre.


Crear el mapa geográfico
========================

El siguiente paso consiste en crear al menos una zona en la que ubicar nuestra primera oficina.

Para ello deberemos crear un país, un destino y una zona.

En el caso del país conviene utilizar el código ISO.

En el caso de la zona podemos proporcionar, además del nombre, una lista de alias (nombres por los que también es conocida la localidad). Los alias los utilizamos depués en las búsquedas de disponibilidad.

Cuando creamos el mapa geográfico podemos crear también áreas. Una área es una lista de zonas que queremos agrupar bajo un mismo nombre, con vistas a utilizarlos después en las consultas de disponibilidad.

En el país debemos incluir esta información relativa a la gestión de traslados:

Lista de aeropuertos que hay que considerar como nacionales
  Lista de códigos IATA separados por coma.


Y en los aeropuertos, que definimos como puntos de traslado, completaremos la información con los siguientes campos:

Minutos para vuelos nacionales
  Si es un aeropuerto, el nº de minutos que necesitan para facturar y pasar los controles ara vuelos nacionales.

  Esto es, nº de minutos que tienen que estar en el aeropuerto, antes de la hora de salida del vuelo.

Minutos para vuelos internacionales
  Si es un aeropuerto, el nº de minutos que necesitan para facturar y pasar los controles para vuelos internacionales.

  Esto es, nº de minutos que tienen que estar en el aeropuerto, antes de la hora de salida del vuelo.


Crear la contabilidad
=====================

Hay que crear una contabilidad para cada una de las empresas que definiremos más adelante.

Para cada contabilidad debemosindicar un nombre y una divisa, que no podremos modificar más adelante.


Crear las empresas
==================

QuoTravel es un sistema multiempresa.

Esto quiere decir que dentro de la misma base de datos pueden coexistir varias empresas diferentes, cada una con su contabilidad, pero compartiendo la base de datos de clientes, usuarios, etc.

De esta manera una oficina puede gestionar servicios independientemente de si luego serán facturados por una u otra empresa.

Naturalmente, si queremos mantener bases de datos estancas para cada una de nuestras empresas también es posible.



Crear las oficinas
==================

Tanto la carga de producto como las reservas necesitan estar asociadas a una oficina, así que necesitamos crear al menos una.

Para cada oficina debemos proporcionar:

Nombre
  El nombre de la oficina. Aparece después en los informes, o en los emails
Localidad
  Donde está ubicada la oficina. Es necesaria para la correcta aplicación del IVA
Aeropuerto por defecto para traslados
  Se utiliza para asignar un aeropuerto a los traslados que son punto a punto, ya que necesitamos que todos los servicios de traslado estén asignados a un aeropuerto para montar el calendario de traslados.
Datos del servidor de email
  Los utilizamos para todos los envíos de email realizados desde la oficina, como pueden ser solicitudes de servicio a los proveedores.qqq

  Host
    La dirección del servidor de correo saliente. Normalmente este dato lo proporcionará el departamento de sistemas
  Port
    El puerto del servidor de correo saliente. Normalmente este dato lo proporcionará el departamento de sistemas
  Usuario
    El usuario a utilizar para conectarse al servidor de correo
  Password
    El password a utilizar para conectarse al servidor de correo
  From
    El remitente (email) que aparecerá en los emails
  CC
    Si queremos que los emails se envíen con copia a una dirección. Aunque el sistema guarda un registro de los emails que se han enviado, algunas delegaciones prefieren que se envíe también una copia a una dirección porque les resulta más cómodo.


Crear una clave de facturación
==============================

Para poder facturar necesitamos asociar lo que facturamos a lo que llamamos clave de facturación.

La clave de facturación, aparte de servirnos para generar informes y para agrupar los importes de una reserva o factura, nos proporciona la información necesaria para la correcta aplicación del IVA.

Así, para cada clave de facturación deberemos indicar:


Código
  Un código alfanumérico
Nombre
  Un nombre descriptivo
Regla de localización
  Se utiliza para aplicar correctamente el IVA.

  En QuoTravel todos los importes que se manejan en la reserva son con IVA incluido.

  En función de la regla de localización sabemos después como gestionar el IVA: si tiene IVA, si podemos ir por régimen general, si debemos permanecer en régimen especial, ...
Clasificación
  Aquí indicamos si esta clave se utiliza para un servicio de hotel, traslado, genérico, comisión o handling fee


Crear un mercado
================

Para poder crear creservas necesitamos asociarlas a un mercado.

En base al mercado sabemos luego que precios podemos aplicar a una reserva. Es pues un campo obligatorio de la reserva.


Para crear los mercados debemos utilizar la opción CRM --> Markets.


Para cada mercado debemos indicar únicamente un nombre.



Crear un punto de venta
=======================

Todas las reservas están asociadas a un punto de venta o canal, así que deberemos crear al menos uno.

Normalmente crearemos uno para la web, otro para el xml, otro para el mostrador de la oficina, ... según nos convenga.

Solo necesitamos darle un nombre, y aparecerá después en la reserva y en algunos informes.





*******************
Gestión de usuarios
*******************

En QuoTravel podemos crear tantos usuarios como necesitemos, y asignar a cada uno diferentes roles o darle acceso únicamente a una oficina, como agencia o como proveedor.

Crear usuarios
==============

Para crear un usuario basta ir al mantenimiento de usuarios, en *Admin* --> *Users*, y utilizar la opción *New*.

Para el nuevo usuario podemos indicar:

Login
  Código alfanumérico del usuario. Debe ser único. No se distinguen mayúsculas.
Nombre
  El nombre completo del usuario
Email
  Email del usuario. El usuario recibirá un email de bienvenida en esta dirección, con el password.
Estado
  Un usuario puede estar en uno de los siguientes estados:

  ===============  ==============================================================================================
  Activo           El usuario puede acceder al sistema
  Inactivo         Hemos desactivado el usuario y no puede acceder al sistema
  Bloqueado        Sucede tras haberse equivocado más de 10 veces al poner el password
  Caducado         Ha pasado la fecha de caducidad. El usuario ya no puede acceder al sistema
  ===============  ==============================================================================================

Fecha de caducidad
  Aquí podemos indicar una fecha para la desactivación automática de este usuario. Después de esa fecha, el usuario pasará al estado *Caducado* y no podrá seguir accediendo a QuoTravel.
Foto
  La foto del usuario
Comentarios
  Comentarios de uso interno
Actor
  Aquí indicamos si es un usuario de una agencia o de un proveedor
Oficina
  Utilizaremos este campo si queremos que este usuario acceda solo a las reservas y producto de una oficina concreta.
Permisos
  En QuoTravel hay definidos diferentes permisos para controlar el acceso de los usuarios. Actualmente son:

  Súper administrador
    Este permiso otorga acceso a todo el sistema.
  Booking
    Este permiso permite al usuario gestionar reservas.
  Administración
    Este permiso da acceso al área financiera (facturación, cobros y pagos, etc).
  Confirmación horarios
    Este permiso otorga acceso a la pantalla para la confirmación de horarios de recogida de los clientes de traslado.

  Los permisos son acumulativos. Podemos asignar varios de ellos al mismo usuario.

  Los permisos irán creciendo en función de las peticiones de los clientes de QuoTravel.


Al grabar el nuevo usuario se manda un email de bienvenida a la dirección de email con su password. El sistema obligará al usuario a cambiar el password en su primer acceso.

Tanto el email de bienvenida como el email de recuperación del password son personalizables en *Admin* --> *AppConfig*.


Recuperar el password
=====================

Si un usuario ha olvidado el pasword puede recuperarlo utilizando la opción *Password olvidado* que le aparece cuando va a acceder a QuoTravel.

El sistema le enviará entonces un email con una url para indicar un nuevo password.


Modificar usuarios
==================

A través del listado de usuarios podemos entrar en la ficha de cualquier usuario y modificar cualquiera de los campos salvo el login.

En la ficha del cliente podemos ver también la fecha y hora de su último acceso a QuoTravel, o el número de veces que se ha equivocado con el password.


Bloqueo de usuarios
===================

Para proteger el sistema, si un usuario se equivoca de manera consecutiva 10 veces al intentar acceder al sistema, el usuario queda bloqueado.

Esto es así para evitar que alguien averigue los passwords utilizando un proceso automático.

Cuendo esto sucede, el usuario pasa a estado *Bloqueado* y hay que desbloquearlo entrando en la ficha del usuario y cambiando su estado a *Activo*.




***********
Multiidioma
***********

En QuoTravel hay muchos contenidos que son multiidioma.

Por ejemplo el nombre de un tipo de habitación, o la descripción de un hotel.

Aparte de modificarlos en los mantenimientos correspondientes, podemos gestionarlos aquí de manera centralizada.


Idiomas
=======

Los idiomas soportados en QuoTravel son los siguientes:

======  ==========================
es      Español
en      Inglés
fr      Francés
de      Alemán
it      Italiano
ar      Árabe
cz      Chino
ru      Ruso
======  ==========================

En el caso de necesitar otro idioma hay que contactar con nosotros y solicitar su inclusión.


Traducciones
============

En *Admin* -> *Translations* podemos gestionar las traducciones de manera centralizada.

Podemos editar cada texto en los diferentes idiomas soportados, que hemos enumerado en el apartado anterior.

QuoTravel está integrado con Google para traducir los textos, aunque la fiabilidad es la del servicio de Google. Siempre es recomendable comprobar luego los textos.






******************
Plantillas mailing
******************

En QuoTravel es posible realizar envíos masivos de emails a clientes y proveedores.

En *Admin* -> *Templates* podemos crear, modificar o eliminar las plantillas que utilizaremos después para esos emails.

Para cada plantilla podemos indicar:

  Nombre
    Para identificar la plantilla

  Freemarker
    La plantilla se escribe utilizando freemarker.


Campos freemarker
=================

Cuando construimos la plantilla hay una serie de campos que podemos incrustar, que enumeramos a continuación:

============  ===================================================================
businessname  Nombre de la empresa
logourl       Logo de la empresa
username      Nombre del usuario
useremail     Email del usuario
partnername   Nombre del cliente o proveedor
partneremail  Email del cliente o provedor
============  ===================================================================

Los campos disponibles dependen del entorno. Si estamos mandando un email a un usuario solo los campos relativos al usuario estará, disponibles, lo mismo cuando enviamos un email a un partner, etc.



***********************
Integraciones de compra
***********************

En *Admin* -> *Integrations* podemos mantener nuestras integraciones de compra.

QuoTravel "habla" la especificación abierta easytravelapi.

Eso quiere decir que necesita que el proveedor haya publicado sus servicios utilizando dicha especificación.

En caso contrario hay que desarrollar un traductor que se encargue de convertir las peticiones en formato easytravelapi que se envían desde QuoTravel a la especificación del provedor.

Dicho traductor no tiene porque desarrolarlo Quonext, aunque estamos encantados de hacerlo, sino que puede ser desarrollado por el departamento de IT de la agencia, por el proveedor del servicio o por un tercero.

Al final, esos traductores se resumen en una url y unas credenciales.


Así, por cada integración de compra deberemos definir:

  Nombre
    Para identificar la integración.

  Producto
    Para saber que reglas de negocio debemos aplicar a este producto.

  URL base
    Este dato nos lo deberá proporcionar el proveedor, o nuestro departamento de IT.

  Activa
    Podemos activar o desactivar una integración

  Servicios que provee
    La integración puede servir para comprar hoteles, traslados, excursiones. Aquí indicamos que servicios podemos comprar utilizando esta integración.

  Nº máximo de recursos por petición
    Este es un parámetro técnico. Sirve para indicar cuantos hoteles como máximo debemos pedir en las consultas de disponibilidad. Si hay más hoteles en la zona se realizarán varias peticiones en funcióin de este número.






*********************
Configuración general
*********************

En *Admin* -> *AppConfig* encontramos la configuración general del sistema.

Son aquellos valores que se definen una única vez para todo el sistema, y son valores que normalmente no se tocan o solo se tocan una vez.


Gran parte de los valores que aquí indicamos están destinados al departamento de IT.


Estos son los valores que podemos modificar:


  Nombre de la empresa
    Aparece luego en nuestra intranet, en documentos y en algunos emails.

  Logo de la empresa
    Igual que el nombre aparece luego en nuestra intranet, en documentos y en algunos emails.

  Servidor de email
    QuoTravel utiliza un servidor de email para enviar y para recibir emails.

    Host SMTP
      La dirección del servidor SMTP

    Puerto SMTP
      El puerto del servidor SMTP

    Usuario email admin
      El usuario a utilizar para que el sistema envíe emails necesarios para el funcionamiento del sistema.

    Password email admin
      El password de la cuenta que el sistema envíe emails necesarios para el funcionamiento del sistema.

    Remitente email admin
      El remitente a utilizar en los emails que se envían desde el sistema.

    CC email admin
      Si queremos recibir copia de los emails que se envían desde el sistema.


    Host POP3
      La dirección del servidor POP3

    Puerto POP3
      El puerto del servidor POP3

    Usuario pop3
      El usuario a utilizar para accedder al servidor pop3.

    Password pop3
      El password a utilizar para accedder al servidor pop3.

    Email rebote
      A que cuenta hay que reenviar los emails cuando haya problemas.

  SMS
    QuoTravel utiliza SMS para informar por ejemplo las horas de recogida a los clientes de traslados

    Habilitar Clickatell
      Para indicar si queremos utilizar Clickatell para el envío de SMS

    Clave Clickatell
      La clave a utilizar para acceder a la plataforma de Clickatell

  Plantillas
    QuoTravel utiliza plantillas para todos los documentos e emails que se generan desde la plataforma.

    De esta forma podemos personalizarlos.

    Normalmente utilizamos XSL-FO para generar pdfs y Freemarker para generar el html que metemos en los emails.

    Xsl-fo para listados
      Se utilia para generar los pdf a partir de los listados

    Xsl-fo para contrato de hotel
      Se utiliza para generar el pdf para revisar / firmar el contrato de hotel

    Xsl-fopara contrato de traslado
      Se utiliza para generar el pdf para revisar / firmar el contrato de traslado

    Xsl-fo para el voucher
      Se utiliza para generar el voucher en formato pdf

    Xsl-fo para factura emitida
      Se utiliza para generar el pdf de una factura

    Xsl-fo para el mundo
      Se utiliza para generar un pdf con todo nuestro producto

    Xsl-fo para objeto
      Se utiliza para generar un pdf para cualquier objeto del sistema, con vistas a imprimirlo.

    Xsl-fo para listas de traslado
      Se utiliza para generar un pdf con una lista de traslados

    Xsl-fo para pedidos de compra
      Se utiliza para generar un pdf para un pedido de compra

    Freemarker para pedido de compra
      Se utiliza para generar el email para una pedido de compra

    Freemarker para SMS horario recogida
      Se utiliza para generar el SMS que enviamos a los clientes para informar la hora de recogida de los traslados

    Freemarker para email horario recogida
      Se utiliza para generar el email que enviamos a los hoteles para informar la hora de recogida de los traslados

    Freemarker para SMS horario recogida en español
      Se utiliza para generar el SMS que enviamos a los hoteles para informar la hora de recogida de los traslados cuanod el móvil es español (prefijo 34).

  CMS
    Aquí indicamos la configuración necesaria para que funcione el gestor de contenidos

    Directorio configuración Nginx
      Aquí indicamos el path del firectorio donde deben crearse los ficheros de configuración de Nginx

    Comando para recargar Nginx
      Aquí indicamos el comando que debe ejecutarse cada vez que actualizamos la configuración de Nginx





******************************
Integración con ERP financiero
******************************

QuoTravel incluye un ERP financiero.

No obstante, permite la integración con un ERP externo de nuestra elección.


Esta integración puede hacese a varios niveles, como veremos ahora.


Toda esta configuración la encontramos al crear los planes contables.


Solo exportar asientos contables
================================

En el nivel más bajo QuoTravel solo exporta los asientos contables.

Toda la operativa financiera (facturación, gestión de pagos, cierre de IVA) se realiza íntegramente en QuoTravel y, cuando se solicita, se genera un fichero con los asientos contables que reflejan las operaciones realizdas en QuoTravel.

Hay que recordar que podemos personalizar los asientos contables que generamos desde QuoTravel, cambiando su forma, los textos o añadiendo registros para la contabilidad analítica.


Exportar facturas y pagos
=========================

En el siguiente nivel mandamos al ERP financiero las facturas y cobros y pagos que hemos registrado en QuoTravel.

Los asientos los generará el ERP a partir de las operaciones que hemos exportado, y ya nos los veremos desde QuoTravel.


Exportar líneas de cargo
========================

En el nivel más alto de integración QuoTravel deja en manos del ERP financiero todas la facturación y la gestión de cobros y pagos.

En este caso QuoTravel se "limita" a la carga de producto y a la gestión de las reservas.

Lo que se exporta al erp financiero son en este caso las líneas de cargo.

Las emisión de facturas a clientes, la validación de facturas de proveedores y la gestión de cobros y pagos hay que hacerlas en el ERP financiero.


Como implementar la integración
===============================

Para hacer la integración con el ERP financiero hay que implementar una interfaz que proporcionamos, y luego inyectar nuestro conector en nuestra instalación de QuoTravel.


Si la integración se implementa completamente podremos seguir viendo desde una reserva si ha sido facturada, si la hemos cobrado o si hemos pagado a los proveedores.



