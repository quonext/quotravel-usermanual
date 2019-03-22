#####################
Documentación interna
#####################

***********************
Alta de una instalación
***********************

Las instalaciones pueden venir como resultado de una acción comercial, pero también un cliente puede darse de alta en QuoTravel por sí mismo.

Contratación modo tradicional
=============================

En el modelo "tradicional" crearemos la instalación desde un backoffice específico para QuoTravel como plataforma saas.

En este caso, deberemos proporcionar:

- un nombre de cliente
- datos comerciales, de facturación y contacto técnico
- en que servidor queremos desplegar la aplicación
- una url para el backoffice (del tipo europalia.quoon.net)
- lista de servicios contratados

En el caso del modelo tradicional ya habremos presupuestado la infraestructura contratada (el nº y tipo de servidores, alta disponibilidad, etc)y existirá un proyecto para la instalación, formación, tipo de soporte contratado, etc.


Contratación modo online
========================

Un cliente de QuoTravel se puede registrar directamente en la web de QuoTravel y operar sin que haya ninguna intervención por nuestra parte.

Vendría a ser una venta desatendida.

El cliente ya ha podido probar QuoTravel en una web de demo. Habrá que aclarar con comercial si se quiere dar acceso al entorno de demo después de un registro, con una validación por parte de los comerciales, etc.

En este caso el cliente se registra por si mismo en la web de QuoTravel y contrata el servicio.

Para ello proporciona algunos datos:

- contacto
- datos de la empresa
- tipo de servidor deseado
- valida las condiciones de uso (uso no faudulento, etc)
- la forma de pago (p.ej: anual con un descuento o mensual)
- datos de la tarjeta (el servicio se cobra por aticipado)

El soporte básico es a través de un foro privado, desde su cuenta en la plataforma, y no existe un compromiso de tiempo de respuesta (lo antes posible).

En esta modalidad el cliente solo pone la visa y utiliza el sistema. Si cada mes la visa funciona puede utilizar el sistema. Si no, se inhabilita la cuenta.


Plataforma saas
===============

A través del área de cliente en la web de QuoTravel el cliente puede controlar su cuenta y contratar servicios adicionales y otras operaciones:

- soporte (acceso al sistema de incidencias)
- servidores
- formación
- conexiones con terceros
- darse de baja
- cambiar los datos de la tarjeta
- comprobar el estado de sus servidores
- configurar una url de un dominio propio para su sistema (ej: admin.viajesibiza.es)



NOTA: trabajaremos en la plataforma saas a partir de mayo de 2019, para que esté lista para la WTM2019.


***************
Infraestructura
***************

Cada cliente tendrá sus propios servidores.

El motivo es que no se "molesten" entre ellos, y que puedan contratar una infraestructura adecuada a sus necesidades.

Hay servidores dedicados desde 50 euros al mes (más iva), aunque el recomendado para un cliente tipo Viajes Ibiza tiene un coste de 125 euros.

Hay que explorar la posibilidad de ubicar QuoTravel en servidores privados virtuales que tienen un coste de 8 euros al mes (suscripción anual, 2 cores, 4GB RAM y 60GB SSD), para proporcionar una versión de coste extra bajo para clientes que quieren probar QuoTravel o que solo tienen 1 usuario.

A partir de ahí, se pueden ir añadiendo servidores de diferentes configuraciones a la ecuación para conseguir alta disponibilidad y escalabilidad.

La regla a seguir es que **no hay que escatimar con este tema**. Siempre tenemos que ir holgados, con un margen. No nos interesa tener problemas porque el servidor no está correctamente dimensionado, sobre todo por el bajo coste de un servidor dedicado.

No obstante, es cierto que al trasladar al cliente la elección del servidor que quiere utlizar y el utilizar servidores separados para cada cliente nos libera un poco del tema. Podemos bajar el coste de QuoTravel para clientes mini y pueden irse a servidores más grandes si lo necesitan y lo quieren pagar.

Todas las tareas de instalación y de sistemas estarán automatizadas: instalación de QuoTravel en un nuevo servidor, copias de seguridad, mover a un cliente de un servidor a otro, ...  y en lo posible ejecutables desde la plataforma, sin necesidad de entrar en el servidor.


***************************
Estructura de los proyectos
***************************

En principio todos los clientes desplegarán los proyectos de QuoTravel "puros".

En el caso de que un cliente desee personalizar su instalación, tanto si nos encargamos nosotros como si lo hacen ellos o un tercero, crearemos un fork de los respositorios de los proyectos afectados.

En el caso de un cliente con una instalación personalizada serán esos forks los que se desplegarán en los servidores.

Esta configuración (repositorio / rama / release / servidores) deberá figurar en la base de datos de la plataforma, para utilizarla en los scripts de despliegue de las aplicaciones.


****
Core
****

QuoTravel se desarrolla con java.

Utilizamos programación orientada a objetos, que persistimos en base de datos utilizando la especificación jpa.

Esta manera de trabajar nos permite aprovecharnos de todas las ventajas de la programación orientada a objetos (herencia, polimorfismo, promueve la correcta distribución del código, etc).

Utilizar jpa nos independiza de la base de datos en la que decidimos guardar los datos (utilizamos postgresql, pero podría ser oracle, mssql, mysql o inlcuso bases de datos nosql como mongodb o couchdb) y nos proporciona los mecanismos (una caché de 2 niveles sincronizada y sharding) para conseguir el alto rendimiento y la escalabilidad que necesitamos, sin que tengamos que hacer un esfuerzo adicional.

Para que lo entendamos, es como si moviésemos la base de datos a java.

Jpa nos dice como debemos implementar triggers, nos da transacciones y nos permite también poner restricciones sobre los datos para asegurar la consistencia de los mismos.

La implementación de jpa (en nuestro caso eclipselink) también se encargar de mantener el esquema de base de datos actualizado, creando tablas y añadiendo columnas automáticamente.


La base de datos se convierte pues en un simple almacén donde guardamos los datos para sobrevivir a los reinicios y para no tener que tener todos los datos en memoria.


Para que los usuarios puedan gestionar sus datos creamos la interfaz de usuario utilizando MDD (desarrollo dirigido por el modelo).

Esto quiere decir que no "programamos" la interfaz de usuario, sino que se genera automáticamente a partir de nuestras clases de negocio.

Podemos controlar la manera en que exponemos nuestros objetos y nuestros métodos simplemente anotando nuestras clases de negocio.

El control de la interfaz de usuario puede llegar a ser muy fino, pudiendo crear nuestros propios componentes si hace falta.

Lo importante es que, al no haber código, obtenemos varias ventajas importantes:

- nos proporciona independencia de la tecnología que utilizamos en el lado cliente y protege nuestra inversión. Si el año que viene aparece una nueva tecnología solo tenemos que crear un nuevo port del framework MDD, pudiendo mantener toda nuestra lógica de negocio.
- minimiza el tiempo de desarrollo
- evita bugs. El código que no falla es el que no se ha escrito.


Esta manera de trabajar también nos da acceso a toda una serie de facilidades que son las que permiten que podamos utilizar la herencia y composición en nuestros proyectos.

Podemos por ejemplo tener nuestro proyecto "core" y crear un proyecto "viajesibiza", que extiende nuestro proyecto "core" y que solo modifica los menús y añade una funcionalidad específica para exportar la producción a Beroni.

O crear un proyecto "quoon" que extiende también nuestro proyecto "core", pero que solo "enseña" la parte relativa a la reserva de hotel.

O separar nuestro proyecto "core" en varios proyectos (uno con el erp, otro con el cms, otro con el crm) y utilizarlos a discrección en otros proyectos, simplemente añadiendo las dependecnias.


Todo esto llega de la mano del uso correcto del ecosistema java.


Los artefactos acaban en un repositorio maven (con su versionado) para que luego podamos utilizarlas en nuestros desarrollos o desplegarlas en los servidores de producción.

El tema de las versiones es importante, pues nos permite seguir con nuestros desarrollos sin afectar a los clientes que ya tenemos funcionando. En nuestro caso, para la parte java, nos basamos en maven para resolver esta problemática.

***
Web
***

La lógica de las webs se aloja en proyectos independientes, se programa utilizando Vue y el ejecutable resultante se publica en npm.

Npm nos resuelve la problemática de las dependencias y versionado, igual que maven lo hace en la parte java.

Para generar nuestros "artefactos", ya sea generando javascript, procesando nuestras scss para generar los css finales, o optimizando las imágenes, utilizamos webpack.

Luego esa lógica (la que hemos guardado en npm) se consume desde el proyecto que realmente contiene la web.

En esta parte utilizamos un generador de sitios estáticos que se llama Hugo y que nos permite separar contenido de presentación.

Es este proyecto el que "forkeamos" para crear una repositorio específico para el cliente, al que le damos acceso.

EL despliegue de las webs se hace sobre netlify, con lo que descargamos nuestros servidores, nos ahorramos tener que mantener la infraestructura para el despliegue de las webs y nos aprovechamos del cdn de netlify. Esa separación de también ayuda después a la mantenibilidad del sistema, que es importante también.

El camino queda resumido como sigue:

Vue --> Npm --> Hugo --> Netlify

Naturalmene también utilizamos scss y otras cosas, pero la idea principal es esa.

Los servidores dedicados soportan únicamente la lógica de negocio y la base de datos. Las webs las desplegamos en netlify.


***************************
Integración con ERP externo
***************************


QuoTravel incluye un ERP financiero que permite gestionar todo lo concerniente a emisión y recepción de facturas, gestión de cobros y pagos, iva, etc.

Lo que no incluye en principio es la gestión de la contabilidad.

El reflejo contable de todas las facturas, cobros y pagos, etc se exporta al programa contable en forma de asientos.


El objetivo de incluir el erp como parte de QuoTravel es el de poder ver y acceder desde la reserva a todo lo relacionado con la misma, que incluye facturas, cobros y pagos.

Desde una reserva debemos poder emitir una factura, registrar cobros, o ver si ya hemos recibido la factura del proveedor y si la hemos pagado ya.

También el de ofrecer al cliente, en la medida de lo posible, una solución integral.


No obstante, vamos a contemplar la posibilidad de utilizar un erp financiero diferente al que incluye QuoTravel.

Esto significa que habrá una interfaz que va a definir la interacción con el erp para poder facturar una reserva, introducir un cobro, leer  los datos de facturación para asignarlos a una agencia, consultar las facturas en la que aparece una reserva, leer los pagos realizados por un cliente para conocer el saldo de una reserva, etc.


Para integrar un erp externo "solo" habrá que implementar esa interfaz y decirle a QuoTravel que quiere utilizar ese erp en lugar del interno de QuoTravel.






