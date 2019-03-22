#########
Extensión
#########

El sistema es totalmente extensible y personalizable.

Esto quiere decir que podemos desde personalizar nuestros informes y documentos hasta añadir nuevos objetos a la base de datos y extender los existentes con nuevos campos, o modificar la lógica de negocio.

Las webs son totalmente personalizables, pudiendo añadir nuestros propios contenidos o alterar la imágen y estructura de nuestra web.

Además de la personalización de documentos y plantillas, algunos ejemplos de lo que podemos hacer serían:

- Personalización de los menús de la aplicación
- Extender el objeto agencia para guardar información adicional
- Extender el objeto factura para que genere asientos diferentes en contabilidad
- Cambiar el control de acceso a partes de la aplicación
- Cambiar el flujo de un proceso de negocio para que
- Personalizar los componentes que aparecen en una pantalla, o las pantallas completas
- Añadir nuevas pantallas


Definimos 2 niveles de personalización de QuoTravel:

- básico
- avanzado

******
Básico
******

En el nivel básico podemos personalizar documentos y plantillas, añadir traductores de compra y venta a terceros, crear informes, pero no podemos modificar el modelo de datos de QuoTravel ni los procesos de negocio.


********
Avanzado
********


En el nivel avanzado el control es total. Podemos modificar el modelo de datos, alterar el menú, las áreas privadas y el control de acceso, o personalizar los procesos de negocio a través del BPM.


Para poder trabajar en la personalización avanzada de QuoTravel es necesaria una formación previa.

En dicha formación los desarrolladores aprenden, entre otras cosas:

- el funcionamiento interno de QuoTravel
- como extender QuoTravel con sus propios objetos y/o campos
- como modificar los procesos de negocio para adaptarlos a sus necesidades
- como personalizar el manual de usuario de QuoTravel
- como cambiar los componentes de las pantallas
- como crear pantallas
- como cambiar el estilo de la interfaz de usuario de QuoTravel


*********
Seguridad
*********


QuoTravel cuenta con un conjunto de pruebas unitarias que cubren las principales funcionalidades del sistema y que se deben pasar al subir cambios a una instalación de QuoTravel.

A pesar de todo, naturalmente, no nos podemos hacer responsables de los problemas introducidos por las manipulaciones realizadas por personal ajeno a Quonext.



****
Webs
****

QuoTravel permite, utilizando su gestor de contenidos, añadir contenidos a la web del cliente y personalizarla hasta cierto punto.

No obstante, la personalización de las webs puede llegar al punto de cambiar absolutamente la presentación y los contenidos disponibles en la misma.

QuoTravel utiliza un generador de sitios estáticos (Hugo) que permite a nuestros clientes alterar completamente el esquema y la imágen de sus webs.

Como cliente de QuoTravel usted puede tener acceso a un repositorio en Github (o hacer un fork de nuestro repositorio) para manipular su web en la manera que necesite.

Puede cambiar la estructura de las páginas, la navegación, añadir o eliminar contenidos, los estilos...

Antes de desplegar sus cambios en producción se pasan una serie de pruebas unitarias para controlar que no se haya "roto" nada importante.

Además de las pruebas unitarias, el funcionamiento de la web también se controla por nuestro sistema de monitorización.


NOTA: considerar diseñar una formación (bajo demanada, con un precio) para la manipulación de las webs.
