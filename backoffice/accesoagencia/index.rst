.. QuoOn user manual documentation master file, created by
   sphinx-quickstart on Tue Dec  5 09:46:59 2017.
   You can adapt this file completely to your liking, but it should at least
   contain the root `toctree` directive.

Acceso para la agencia
=============================================

El acceso para agencias tiene una url propia.

En el caso del entorno de test esta url es http://agency.test.quoon.net .

========  =====
User      mv
Password  1
========  =====

.. warning:: deberíamos poner el entorno de demo. Pendiente de conseguir servidor.


La funcionalidad que el usuario de una agencia puede encontrar en este acceso queda resumida en el siguiente diagrama:

.. figure:: /_static/img/backoffice/back02.png
    :align: center
    :figwidth: 600px

En los siguientes capítulos revisaremos cada una de las funcionalidades que aparecen en el diagrama.


Nueva reserva
---------------------------

Para hacer una nueva reserva debemos selecionar la opción de menú "Bookings" y, una vez en el listado, seleccionar la acción "New booking".

A partir de este momento aparecerá un diálogo que nos pedirá la provincia, las fechas y las ocupaciones (combinaciones de nº de habitaciones / pax).

Al hacer click en "Next" nos aparecerá la lista de hoteles disponibles para esas fechas y ocupación, indicando el precio desde en cada caso.

Si algún hotel no está disponible en lugar del precio aparece el mensaje "NOTAVAILABLE" marcado en rojo.

En esta pantalla debemos seleccionar el hotel que nos interese y después hacer click en "Next".

Nos aparecerá una pantalla con las diferentes opciones dentro del hotel seleccionado. Deberemos seleccionar la opción que nos interese y hacer click en "Next".

Nos aparecerá la última pantalla del proceso de reserva, en la que deberemos introducir el tritular de la reserva, nuestra referencia para esta reserva y los comentarios / peticiones especiales que queramos transmitir al hotel.

.. warning:: las peticiones indicadas en los comentarios no están garantizadas.

Al hacer click en "Done" la reserva se confirmará y nos aparecerá una pantalla con la reserva que acabamos de confirmar.



Consultar reservas
---------------------------

Para consultar nuestras reservas debemos seleccionar la opción "Bookings" del menú.

Entonces veremos un listado con nuestras reservas, con varios filtros que podemos aplicar a la búsqueda.

En el listado veremos los datos básicos de las reservas (titular, hotel, fechas de entrada y salida, estado, importe, etc) y un link para entrar en la reserva.

Desde el listado mismo podemos también seleccionar una o varias reservas y cancelarlas (si es posible).

También podemos exportar el listado a una hoja excel o a un pdf, para imprimir el listado.



Cancelar una reserva
---------------------------

Para cancelar una reserva debemos ir al listado de reservas, utilizando la opción "Bookings" del menú.

En el listado podemos seleccionar una o varias reserva y utilizar la opción "Cancel selected services" para cancelarlas.

Nos parecerá un mensaje con el costte de la cancelación y, si aceptamos, las reservas se cancelarán.

Si la cancelación no fuese posible (por ejemplo porque la fecha de entrada ya ha pasado) nos aparecerá un mensaje avisándonos del error.


Modificar una reserva
---------------------------

Para modificar una reserva debemos ir al listado de reservas, utilizando la opción "Bookings" del menú.

Una vez que vemos la reserva en el listado, podemos acceder a ella haciendo click en el id de la misma.

Una vez con la reserva en pantalla, podemos modificar varios datos:

- nuestra referencia para esta reserva
- el nombre del titular (OJO: NORMALMENTE ESTO NO DEBERÍAMOS DEJAR HACERLO)
- las fechas, tipos de habitación, ocupaciones y tipo de régimen) (OJO: REVISAR SI DEBEMOS PERMITIRLO. TAL VEZ CONFIGURABLE)

Para confirmar los cambios utilizaremos la opción "Save".

La modificación de una reserva puede conllevar gastos. Una vez que los aceptamos la reserva quedará modificada.


