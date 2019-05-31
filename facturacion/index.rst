##############
ERP financiero
##############

Aquí explicaremos toda la parte relacionada con la emisión y la validación de facturas, con la gestión de cobros y pagos, y con el enlace con el programa contable.


***********
Facturación
***********

Aquí explicaremos toda la parte relacionada con la emisión y la validación de facturas.


Modelo de datos
===============


Para entender bien la parte de facturación es necesario explicar un poco el modelo de datos.

La facturación se basa en lo que llamamos cargos. Con las líneas de cargo indicamos tanto una deuda que el cliente ha contraído con nosotros como una deuda que hemos contraído nosotros con un proveedor.

Luego esas líneas de cargo las asociamos con su factura correspondiente en el momento en que facturamos, o en el momento en que validamos una factura de un proveedor.

Es importante entender la simetría entre los 2 caminos: emisión de facturas a cliente y validación de facturas de proveedor.

De hecho, son los mismo objetos.


Entonces, el sistema va acumulando líneas de cargo que se han generado desde las reservas y pedidos de compra. Desde la reserva siempre podemos llegar a ellas.

En un momento dado, ya sea de manera automática o manual como veremos más adelante, transformamos esas líneas de cargo en facturas que enviamos después a nuestros clientes.

En el camino opuesto, asociamos esas líneas de cargo (también de manera automática o manual) con las facturas que hemos recibido de los proveedores.


Es importante también entender que los agentes de facturación (a quien emitimos o de quien recibimos facturas) es una entidad independiente de la entidad partner (que utilizamos para identificar a agencias y/o proveedores) que utilizamos en la parte de negocio.



Agentes de facturación
======================

El agente de facturación identifica a quien emite o recibe facturas. Esto es, un nif y un nombre.

Nosotros también debemos figurar como agente de facturación.

Las facturas (tanto las emitidas como las recibidas) son de un agente de facturación a otro.

El agente de facturación es también el propietario de los pagos y cobros.

La asociación de un partner (agencia o proveedor) en la parte de negocio con un agente de facturación se hace desde la entidad partner, en CRM --> Partners.


Para mantener los agentes de facturación debemos utilizar la opción Financial --> Agents.

Para cada agente de facturación podemos indicar:


General
  Información general del cliente

  Nombre
    El nombre "coloquial" de la empresa
  Nombre fiscal
    El nombre que debe aparecer en las facturas
  Dirección
    La dirección de la empresa
  Código postal
    El código postal de la empresa
  Localidad
    La localidad de la empresa
  Provincia
    La provincia en que está ubicada la empresa
  País
    El país de la empresa
  Teléfono
    Teléfono de la empresa
  Fax
    Fax de la empresa
  Email
    El email de la empresa. Aquí es donde vamos a enviar las facturas.
  Comentarios
    De uso interno

Impuestos
  Información para la aplicación del IVA

  Nº identificación fiscal
    Lo que sería el NIF
  Impuesto
    A que tipo de impuesto pertenece este cliente. Si está vacío este cliente / proveedor estará exento de iva.
  Pertenece a la CEE
    Si lo marcamos, las operaciones con este agente aparecerán marcadas como intracomunitarias

Como cliente
  Información para este cliente como destinatario de las facturas que emitimos

  Venta directa
    Lo marcaremos para indicar que este cliente es de contado

  Regla de facturación automática
    Si queremos que se le facture automáticamente o manualmente.

    En el caso de querer facturación automática, podemos elegir el momento de la emisión de facturas:

    - en el momento de confirmar la reserva
    - al comenzar el servicio
    - al terminar el servicio

  Último día del mes
    Para indicar que queremos que las facturas se emitan el último día del mes

  Quincenal
    Para indicar que queremos que se emitan las facturas los días 1 y 15

  Release
    Si es facturación automática, podemos indicar un release para indicar por ejemplo 3 días antes de la entrada de los clientes, o 5 días después de la salida. También lo podemos utilizar para indicar que queremos facturar el día 2 en lugar del día 31.


  Agrupación de servicios en facturas
    Aquí podemos indicar como queremos que se distribuyan los cargos en las facturas

    - todo lo pendiente en una misma factura
    - una factura por reserva
    - una factura por fecha de entrada
    - una factura por vuelo

  Separar servicios
    Si marcamos esta opción generará facturas diferentes para cada tipo de servicio: hotel, traslado, excursiones, ...

  Condiciones de pago
    Condiciones de pago como cliente, para las facturas emitidas

  Email facturación
    Email al que enviaremos las facturas

  Email facturación CC
    Email al que enviaremos en copia las facturas

  Método de envío de las facturas
    Puede ser email o Voxel

  Nº de cuenta como cliente
    Para el enlace contable


Como proveedor
  Aquí rellenamos la información relativa a esta empresa cuando actúa como proveedor nuestro

  Régimen especial
    Lo marcamos para indicar que este agente nos puede enviar facturas en régimen especial, lo que hace que no nos podamos acoger al régimen general cuanso emitamos una factura que incluya servicios de este proveedor

  Permitir facturas antes de la fecha de entrada
    Lo marcamos si podemos acptar facturas de este proveedor antes de la entrada de los clientes. Si no está marcado, esas facturas se rentendrán hasta que llegue la fecha de inicio del servicio

  Retención
    Para el caso de que debamos retener IRPF de las facturas recibidas

  Método de pago
    Método de pago de sus facturas

  Pagos bloqueados
    Si marcamos esta opción no podremos efectura pagos a este agente. Podmeos indicar también un motivo del bloqueo, ara acordarnos más tarde de por que hemos marcado esta opción

  CC
    Aquí indicamos el nº de cuenta corriente que utilizaremos en el pago por transferencia

  IBAN
    Aquí indicamos el IBAN que utilizaremos en el pago por transferencia

  SWIFT
    Aquí indicamos el código swift para las transferencias


Crédito
  Aquí indicamos el crédito que damos a este cliente

  Tipo de riesgo
    Aquí indicamos si el cliente tiene crédito o si es de prepago

  Límites de crédito
    Aquí indicamos los límites de crédito de este cliente. Recordar que los límites de crédito los damos de alta en CRM --> Límites de crédito y que pueden ser compartidos por varios agentes

Voxel
  Aquí indicamos la información relativa a la integración con Voxel

  ID Voxel
    El identificador de este agente en Voxel





Líneas de cargo
===============

Para poder facturar algo a un cliente primero tenemos que introducir lo que queremos facturar en forma de líneas de cargo.

Para emitir una factura el camino es:

# introducir la deuda del cliente en forma de líneas de cargo
# crear facturas a partir de las líneas de cargo

Normalmente las líneas de cargo se generan automáticamente desde las reservas, por la liquidación de una garantía, al liquidar el rappel de un proveedor, o al retroceder una factura, o al introducir un depósito, o al ir consumiendo un depósito.

Análogamente tendremos que introducir líneas de cargo si queremos validar una factura de un proveedor.

En el caso de las líneas de argo asociadas a compra / proveedor éstas normalmente se generan automáticamente desde un pedido de compra, los depósitos,


Para cada línea de cargo debemos indicar:


Tipo
  Nos indica la naturaleza de la línea de cargo. Puede ser

  - Reserva
  - Compra
  - Liquidación garantía
  - Liquidación depósito

Moneda
  La moneda en que están expresados los importes

Concepto de facturación
  Lo que estamos cargando. Con fines estadísticos y para determinar la aplicación del IVA.

Texto
  Texto descriptivo del cargo

Cantidad
  Nº de unidades

Importe
  El precio de cada unidad, impuestos incluidos. Es el único importe que podemos modificar

Total
  Total para este cargo. Es un campo calculado, no se puede modificar

Reserva
  Reserva asociada con este cargo

Servicio
  Servicio asociado con este cargo

Contrato hotel
  Contrato de hotel relacionado con este cargo, en el caso de que sea una liquidación de una garantía

Pedido de compra
  Pedido de compra relacionado con este cargo.

Agencia
  Agencia a la que se ha hecho el cargo

Factura
  En que factura se ha incluido este cargo

Liquidación
  Liquidación de punto de venta (representante) en la que se ha liquidado este importe


Es importante resaltar que todos los importes que introducimos en QuoTravel son con impuestos incluidos. Luego, en función del concepto de facturación y de otros factores, QuoTravel es capaz de deducir que impuestos y porcentajes debe aplicar.



Factura
=======

La factura en QuoTravel uede ser tanto factura emitida como factura recibida.

Es en la factura donde residen el IVA, las retenciones y los vencimientos relativos a fecha de factura.

Para cada factura tenemos la siguiente información:


Auditoría
  Quien ha creado esta factura y cuando, así como quien ha sido el último en modificarla y cuando.

Número de factura
  Nº de la factura. Se genera automáticamente, pero podemos sobreescribirlo

Fecha de emisión
  Fecha de emisión de la factura

Fecha impuestos
  O fecha contable

Emisor
  Quien ha emitido esta factura

Destinatario
  Quien es el destinatario de esta factura

Total
  Total de esta factura, con impuestos incluidos

Régimen
  Si es régimen especial o régimen general

Total antes impuestos
  Total sin impuestos

Total impuestos
  Total IVA

Desglose impuestos
  Líneas con su base, porcentaje y total IVA para cada impuesto y porcentaje

Porcentaje retención
  Porcentaje retención IRPF

Total retención
  Importe de la retención

Vencimientos
  Lista de vencimientos, cada uno con su fecha e importe



En el caso de una factura emitida podemos sobreescribir los datos del destinatario (caso factura contado):


Nombre
  Nombre del cliente

Nombre fiscal
  Nombre fiscal del cliente

NIF
  Identificación fiscal del cliente

Dirección
  Dirección del cliente

Localidad
  Localidad del cliente

País
  País del cliente

Código postal
  Código postal del cliente

Teléfono
  Teléfono del cliente

Fax
  Fax del cliente

Email
  Email del cliente



Línea de factura
================

Las líneas de factura contienen la siguiente información:

Nuestro localizador
  Nuestro identificador para la reserva

Su localizador
  La referencia de la agencia para este servicio

Fechas servicio
  Fecha de inicio y de fin del servicio

Titular
  Titular de la reserva

Servicio
  El servicio al que hace referencia esta línea de factura

Concepto
  Descripción de lo incluido en esta línea de factura

Importe impuestos incluidos
  Total para esta línea


Línea de IVA
============

Las líneas de iva contienen la siguiente información:

Factura
  Factura relacionada

Impuesto
  IVA, IGIC, ...

Base
  Base imponible

Porcentaje
  Porcentaje aplicado

Total impuesto
  Total IVA

Total
  Ttal IVA incluido




Emisión de facturas
===================

En los siguientes apartados revisaremos la emisión de facturas a clientes


Series de facturas
------------------

En Financial --> Facturación --> Series de facturas podemos configurar nuestras series de facturas.

Luego en cada empresa configuramos las series que vamos a utilizar para las facturas emitidas y para las autofacturas de comisiones.

Para cada serie podemos indicar un prefijo y el nº que se utilizará en la siguiente factura. El sistema comprueba, cuando genera las facturas, que no haya ninguna factura con ese nº y, si fuese así saltaría hasta encontrar un nº libre.

No puede haber dos facturas con el mismo número. Tampoco se permite que se repita el nº de factura de un proveedor.


Manual / automática
-------------------

La emisión de facturas puede ser manual o automática, y el modo de facturación lo decidimos cliente por cliente.

En el caso de haber elegido facturación automática el sistema irá generando facturas automáticamente según las reglas que hemos indicado en la ficha del agente, que nos indican el momento de facturar y la manera en que distribuimos los cargos pendientes en facturas.

El sistema enviará las facturas automáticamente al cabo de 2 horas de haberlas generado, ya sea por email o por Voxel según esté configurado.


Diferentes criterios para generar las facturas
----------------------------------------------

Como hemos visto en la fecha del agente de facturación, podemos indicar diferentes criterios para generar nuestras facturas: momento de facturar y modo de agrupar los cargos.

Esos criterios se utilizan en la facturación automática y en la facturación manual.

Los diferentes criterios ya los hemos visto anteriormente cuando hemos revisado el agente de facturación.

Esto quiere decir que, cuando facturemos manualmente, se generarán tantas facturas como sea necesario para cumplir el modo de agrupación que hemos indicado en la ficha del cliente.

Si quisiéramos agrupar los cargos de froma diferente, tendríamos que ir selccionando cargos y facturando o cambiar la configuración del agente.


Cargos no facturables
--------------------

Desde la reserva podemos decidir bloquear líneas de cargo cuando no queremos que se facturen.

Sería el caso de reservas en las que el departamento de booking está trabajando, cuay valoración no ha cerrado todavía, y no quiere que por error se fecture.

Tampoco se emite factura de aquellas reservas que se han cancelado y de las que no existen gastos de cancelación. Es decir, que el total a facturar suma 0.



Factura de anticipos
--------------------

Cuando un cliente nos hace un pago por anticipado automáticamente se genera un cargo por el importe del depósito.

Ese cargo se puede facturar y generará una factura con su iva correspondiente.

A medida que vayamos asociando facturas a ese depósito se generarán cargos en negativo que, al facturarlos, compensarán la factura del depósito para recuperar el iva

Al final, solo quedarán las facturas correspondientes a los servicios prestados, cada uno con su iva y régimen correspondiente.


Anulación de facturas
---------------------

En QuoTravel se pueden anular facturas mientras no se hayan contabilizado, ni enviado al cliente, ni enviado al SII.

Si la factura se ha contabilizado ya se puede desde el mantenimiento de facturas generar un abono, y facturar de nuevo.



Autofactura comisiones
----------------------

Cuando emitimos una factura para un servicio del que vamos a cobrar una comisión podemos generar, para cada factura emitida, la correspondiente factura de comisión como si el cliente nos la hubiese mandado.

Esta factura se matará automáticamente con una línea de cargo para esa comisión y quedará todo correctamente cerrado.

Esa factura de comisión llegará al cliente conjuntamente con las facturas emitidas.

Si generamos la autofactura por la comisión o no lo indicamos en la ficha del partner.




Control de incidencias / reclamaciones
======================================

En QuoTravel podemos indicar las incidencias que surgen con la facturación a nuestros clientes. Esto es, que el cliente no está conforme con lo que le estamos facturando.

Podemos registrar la incidencia, que automáticamente es visible desde las facturas y desde las reservas afectadas.

También nos permite controlar las incidencias que tenemos pendientes, ir añadiendo comentarios con las diferentes conversaciones que tenemos con el cliente y anotar alarmas para que nos mande un recordatorio un día determinado.

Las incidencias las mantenemos en Financial --> Litigations.

La incidencia acaba cuando cobramos o asumimos la pérdida, o ambas cosas. En caso de asumir la pérdida se generará una línea de cargo por el menor valor, que luego acabará en una factura para recuperar el iva y que tenga su correspondiente reflejo contable.


Validación facturas de proveedor
================================

En este apartado veremos todo lo referente a la recepción de facturas de nuestros proveedores.

Las facturas de proveedores tienen la misma estructura que las facturas a clientes.

Tanto si entran automáticamente desde Voxel o desde un proceso de importación, como si las introucimos manualmente, las facturas pueden ser incorrectas. Esto es, que les falten datos como el nº de factura, nuestro localizador, etc.

Si la factura tiene algún problema de forma se marca como incorrecta, y queda a la espera de que la corrijamos manualmente o de que la anulemos.

Si la factura está bien formada (es correcta), entonces se comprueba si es válida.

Cuando se introuce una factura de un proveedor en el sistema esta se valida automáticamente.

Esto quiere decir que, si hay previsión (líneas de cargo que no se han matado todavía con ninguna factura) suficiente, la factura queda automáticamente validada.

Si no hay previsión suficiente la factura queda como no validada, a la espera que que haya previsión suficiente para validarla.

La validación se volverá a intentar automáticamente cada noche, si entramos en la factura y grabamos, y también se puede lanzar explícitamente desde el mantenimiento de facturas de proveedor.



Introducción de facturas
------------------------

El grueso de las facturas de proveedores normalmente llegará al sistema de manera automática, a través de las plataformas de facuración electrónica (Voxel) o de los procesos de importación.

Normalmente la introducción de facturas de manera manual debería ser una parte cada vez más pequeña.

Las facturas que vienen de Voxel o a través de un proceso de importación entran (y se validan) automáticamente.

En el caso de facturas que necesitemos entrar de manera manual podemos hacerlo de varias maneras:

- desde la previsión, consultando la previsión que tenemos de ese proveedor y matándola con la factura.
- entrando la factura directamente, sin consultar antes la previsión

En el caso de entrar la factura directamente podemos hacerlo desde el mantenimiento de facturas, creando cada factura y rellenando sus líneas, o de manera masiva.

En el caso de la introducción masiva lo hacemos en una pantalla que nos permite ir entrando una secuencia de líneas (nº factura, fecha factura, proveedor, nº de pedido, importe) y grabando en el momento que queramos. En el momento en que grabamos desaparecen de la pantalla todas las líneas que han sido validadas correctamente y nos quedan únicamente las líneas que no se han podido validar porque no hay previsión. En este caso, para cada línea, podemos decidir grabarlas igualmente y quedarán pendientes de validar, aceptar un mayor valor, o apartamos la factura y las descartamos para volver a introducirlas más adelante.

El sistema por defecto no acepta facturas de proveedores que no sea el que tenemos en la previsión. No obstante podemos configurar que sea más permisivo, indicando en el partner --> puede facturar desde otras empresas.


Importación de facturas de proveedores (no Voxel)
^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^

También podemos introducir las facturas de proveedor desde un excel o csv.

Para ello debemos utlizar la opción Importar del listado de facturas de proveedor.

El sistema nos pedira la empresa, el proveedor y un fichero excel o csv.

El excel o csv debe tener las siguientes columnas:

- Nº factura
- Fecha factura
- Nº pedido
- Concepto
- Base
- Impuesto
- Total
- Moneda

El sistema importará las facturas y nos devolverá un informe.

Si faltan datos en alguna línea no se importa nada.

Si el documento está bien formado entonces las importa todas, haya previsión o no.


Margen configurable
-------------------

A la hora de validar las facturas de los proveedores podemos decidir aceptar una pérdida si está dentro de un margen. Por ejemplo 0,05 euros.

Para configurar ese margen lo hacemos a nivel de empresa, en Admin --> Empresa --> Margen validación facturas proveedor.

Abonos y mayor valor
--------------------

En el caso de que una factura no sea valida porque no hay previsión suficiente, la única manera de que entre es modificando la factura del proveedor o aceptando un mayor valor.

El mayor valor en una línea de cargo a favor del proveedor, y la podemos generar desde la factura misma o desde Financials --> Facturación --> Líneas de cargo.

Al haber previsión la factura ya se puede validar.

Recordar que los abonos deben utilizar una serie diferente a la serie de las facturas emitidas, que indicamos en la empresa.


Retenciones
-----------

En el caso de hayamos indicado en nuestro proveedor que está sujeto a retencioones (IRPF) automáticamente de crea un línea de retención para esa factura, que tendrá su reflejo contable.

Las retenciones pueden liquidar en el momento que queramos, y tenemos un informe para cada liquidación con las retenciones incluidas.


Autofactura
===========

Nosotros podemos autofacturar (generar facturas como si las hubiese enviado un proveedor) a un proveedor, o podemos ser objeto de autofactura por parte de un cliente (el cliente nos informa de las facturas que debemos registrar como emitidas por nosotros al cliente).

En el caso de que queramos generar nosotros las facturas de un proveedor basta ir la previsión de proveedor y seleccionar "Generar autofacturas".

El sistema nos pedirá la fecha de factura y generará las facturas (a partir de la previsión) como si nos hubiesen llegado de ese proveedor. Naturalmente quedarán automáticamente validadas y listas para ser pagadas.

En el caso de seamos objeto de autofactura por parte de un cliente simplemente debemos importar las facturas cuando nos las envíe, como se explica en el siguiente punto.


Importación de facturas generadas por un cliente
------------------------------------------------

Para importar las facturas generadas por un cliente (autofacturas) deberemos utilizar la opción "Importar autofacturas" del listado de facturas emitidas.

El sistema nos pedirá la empresa, el cliente y un fichero excel o csv.

El excel o csv deberá contener las siguientes columnas:

- Nº factura
- Fecha factura
- Su referencia
- Concepto
- Base
- Impuesto
- Total
- Moneda

El sistema importará las facturas y nos devolverá un informe.

Si faltan datos en alguna línea del csv no se importa nada.

Las facturas quedarán relacionadas con sus reservas correspondiente y quedarán como impagadas, a la espera de que metamos el cobro.

En el caso de existir alguna diferencia entre nuestra valoración de la reserva y lo que elos nos dicen que tenemos que facturar se genera una línea de cargo por la diferencia, con una marca especial para que podamos luego controlarlas.



Voxel
=====

Voxel es una plataforma de facturación electrónica que nos permite enviar facturas a nuestros clientes y recibir facturas de nuestros proveedores.

QuoTravel está integrado con Voxel para enviar y recibir facturas.

La integración con Voxel es automática. Esto quiere decir que no es necesaria la intervención manual.

En cuanto al envío de facturas a nuestros clientes, Voxel aparece como un método de envió má. Igual que podemos enviar las facturas por email, podemos enviarlas por Voxel.

Cuando la factura la enviamos por Voxel la factura aparece como enviada igual que si la hubiésemos enviado por email, y simplemente vemos en el histórico de tareas relacionadas con esa factura que en un fecha y hora determinada fueron enviadas por Voxel.

Los acuses de recibo que reporta Voxel también tienen su reflejo en la factura dentro de QuoTravel, con lo que podemos ver en cualquier momento si la factura ha llegado a su destinatario.

Hay un alarma en el sistema que controla que las facturas acaben marcadas como "recibidas".

En cuanto a la recepción de facturas casi no vemos nada. Simplemente las facturas van entrando en el sistema y se van validando automáticamente si hay previsión, a medida que van llegando.

Recordar que tenemos informes que nos permiten ver de manera fácil las cantidades recibidas y validadas para cada proveedor.


SII
===

QuoTravel está integrado con el SII.

Esto significa que las facturas que emitimos y las que recibimos se envían al SII, ya sea de manera manual o de manera automática.

El modo en que enviamos las factras (automático / manual) lo configuramos en Admin --> Empresa.

Las facturas emitidas se pueden enviar al SII en cualquir momento, pero las facturas recibidas solo se pueden enviar cuando han sido validadas.

QuoTravel registra la confirmación de que la factura ha sido correctamente procesada por el SII.

Desde el momento en que una factura ha sido enviada al SII dicha factura se bloquea y no puede ser modificada.

Existe una alarma que no avisa cuando hay facturas de las que no tenemos el ok del SII 2 días después de la fecha de factura, para no incurrir en penalización por no enviar las facturas dentro de los 4 días que marca el SII.

En el caso de que haya facturas que hayan sido rechazadas por no coincidir el nombre de la empresa con el nif se crea una incidencia a la espera de que indiquemos el nif y el nombre correcto del cliente o proveedor.

Al corregir los datos se actualizará la ficha del partner, se corrigen las facturas y se vuelven a enviar al SII.


Facturación multiempresa
========================

Como hemos dicho antes QuoTravel es un sistema multiempresa.

Esto quiere decir que coexisten varias empresas en nuestra base de datos, cada una con su contabilidad.

A un cliente podemos emitirle facturas desde cualquiera de nuestras empresas, y las facturas de nuestros proveedores las irán recibiendo las empresas pertinentes.

Podemos configurar QuoTravel para que vaya generando facturas entre nuestras empresas para aquellos casos en que el que recibe la factura del proveedor es una empresa mientras que el que ha emitido la factura al cliente es una empresa diferente.

El resultado final es que cada reserva tiene su venta y su coste.

Podemos configurar la facturación entre empresas para que deje una parte del beneficio en una u otra empresa (porcentaje).

El proceso que genera estas facturas se puede iniciar de manera manual o dejarlo programado para que se ejecute periódicamente.




**************
Cobros y pagos
**************


Cuentas
=======

En QuoTravel unificamos los conceptos de cuenta bancaria y caja en la entidad cuenta.

Para manterner las cuentas debemos ir a Financial --> Payments --> Accounts

Para cada cuenta deberemos indicar

Nombre
  Para identificar la cuenta

CCC
  Nº de cuenta, en el caso de tratarse de un banco

IBAN
  IBAN, en el caso de tratarse de un banco

Nº cuenta contable
  Nº de cuenta contable, a utilizar en los apuntes contables relacionados con esta cuenta


Para cada cuenta tenemos un saldo y una fecha del último cierre.

En cualquier momento podemos liquidar o cerrar una cuenta, indicando la fecha del último movimiento que queremos incluir en la liquidación.

Los cierres se pueden consultar en cualquier momento, y generar un documento para ser firmado por quien sea necesario.


Movimientos
===========

Sobre una cuenta podemos realizar movimientos, que pueden corresponder a cobros, pagos o movimientos entre cuentas.

Para mantener los movimientos deberemos ir a Financial --> Payments --> Movements


Para cada movimiento deberemos indicar

Origen
  Cuenta de la que sale el dinero

Destino
  Cuenta a la que entra el dinero

Agente financiero
  Agente que realiza o recibe el pago

Estado
  Un movimiento puede estar marcado como Ignored si no queremos que tenga un reflejo contable. Esto se utiliza cuando importamos un extracto bancario y existen entradas que no están relacionadas con la actvidad de la empresa.

  También puede estar en estado pending, sent o confirmed.

  Un pago puede estar PENDING cuando por ejemplo es una transferencia y no hemos generado la remesa que tenemos que enviar al banco. Estará en estado SENT cuando hemos enviado la remesa al banco y estará en estado CONFIRMED cuando vemos el movimiento en el extracto del banco.

Log
  De un movimiento vamos guardando los diferentes cambios de estado que van sucediendo.

  Para cada cambio de estado guardamos el usuario, la fecha y la hora y el nuevo estado.

Moneda
  Moneda de la operación

Importe
  Importe de la operación, antes de costes

Coste de la operación
  Coste de la operación. Es la regla que se utiliza para el cálculo del coste de la operación.

Importe del coste de la operación
  A rellenar en caso de que se haya seleccionado coste manual

Reparto
  Como se reparte el importe de este movimiento.

  Qué importe corresponde a cada factura o reserva.

  Si no es un traspaso, el movimiento siempre debe quedar liquidado. Si no es así, el saldo pendiente se considera que es un depósito.


Al menos la cuenta de origen o la de destino deben estar indicadas y, en el caso de faltar una de ellas, el agente es obligatorio.


Cobros
======

Aquí explicaremos algunas pecularidades relacionadas con los cobros

TPV
---

QuoTravel está integrada actualmente con Sermepa, con Paypal y con Webpay.

Esto quiere decir que podemos emitir cobros con cualquiera de estas pasarelas de pago.

Independientemente de si la reserva se realiza por la web o si la estamos introduciendo desde el backoffice, el sistema generará la transacción para la pasarela de pago pertienente si así está configurado en la forma de pago del cliente.

Esta transacción genera un link que podemos enseñar al cliente en la web, utilizarlo para redireccionar automáticamente al cliente, o que podemos mandar en un correo electrónico al cliente.

Mientras el cliente no intenta la operación, la transacción aparece como pendiente.

Cuando el cliente realiza el pago (vaya bien o no) recibimos la notificación por parte de la pasarela de pago y lo reflejamos en la transacción, con los datos reportados por la pasarela.

Si el pago ha ido bien, se crea un movimiento de caja y se asocia con la reserva y con la factura si es pertinente.

Si el pago no ha ido bien no se genera ningún movimiento de caja, y podemos ver la causa del error al consultar la transacción.

Para mantener las pasarelas e pago debemos ir a Financial --> Payments --> TPV

Para cada TPV debemos indicar:


Nombre
  Para identificar esta pasarela de pago

Cuenta banco
  Sobre que cuenta de banco se creará el movimiento en caso de que la operación tenga éxito

Oficina
  Con que oficina se relacionará la operación

Action url
  La url de la pasarela de pago

Notification url
  URL a la que la pasarela de pago debe enviar la información sobre el éxito o fracaso de la operación

OK url
  URL a la que hay que redireccionar al cliente si la operación va bien

KO url
  URL a la que hay que redireccionar al cliente si la operación no va bien

Tipo
  El tipo de pasarela de pago.

  Actualmente soportamos:

  - Sermepa
  - Paypal
  - Webpay

Paypal
  Datos específicos para Paypal

  Email
    Email que identifica nuestra cuenta en Paypal

Sermepa
  Datos específicos para Sermepa

  Merchant code
    Proporcionado por Sermepa

  Merchant name
    Proporcionado por Sermepa

  Merchant secret
    Proporcionado por Sermepa

Webpay
  Datos específicos para Webpay

  Private key
    Clave privada que se utiliza para encriptar todo el proceso


Podemos consultar las transacciones creadas y su estado en Financial --> TPV --> Transactions

Para cada transacción tenemos

Id
  Nº que identifica esta transacción

TPV
  Pasarela de pago relacionada con esta transacción

Auditoría
  Fecha y usuario que han creado esta transacción

Momento fin
  Fecha y hora en que se ha cerrado la transacción

Estado
  Si ha ido bien o si ha habido un problema

Importe
  Importe de la transacción

Moneda
  Divisa de la transacción

Reserva relacionada
  Reserva relacionada con esta transacción

Movimiento de caja
  Movimiento de caja generado, en el caso de que la operación haya terminado satisfactoriamente.


Recordar que los pagos por TPV se pueden generar desde la reserva, desde la factura o directamente desde el mantenimiento de TPVS o de transacciones de TPV.

Conciliación bancaria (importación extracto banco)
--------------------------------------------------

En QuoTravel podemos importar extractos bancarios.

Para introducir un extracto bancario deberemos ir a Fianncials --> Payments --> Accounts, seleccionar una cuenta y, desde ella, seleccionar la opción "Import banc extract".

Nos aparecerá una ventana para pedirnos el fichero y la opción para importarlo.

QuoTravel comproará entonces que el nº de cuenta coincide y, si es así, generará los movimientos pertinentes.

Luego podemos revisar los movimientos e irlos asociendo con las reservas, facturas y otros movimientos, así como marcarlos para que sean ignorados si no están relacionados con nuestra actividad.

Los movimiento arcdos como "ignore" no se contabilizan.

Podemos configurar QuoTravel para que establezca la relación automáticamente (en base por ejemplo a encontrar el localizador de la reserva en el asunto), pero es un desarrollo ad hoc que queda fuera del estándar.


Depósitos
---------

A efectos prácticos un depósito es cualquier movimiento de caja que no hemos justificado.

Si tenemos un movimiento de caja relacionado con un cliente y no justificamos el importe del mismo asignándolo a reservas y/o facturas, el importe pendiente puede ser utilizado cuando queramos cobrar una reserva o factura.

Lo mismo pasa cuando el movimiento es hacia un proveedor. Mientras no lo repartamos, el importe pendiente de reparto puede ser utilizado para pagar pedidos de compra y/o facturas de ese proveedor.

Para justificar un depósito podemos generar una factura desde cualquier movimiento de caja.

Simplemente vamos al movimiento en cuestión y seleccionamos la opción "Generar factura de depósito".

Esta operación generará una línea de cargo y una factura, que tendrá sus correspondientes asientos y reflejo en el cierre de iva.

Cuando hemos generado una factura para un moviento, cada vez que utiilicemos ese depósito para cobrar una reserva o factura se generará una línea de cargo en negativo para compensar la factura emitida por el depósito.

Al final la factura inicial quedará compensada y solo tendrán efecto las facturas emitidas por los servicios.



Incobrados
----------


Al finalizar la temporada es posible que queden reservas o facturas por pagar.

Si queremos marcar estos importes como pérdida y cuadrar la reserva deberemos asumir las pérdidas de manera manual reserva por reserva.

Podemos hacerlo generando una línea de cargo en negativo, lo que generará un abono (factura) y dejará la deuda a 0, o entrando en las mismas y generando un movimiento de caja para dar la factura por liquidada.


Cobros fraccionados
-------------------

Cada cobro que relacionamos con una reserva o factura va decrementando el saldo pendiente de esa factura o reserva.

Desde la reserva siempre podemos consultar el saldo y el extracto, y ver todos los pagos que se han ido haciendo.

Los pago pueden haberse realizado sobre la reserva (prepago), y luego se ligan a la factura.


Pagos
=====

Aquí explicaremos algunas peculiaridades relacionadas con los pagos a proveedores.


Retenciones
-----------

En QuoTravel podemos indicar que un proveedor está sujeto a retenciones de IRPF.

Si esto es así, tal circunstancia queda reflejada en la factura y se considera pagada cuando se ha satisfecho el importe sin la retención.

La retención en sí misma se va acumulando la podemos consultar en Financial --> Retentions.

Para cada retención podemos ver


Factura
  Factura objeto de la retención

Base
  Importe que se ha utilizado para el cálculo de la rentención

Porcentaje
  Porcentaje que se ha aplicado para el cálculo de la retención

Importe
  Importe retenido

Divisa
  Divisa de la retención


En cualquier momento podemos liquidar las retenciones pendientes, simplemente utilizando la opción "Liquidar" desde el mantenimiento de retenciones.

QuoTravel nos pedirá hasta que fecha de factura queremos liquidar, y generará la liquidación pertinente.

Esta acción relacionará las retenciones con su pertienente liquidación, de manera que una retención no puede figurar en dos liquidaciones al mismo tiempo.


Depósitos
---------

Los depósitos para con los proveedores son análogos a los depositos de los clientes, solo que no emitimos factura alguna.

En este caso, si así lo deseamos, podemos generar una línea de cargo para que exista una previsión que luego podamos "matar" con la pertinente factura del proveedor.

Igual que pasa con los depósitos de clientes, esa línea de cargo se irá matando con líneas de cargo que se irán generando a medida que vayamos utilizando el depósito.


Remesas (transferencias y talones)
----------------------------------

En el caso de que así lo indiquemos podemos generar desde los movimientos remesas para enviar al banco.

En la remesa incluiremos tanto transferencias como las peticiones para que el banco genere los talones oportunos.

Para ello simplemente debemos ir a la cuenta correspondiente y seleccionar la opción "Generar remesa".

Nos mostrará los movimientos de tipo transferencia y cheque que no han sido todavía incluidos en ninguna remesa, podremos seleccionar aquellos que queramos incluir en esta remesa, y la generará.

Luego podemos consultar la remesa y bajarnos el fichero correspondiente.

Si ya nos hemos bajado en algua ocasión el fichero nos avisará.

Si alguno de los movimientos ya ha sido confirmado al importar el extracto del banco, entonces no nos podremos volver a bajar el fichero.

Un movimiento solo puede estar incluido en una única remesa.

En Financials --> Payments --> Bank remittances encontraremos el listado de remesas generadas, las veces que nos las hemos descargado y la lista de movimientos incluidos.

Controlamos si los talones han sido cobrados y las transferencias realizadas al importar el extracto del banco.


VCC
---

QuoTravel utiliza Voxel para emitir tarjetas de crédito virtuales (VCC) para el pago a proveedores.

El pago con tarjeta de crédito virtual es simplemente una forma de pago más, con sus respectivos cambios de estado.

Para emitir las tarjetas de credito virtual basta ir a la cuenta correspondiente y seleccionar "Generar VCCs". En ese momento veremos una lista de los movimientos asociados con esta foma de pago que no hayan sido ejecutados y podremos generar las tarjetas de crédito virtuales.

La tarjeta de crédito llega al proveedor utilizando Voxel o a través de un email nuestro, según lo hayamos configurado.

La única manipulación que se hace de las tarjetas una vez emitidas es la de cancelarlas o modificar su valor en el caso de una modificación del importe de la reserva, normalmente por una cancelación.

El resto de manipulacines de las tarjetas en caso de ser necesario deben hacerse desde Voxel.


Carta de pagos
--------------

Para cualquier movimiento podemos generar su correspondiente carta de pagos.

Para hacerlo basta ir a la consulta de movimientos, marcar los que queramos, y utilizar a opción "Generar carta de pagos".

Nos aparecerá un pdf que incluirá todas las cartas de pagos correspondientes a los movimientos seleccionados.


***
VAT
***

El tema de los impuestos siempre ha sido un poco complejo en el caso de las agencias de viajes.

Hay que intentar ir siempre al régimen general aunque con cuidado de no pillarnos los dedos si inlcuimos servicios que luego nos puedan facturar en régimen especial, incluimos servicios con distintos tipos de iva, mezclamos servicios de varias naciones y con diferentes regímenes, ...

En este capítulo vamos a ver como configuramos y como se tratan los impuestos (IVA) en QuoTravel.

Régimen general y especial
==========================

Como hemos mencionado antes siempre intentaremos emitir nuestras facturas en el régimen general, ya que nos reulta más ventajoso.

No es lo mismo pagar el 21% sobre nuestro margen que pagar el 7%, que es lo que ocurre cuando estamos en régimen general.

También es más ventajoso para nuestros clientes, que pueden deducirse el IVA de nuestras facturas, con lo que nos equipara en competitividad con nuestros proveedores.

Entonces, aunque por defecto deberíamos emitir nuestras facturas en régimen especial, siempre que podamos nos iremos al régimen general.

Recordemos que esto es posible siempre que nuestros proveedores nos facturen en régimen general con el mismo impuesto que estamos facturando nosotros.

Si no es así podemos acabar soportando un iva que luego no podremos deducir.

El régimen que se utiliza en la factura aparece reflejado en la misma.


Reglas de localización
======================

Para saber que impouesto tenemos que aplicar en cada operación y para su correcta aplicación debemos definir la reglas de localización para cada concepto de facturación.

Las reglas de localización pueden ser

- Punto de venta
- El destinatario
- El servicio

Una vez que sabemos la regla de localización a utilizar sabreos que impuesto debemos aplicar.

Puede ser que la regla de localización nos diga que la operación está sujeta a IVA porque la sitúa en la pensínsula o Baleares, que la operación está sujeta a IGIC porque ha ubicado la operación en Canarias, o que la operación está exenta porque la ha ubicado en un país donde no tributamos o no existe IVA.


Intra comunitario
=================

Si hemos marcado el cliente o el proveedor como intracomunitario todas las operaciones realizadas con este proveedor aparecerán marcadas como tales en el cierre de IVA.



***
SII
***

Esto hay que acabar de definirlo pero, básicamente, cualquier cliente nuestro español que facture más de 6 millones de euros al año debe subir sus facturas al SII.

Básicamente hay 2 operaciones relacionadas con el SII:

- subir las facturas (las emitidas y las validadas)
- comprobar que están correctamente en al aeat





Subida de facturas al SII
=========================

Aunque podemos automatizar el envío, seguramente también soportaremos el envío manual.

Para ello el usuario nos dirá hasta que fecha quiere mandar al SII y el sistema procederá a subir las facturas.

El funcionamiento es similar al de los cierres de iva.

Las facturas se quedarán con la confirmación del SII y podremos en cualquier momento consultar cuando se enviaron y quien lo hizo.

En el caso de que queramos automatizar el envío al SII seguramente podremos decidir la frecuencia.

Para cada factura queda registrada tanto la petición que ha hecho al SII como la respuesta de la AEAT.



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


***********
Retenciones
===========

En QuoTravel podemos indicar retenciones (importe a retener sobre facturas de proveedores).

Para ello podemos definir retenciones y reglas para las mismas.

Para el tipo de retención podemos indicar:

Nombre
  Nombre del tipo de retención


Para las reglas de retenciones podemos indicar:

Nombre
  Nombre de las reglas de retenciones

Tipo
  Tipo de rentención

Porcentaje
  Porcentaje a retener sobre la factura


En la parte de informes tenemos un informe que nos dice las retenciones aplicadas sobre las facturas de proveedores.


**************
Representantes
**************

En QuoTravel para cada venta podemos asignar un representante, que es básicamente una persona que se llevará una comisión sobre esa venta.

En QuoTravel la gestión de representantes está muy evolucionada, como veremos ahora.


>>>>>> terminar este capítulo


***************
Gestión divisas
***************

En QuoTravel podemos indicar operaciones en diferentes divisas.

En cada operación aparecen 2 divisas:

- la divisa de la operación
- la divisa de la empresa / contable

En cada operación se registra la fecha y la hora de la misma, así como el ratio aplicado para el cambio entre las diferentes divisas.

Como veremos más adelante en QuoTravel por defecto recoge automáticamente cada hora los cambios del Banco Central Europeo.

Esto significa que en el caso de que ni la divisa de compra ni la divisa de venta sean el Euro, para conocer el ratio de cambio entre la moneda de compra y la moneda de venta se pasa por el Euro.

Si la moneda contable no es el Euro entonces es necsaria la contratación de un servicio profesional que provea el ratio entre las diferentes monedas.


Tanto en la reserva como en las facturas podemos ver siempre los importes en la moneda de la operación como su contravalor en la divisa contable.


Ratios de cambio
================

QuoTravel por defecto recoge automáticamente cada hora los cambios del Banco Central Europeo.

Concretamente recoge los cambios publicados en https://www.ecb.europa.eu/stats/eurofxref/eurofxref-daily.xml

Según el BCE


  The reference rates are usually updated around 16:00 CET on every working day, except on TARGET closing days.
  They are based on a regular daily concertation procedure between central banks across Europe, which normally takes place at 14:15 CET.



Naturalmente se puede desarrollar la integración con servicios profesionales como XE u Oanda, servicios que deberá contratar directamente el cliente de QuoTravel.

Desde QuoTravel desaconsejamos el uso de servicios gratuitos como Yahoo o Google.


Contabilización diferencias
===========================

En la vida de una reserva hay varios momentos en los que se utilizan los cambios entre monedas.

En la venta tenemos:

- formalización de la reserva
- emisión de factura
- cobro

Mientras que en la compra tenemos

- formalización de la reserva
- recepción de la factura del proveedor
- pago

El ratio de cambio utilizado en cada uno de los momentos puede variar, lo que puede modificar el margen que deja dicha reserva ya que no podemos variar el precio de la misma. Si hemos dado un precio debemos mantenerlo.

Para reflejar esta fluctuación en cada evento comparamos el ratio utilizado en el evento anterior, lo camparamos con el ratio actual, y generamos un asiento con la pérdida o ganancia debida a la fluctuación del cambio entre divisas.

La suma de estas compensaciones aparece en la reserva, de manera que podemos saber para cada reserva cual ha sido el margen real y cómo ha influido la funtuación del cambio en dicho margen.


************
Contabilidad
************

En QuoTravel cada empresa puede tener su contabilidad.

La asignación de nºs de cuenta contable para cada partner, cuenta de banco, etc se hace a nivel de contabilidad.

Esto quiere decir que un mismo agente puede tener diferentes nº de cuenta en la contabilidad de cada empresa, que los planes contables pueden ser diferentes o estar en diferentes monedas.

El mantenimiento de contabilidades lo encontramos en Financial --> Accounting --> Accountings

Allí podemos crear y definir nuestros planes contables.

Hay que tener en cuenta que un plan contable no se puede modificar una vez que contiene asientos.


El mantenimiento de asientos lo encontramos en Financial --> Accounting --> Entries y podemos consultar los saldos de las cuentas, los apuntes, etc.

La contabilidad que viene con QuoTravel es la básica. Hay un nº de documento no tiene registros para la contabilidad analítica más allá de la oficina y código de producto relacionados con cada apunte.

No obstante, hay que recordar lo extensible que es QuoTravel.

Si necesitamos añadir campos para la contabilidad analítica nos basta con extender la clase Apunte, añadir los campos que necesitemos, e inyectar nuestro propio generador de asientos contables que rellene esos campos.


Generación de asientos contables
================================

La generación de los asientos contables a partir de las facturas y pagos a realiza un componente de QuoTravel.

Ese componente genera unos asientos con una forma concreta, que es:

NOTA: aquí deberemos enumerar los diferentes asientos contables que generamos

- factura de venta
- factura de compra (validada)
- previsión
- pagos y cobros


No obstante, podemos personalizar la generación de los asientos contables inyectando en nuestro QuoTravel nuestro propio generador de asientos contables, que puede sobreescribir total o parcialmente la generación asientos que trae por defecto QuoTravel.

NOTA: aquí incluiremos una referencia a la interfaz que hay que implementar, la clase que utiliza QuoTravel y como inyectar nuestro generador en nuestro QuoTravel.



*********************
Mecanismos de control
*********************

Los mecanismos de control son tan importantes o más que el trabajo que nos resuelve QuoTravel.

Los mecanismos de control en QuoTravel son básicamente reactivos. Esto es, monitorizamos una serie de valores y cuando dteectamos algo que no está bien, lo reportamos a quien haga falta.

Hay que definir con David cuales deben ser los valores que debemos monitorizar.

Algunos ejemplos:

- Facturas que no se han pagado pasado el vencimiento
- Riesgo acumulado
- Reservas de las que hemos recibido facturas pero que no hemos llegado a facturar al cliente
- No hemos recibido ninguna factura por voxel desde hace varios días
- No hemos facturado nada en los últimos días
- ...
