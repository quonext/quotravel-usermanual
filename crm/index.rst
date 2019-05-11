#######
Negocio
#######

************
Introducción
************

En esta área de QuoTravel encontramos lo relacionado con nuestros partners, que pueden ser agencias o proveedores.

La parte relativa a facturación y pagos la encontraremos en el área financiera de QuoTravel.


********
Agencias
********

En QuoTravel una agencia es el que nos hace reservas.

Para cada agencia podemos proporcionar los siguientes datos:

Nombre
  El nombre con el que identificamos a esta agencia.

Estado
  Una agencia puede estar en un de los siguientes estados:

  ================  =====================================
  Activo            La agencia puede hacer reservas
  Inactivo          La agencia no puede hacer reservas
  Crédito excedido  Ha superado alguno de los límites de crédito. No puede hacer reservas
  ================  =====================================

Grupo
  Aquí podemos indicar el grupo de partners al que pertenece, si es el caso. Se utiliza luego en los contratos o en los markups, cuando indicamos que un contrato o markup es válido para un grupo de agencias.

Central
  Aquí podemos indicar que partner es la central de este partner, cuando es una sucursal. Luego se utilizan los markups de la central para todas las sucursales.

Mercado
  Cada agencia está ligada a un mercado por defecto. El mercado se utiliza para segmentar el producto.
  No obstante, veremos que a la hora de realizar una reserva podemos indicar cualquier mercado, para cualquier agencia.

Moneda
  Para cada agencia debemos indicar con que moneda quiere las reservas. En el caso de que una agencia acepte trabajar con las divisas de compra dejaremos el campo en blanco.

Agente financiero
  Aquí indicamos los datos de facturación de un cliente. Al separar la parte operativa de la parte de facturación de las agencias y proveedores nos permite tener una balanza de pagos, compartir los datos de facturación entre diferentes agencias, etc.

Email
  Aquí indicamos el email de la agencia o proveedor. Lo utilizamos para mandarle llos vouchers y otras comunicaciones.

Comentarios
  Este es un campo para poner nuestros comentarios. Es un campo para uso interno nuestro.


Acepta reservas on request
  Si marcamos este campo le devolveremos hoteles aunque estén on request.

Acepta PVP
  Si marcamos este campo le entregaremos precios con PVP obligatorio.
  Algunos hoteles marcan el PVP para conseguir paridad de precios, o para garantizar que los precios más baratos se encuentran en su web.
  No debemos marcar esta opción si la agencia no respetará los precios que marca el hotel.

Acepta prodcto de terceros
  Si marcamos esta opción entregaremos a esta agencia el producto de integraciones de compra con terceros (por ejemplo Hotelbeds).
  Si no marcamos esta opción esta agencia solo verá el producto que tengamos cargado en QuoTravel en forma de contratos.

Margen
  Aquí asignamos el margen que se debe utilizar con este cliente.
  El margen se aplica sobre los precios de compra, cuando no existe un contrato de venta que fije el precio.
  Un ejemplo típico es el del producto que obtenemos a través de una integración con un tercero, donde solo tenemos el precio de compra.

Handling fee
  Aquí indicamos las reglas de hangling fee que hay que aplicar a las reservas realizadas por esta agencia.

Condiciones de cancelación
  Aquí indicamos las condiciones de cancelación que aplican a esta agencia.

Integraciones de terceros
  Aquí podemos indicar que integraciones de compra son accesibles para esta agencia.
  Si no indicamos ninguna todas las integraciones son accesibles, a no ser que hayamos indicado expresamente que no quiere productos de terceros, como hemos visto en el campo *Acepta prodcto de terceros*.

******************
Grupos de agencias
******************

Los grupos de agencias los utilizamos para segmentar el producto.

Así, en los contratos podemos indicar si ese producto es visible para un grupo de agencias en lugar de ir agencia por agencia.


***********
Proveedores
***********

En QuoTravel las reservas las enviamos a proveedores, que es quien después nos enviará facturas por sus servicios.

Para cada proveedor podemos proporcionar los siguientes datos:

Nombre
  El nombre con el que identificamos a este proveedores.

Estado
  Un proveedor puede estar en un de los siguientes estados:

  ================  =====================================
  Activo            La agencia puede hacer reservas
  Inactivo          La agencia no puede hacer reservas
  ================  =====================================

Moneda
  Para cada agencia debemos indicar con que moneda quiere las reservas. En el caso de que una agencia acepte trabajar con las divisas de compra dejaremos el campo en blanco.

Agente financiero
  Aquí indicamos los datos de facturación de un cliente. Al separar la parte operativa de la parte de facturación de las agencias y proveedores nos permite tener una balanza de pagos, compartir los datos de facturación entre diferentes agencias, etc.

Email
  Aquí indicamos el email de la agencia o proveedor. Lo utilizamos para mandarle llos vouchers y otras comunicaciones.

Comentarios
  Este es un campo para poner nuestros comentarios. Es un campo para uso interno nuestro.

Pagadero por
  Lo que pongamos en este campo aparecerá en los vouchers de los servicios proveidos por este proveedor.

Condiciones de cancelación
  Aquí indicamos las condiciones de cancelación que aplican a este proveedor.

Método de envío de pedidos
  Aquí indicamos como enviar los servicios a este proveedor.

Dirección de envío de pedidos
  Aquí indicamos a que emails deben envarse los pedidos de compra

Envío automático de pedidos
  Si lo marcamos los pedidos se enviarán automáticamente en cuanto se creen.

Confirmación automática de pedidos
  Si lo marcamos los servicios se marcarán automáticamente como confirmados en cuanto se envíen.


********
Mercados
********

Los utilizamos para segmentar el producto.

Cada agencia pertenece a un mercado y recibe los precios de los contratos que hemos marado como válidos para ese producto.

Crearemos por ejemplo mercado británico, alemán, nacional, ...

No hay que confundirlo con el concepto de nacionalidad.


******************
Líneas de producto
******************

Cada contrato lo asignamos a una línea de producto.

Luego los márgenes los asignamos a una línea de producto.

De esta manera podemos indicar diferentes márgenes según una línea de producto.

Ejemplos de línea de producto podrían ser *Baleares*, *Península*, *Hotelbeds*, *Sunhotels*, ...


********
Márgenes
********

Los márgenes nos sirven para indicar que reglas debemos aplicar para el cálculo de un precio de venta, cuando lo que tenemos es solo un contrato de compra.

Si existe un contrato de venta válido para nuestro cliente ese es el que manada pero, si solo tenemos un contrato de compra, todavía podemos obtener el precio de venta aplicando un margen, si es que existe alguno aplicable para nuestro cliente.

Para mantener nuestros márgenes debemos ir a CRM --> Revenue --> Markups.

Para cada conjunto de reglas de margen podemos indicar

Nombre
  Para aque podamos identificarla después

Activa
  Para indicar si esta regla está activa o no debe utilizarse

Partners
  A que partners pueden aplicarse estas reglas

Mercados
  A que mercados pueden aplicarse estas reglas

Empresas del grupo
  A que empresas del grupo pueden aplicarse estas reglas


Cada conjunto de reglas de markups tiene líneas de markup, que podemos mantener en CRM --> Revenue --> Markup lines


Para cada línea de markup podemos indicar

Markup
  Regla de markup a la que pertenece

Línea de producto
  Para que línea de producto es aplicable este margen

Activa
  Si esta línea está activa

Margen mínimo por reserva
  Cuanto queremos ganar como mínimo para cada reserva

Margen máximo por reserva
  Cuanto nos basta ganar por reserva

Porcentaje
  Entre el mínimo y el máximo el margen se calcula aplicando este porcentaje sobre el precio de compra


La lógica de aplicación de margenes es:

- Si no existe un contrato de venta entonces intentamos conseguir el precio de venta aplicando un margen sobre el precio de compra
- Las reglas de margen están indicadas en la agencia (partner)
- Buscamos una línea de margen activa para el producto que estamos vendiendo
- Si existe esa línea aplicamos margen mínimo, máximo y pocentaje
- Si no existe esa línea no podemos vender ese producto



************
Handling fee
************

Con cada cliente podemos haber indicado un conjunto de handling fees.

Para definir un handling fee debemos ir a CRM --> Revenue --> Handling fees

Para cada cabecera de handling fee deberemos indicar

Nombre
  Para identificarlo

Concepto de facturación
  Para identificar los cargos y para saber que IVA hay que aplicar


Y para cada línea de handling fee deberemos indicar

Rango de fechas
  Rango de fechas para las que es aplicable este handling fee. Se tiene en cuenta la fecha del inicio del servicio

Mínimo pax para considerarlo un grupo
  Por debajo de este número aplicaremos las condiciones de reservas individuales. Por encima, las condiciones de reservas de grupo

Mínimo habitaciones para considerarlo un grupo
  Por debajo de este número aplicaremos las condiciones de reservas individuales. Por encima, las condiciones de reservas de grupo

Aplicable a reservas de hotel de producto propio
  Si está marcado aplicaremos el handling fee a las reservas donde el contrato no esté marcado como facturación directa. Esto es, hoteles que gestionemos nosotros e integraciones con terceros.

Aplicable a reservas de hotel del touroperador
  Si está marcado aplicaremos el handling fee a las reservas donde el contrato si esté marcado como facturación directa. Esto es, contratos que solo tenemos en el sistema para controlar los cupos y los cierres.

Aplicable a transfers
  Si está marcada esta opción el handling fee se aplicará a todas las reservas que incluyan el servicio de traslado.

Por noche
  Si está marcado, todos los importes se multiplicarán por el nº de noches de la estancia

Porcentaje
  Porcentaje a aplicar al percio de venta de la reserva para calcular el handling fee

Divisa
  Divisa en que están indicados los precios

Condiciones para reservas individuales
  Aquí siguen los precios para el handling fee para el caso de las reservas individuales

  Importe por adulto
    Importe a aplicar por adulto

  Importe por niño
    Importe a aplicar por niño, si ha sido calificado como tal al valorar la reserva

  Importe por habitación
    Importe a aplicar por habitación

  Importe por reserva
    Importe a aplicar por reserva

Condiciones para reservas de grupo
  Aquí siguen los precios para el handling fee para el caso de las reservas que hemos calificado como grupo

  Importe por adulto
    Importe a aplicar por adulto

  Importe por niño
    Importe a aplicar por niño, si ha sido calificado como tal al valorar la reserva

  Importe por habitación
    Importe a aplicar por habitación

  Importe por reserva
    Importe a aplicar por reserva


******************
Límites de crédito
******************

Podemos limitar el riesgo que qeremos asumir con un cliente utilizando los límites de crédito.

Los límites de crédito los definimos a nivel general y luego los asignamos en cada cliente.

De esta manera, varios clientes pueden compartir un mismo límite de crédito.

Para mantener los límites de crédito debemos ir a CRM --> Límites de crédito

Para cada límite de crédito debemos proporcionar


Nombre
  Para identificar este límite de crédito

Límite
  Importe del riesgo

Moneda
  Moneda en que está expresado el riesgo

Restante
  Campo de salida que nos muestra el riesgo que hemos consumido

Restante
  Campo de salida que nos muestra el margen que nos queda, antes de llegar al límite

Porcentaje
  Campo de salida que nos muestra el porcentaje del riego que hemos consumido

Umbral de notificación
  Con que importe consumido deben mandarse notificaciones por email

Emails
  A que emails hay que notificar cuando se alcance el umbral de notificacón, o cuando se produzca una alteración en el estado del cliente relacionada con este límite de crédito.


Luego en el partner podemos indicar un límte de riesgo para producción (reservas no facturadas) y otro para facturación (facturas no pagadas).


******
Rappel
******

En QuoTravel podemos indicar rappels (descuentos por volúmen de facturación) tanto para clientes como para proveedores.

Los rappels los mantenemos en CRM --> Rebate

El importe del rappel es un dato que no sabemos realmente hasta que no ha terminado el periodo que está indicado en el rappel, así que no podemos reflejarlo en la reserva más que a título informativo.

A medida que los rappel se van liquidando las facturas van quedando asocidas a esa liquidación, de manera que no se puede incluir la misma factura en dos liquidaciones diferentes.


La forma que que se materializa la liquidación del rappel varía de si es un rappel que damos a un cliente, o de si es un rappel que nos da un proveedor.

En el caso del rappel que damos a un cliente, a medida que vayamos emitiendo facturas iremos incluyendo un descuento en la misma hasta haber alcazado el importe de la liquidación del rappel. En el rappel podemos indicar el máximo descuento en factura (tanto en forma de importe como en forma de porcentaje).

En el caso del rappel que nos da un proveedor simplemente indicamos el descuento debido al rappel que figura en la factura, y esto irá rebajando el saldo de la liquidación del rappel.




Nombre
  Para identificar este rappel

Base aplicación
  Cada cuanto debemos liquidar este rappel.

  Admite los siguientes valores

  - Anualmente
  - Semestralmente
  - Trimestralmente
  - Mensualmente
  - Semanalmente

Fecha de la próxima liquidación
  Aquí indicamos la fecha de la próxima liquidación.

  Cuando liquidamos esta fecha se actualiza automáticamente de acuerdo con la base de aplicación.

Liquidación automática
  Si lo marcamos entonces se generará una línea de cargo automática a medida que se vaya cumpliendo la base de aplicación, con lo que aparecerá como disponible para facturar.

Comentarios
  Comentarios internos

Porcentaje
  Si este rappel es un porcentaje lineal

Líneas
  Si este rappel no es un porcentaje lineal, entonces utilizamos este escalado

  Desde importe
    Desde que importe es aplicable este porcentaje
  Hasta importe
    Hasta que importe es aplicable este porcentaje
  Porcentaje
    Porcentaje a aplicar para este tramo de factración

Descuento máximo en factura
  Descuento máximo que harems en la facturas futuras para liquidar el rappel. Lo podemos expresar en forma de porcentaje o en forma de importe.


Tanto para consular las liquidaciones anteriores como para liquidar el rappel manualmente tenemos que ir a Financial --> Liquidaciones.

Si queremos crear una liquidación QuoTravel nos pedirá una fecha límite y mostrará un listado con los clientes y el importe a liquidar a la fecha que le hemos indicado, teniendo en cuenta el porcentaje y el escalado indicado en su rappel.

Naturalmente si no hemos indicado ningún rappel para ese cliente no aparecerá ningún importe a liquidar.

A partir de aquí simplemente marcaremos los clientes que queremos liquidar y generará las liquidaciones pertinentes.


*******************
Condiciones de pago
*******************

Para gestionar las diferentes condiciones de pago debemos ir a CRM --> Condiciones de pago

Para cada conjunto de condiciones de pago debemos indicar

Nombre
  Para identificar este conjunto de condiciones de pago

Líneas
  El desglose de este conjunto de condiciones de pago

  Para cada línea deberemos indicar

  Fecha de referencia
    Fecha a tener en cuenta para saber cuando hay que pagar / cobrar

    Puede ser

    - Fecha de confirmación de la reserva
    - Fecha de entrada de los clientes / inicio del servicio
    - Fecha de salida e los clientes / fin del servicio
    - Fecha de factura

  Release
    Nº de días en positivo o negativo a sumar a la fecha de referencia

  Días de pago
    Lista de días del mes o de la semana seprados por comas. El día 31 es el último día del mes. MTWXF para los días de la semana. Si coincide con fín de semana o festivo se pasa al siguiente día laborable.

  Porcentaje
    Porcentaje del importe a pagar.
    En el caso de tener como referencia la fecha de factura el importe base es el importe de la factura.
    En el resto de los casos el importe base es el importe del servicio


**************************
Condiciones de cancelación
**************************

Para mantener las condiciones de cancelación debermos ir a CRM --> Condiciones de cancelación

Siempre se aplica la opción más cara de las que coincidan.

Para cada conjunto de condiciones de cancelación deberemos indicar:

Nombre
  Para identificar este conjunto de condiciones de cancelación

Líneas
  Las diferentes condiciones de cancelación.

  Para cada línea deberemos indicar:

  Fecha inicio
    Esta línea es aplicable a las reservas con fecha de entrada posterior o igual a la fecha indicada

  Fecha final
    Esta línea es aplicable a las reservas con fecha de entrada anterior o igual a la fecha indicada

  Release
    Esta línea es aplicable a las reservas si el nº de noches hasta la entrada el cliente es igual o inferior al valor indicado

  Importe
    Importe fijo

  Moneda
    Moneda en que está expresado el importe

  Porcentaje
    Porcentaje sobre el importe de venta

  Noches
    En el caso de las reserva de hotel, el nº de noches a aplicar

  Que noches
    En el caso de ser una reserva de hotel y haber expresado el coste de cancelación en nº de noches, que noches debemos utilizar para calcular el coste de cancelación.

    Los posibles valores son:

    - Primeras noches
    - Últimas noches
    - Las más baratas
    - Las más caras
    - Precio medio


**********
Comisiones
**********

Para mantener las comisiones tenemos que ir a CRM --> Comisiones

Las comisiones se aplican tanto a clientes como proveedores, y pueden convertirse en un descuento o en una comisión real con su iva correspondiente.

En ambos casos se genera una línea de cargo que facturaremos, utilizaremos para validar la factura del cliente, o se aplicará como un descuento en la factura.

En el caso de las reservas que son pago directo en el hotel será el único servicio que vamos a facturar, con lo que será la única línea de cargo existente en la reserva.

Las comisiones se van liquidando con cada reserva o pedido de compra.

Para cada comisión deberemos indicar:

Nombre
  Para identificar este conjunto de reglas de comisiones

Líneas
  El desglose de las diferentes comisiones por producto

  Para cada línea deberemos indicar

  Partner
    Para que agencia es aplicable este porcentaje.

    Si este campo está vacío, este porcentaje es aplicable a cualquier agencia

  Producto
    Para que producto es aplicable este porcentaje.

    Si este valor está vacío este porcentaje es aplicable a cualquier producto

  Concepto de facturación
    Concepto de facturación a utilizar cuando se genera la línea de cargo.

    Recordar que el concepto de facturación marca la aplicación del IVA.

  Fecha inicio
    Esta comisión es aplicable a servicios con fecha de inicio mayor o igual a la fecha indicada

  Fecha fin
    Esta comisión es aplicable a servicios con fecha de inicio menor o igual a la fecha indicada

  Porcentaje
    El porcentaje de la comisión


*******
Cupones
*******

Los cupones son descuentos concretos a aplicar sobre una venta.

El cupón puede representar un descuento porcentual, un descuento concreto o un precio final.

Para cada descuento que creemos podemos indicar:

- destinatarios del descuento
- cupo (cuantas veces se puede aplicar este descuento)
- porcentaje
- importe descuento
- importe final
- si está activo
- booking window


El cliente actiuva el descuento al introducir el código del mismo cuando realiza la reserva.

También podemos aplicarlo directamente desde el backoffice.

Solo se admite un cupón por reserva.

Luego podemos consultar en que reservas se ha aplicado el descuento.


