# Web service - Doc.

El presente documento constituye la descripción técnica de la plataforma de **Web service** desarrollada para promover el acceso desde el **E-Commerce Automundial.** La documentación está orientada a integrar los procesos internos de tesorería, facturación, despacho; a través del aplicativo interno de **Pedidos** para proveer una trazabilidad de una compra generada a través de la plataforma E-Commerce Automundial.

# Recurso URL
### http://mail.automundial.com.co:89/desarrollos/reporteweb/WebServices/wsMarketPlace.php

El Web service cuenta con 2 funciones que se tienen que ejecutar en un orden consecuente que a continuación se especifica.

* Función 1, ***ValCliente***: *La siguiente función recibe los parámetros del cliente en un array, y verifica la existencia del mismo. Al momento de realizar la verificación si el cliente existe se realiza un proceso de validación y actualización al momento de encontrar alguna información nueva, si no, entonces se procede a realizar la creación de cliente con respecto a los parámetros recibidos.*

> ###  La estructura de la función es la siguiente:
  >>|Campo|Tipo|NULL|Descripción|
  |---|---|:---:|---|
  |key|string|NO|Llave acceso|
  |clicod|char (11)|NO|Nit Cliente|
  |clinom|char (50)|NO|Nombre|
  |clidir|char (50)|NO|Dirección|
  |client|char (50)|NO|Dir. Envió|
  |clitel|char (15)|NO|Teléfono|
  |clipob|char (5 )|NO|Población|
  |climcu|Smallint (2 )|SI|Mes Cumpleaños|
  |clidcu|Smallint (2 )|SI|Día Cumpleaños|
  |clines|char (30)|NO|Contacto|
  |cliobs|char (70)|SI|Observación|
  |clifax|char (15)|SI|Fax|
  |clicel|char (15)|SI|Celular|
  |clireg|char (1 )|NO|Tipo de Cliente(Persona Natural 1,Empresa 2)|
  |clitpr|char (30)|SI|Alias|
  |clirgn|char (3 )|NO|Regional|
  |clieml|char (50)|NO|Correo|

    > El valor de respuesta es un array que contiene el mensaje de respuesta "msn". Los valores de respuesta son los siguientes:
    > * **OK**: *Sucede cuando la transacción ha sido existosa.*
    > * **ERROR**: *Sucede cuando se presenta un error al realizar la transacción y tiene las siguientes varintes.*
    >     * No se puede grabar el cliente
    >     * No se puede actualizar el cliente
    >     * Token no valido

* Función 2, ***GenPedido***: *La función se debe ejecutar luego de haber recibido como respuesta de la función **ValCliente** si y solo si la respuesta de esa función es **"OK"**.*
*La función GenPedido tiene como finalidad recibir información concerniente con el pedido es decir se debe pasar mediante un array la información del encabezado y detalle del pedido.*

> ###  La estructura de la funcion es la siguiente:
>>|Campo|Tipo|NULL|Descripción|
|---|---|:---:|---|
|key|string|NO|Llave acceso|
|cotcli|char(11)|NO|Nit Cliente|
|cottip|char(2 )|NO|Forma de pago|
|cotpln|char(2 )|NO|Plazo|
|cotcan|Decimal(16,2)|NO|Cantidad Total|
|cotdes|Decimal(16,2)|NO|Total Descuento|
|cotiva|Decimal(16,2)|NO|Total IVA|
|cottot|Decimal(16,2)|NO|Total Compra|
|cotobs|varchar(100)|SI|Observación|
|cotent|char(30)|SI|Forma de entrega|
|cotsuc|char(2 )|SI|Sucursal Cliente|
|cotorc|char(20)|SI|Orden compra|
|cotweb|int|NO|Código Pedido MarketPlace|
|cotidtran| char(40)|NO|# Transacción|
|cotdet|
>>>  El detalle debe ser un array el cual debe ir incluido dentro

>>>  |Campo|Tipo|NULL|Descripción|
|---|---|:---:|---|
|dettiq  |int           |SI|# Tiquete|
|detart  |char      (12)|NO|Código Articulo|
|detcan  |Decimal (16,2)|NO|Cantidad del ítem|
|detcre  |Decimal (16,2)|NO|Precio Base Ítem|
|detiva  |Decimal (16,2)|NO|Valor IVA Ítem|
|detdes  |Decimal (16,2)|NO|Valor DCTO base Ítem|
|dettot  |Decimal (16,2)|NO|Valor Total Ítem|
|detpiva |Decimal  (5,2)|NO|Porcentaje IVA|
|detpdes |Decimal  (5,2)|NO|Porcentaje Descuento|
|detcon  |char       (3)|NO|Concepto (112 - Compra Mercancía)|
|detpma  |Decimal  (5,2)|NO|Porcentaje DTCO Adicional|

>El valor de respuesta es un array que contiene el mensaje de respuesta "msn". Los valores de respuesta son los siguientes
> * **Numero de pedido**: *Sucede cuando la transacción ha sido existosa y genera el numero de pedido interno.*
> * **ERROR**: *Sucede cuando se presenta un error al realizar la transacción y tiene las siguientes varintes.*
>     * Errror al insertar el encabezado del pedido
>     * Error al insertar el detalle del pedido
>     * Token no valido
