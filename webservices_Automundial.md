# Web service - Doc.

El presente documento constituye la descripción técnica de la plataforma de **Web service** desarrollada para promover el acceso desde el **E-Commerce Automundial.** La documentación está orientada a integrar los procesos internos de tesorería, facturación, despacho; a través del aplicativo interno de **Pedidos** para proveer una trazabilidad de una compra generada a través de la plataforma E-Commerce Automundial.

## Recurso URL
#### http://mail.automundial.com.co:89/desarrollos/reporteweb/WebServices/wsMarketPlace.php

## Información sobre el recurso

El Web service da acceso a al fichero WSDL, a la página de ***WS Market Place Automundial S.A.***.
>El fichero WSDL (SOAP API Descriptor Lenguaje) es un fichero XML que indica principalmente, qué formato utilizar en la conformación de una petición al servicio y el significado de la petición.

El Web service cuenta con 2 funciones que se tienen que ejecutar en un orden consecuente que a continuación se especifica.

* Función 1, ***ValCliente***: *La siguiente función recibe los parámetros del cliente en un array, y verifica la existencia del mismo. Al momento de realizar la verificación si el cliente existe se realiza un proceso de validación y actualización al momento de encontrar alguna información nueva, si no, entonces se procede a realizar la creación de cliente con respecto a los parámetros recibidos.*

###  La estructura de la función es la siguiente:

|Campo|Tipo|NULL|Descripción|
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

###  La estructura de la funcion es la siguiente:
|Campo|Tipo|NULL|Descripción|
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
|cotdet|array|NO|Anexo informacion del array del detalle del pedido en la siguiente tabla|

>El detalle debe ser un array el cual debe ir incluido dentro


|Campo|Tipo|NULL|Descripción|
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

### Ejemplo desarrollado en **PHP**
<pre><code>
require_once('../lib/common/nusoap-0.9.5/lib/nusoap.php');
header('Content-Type: text/html; charset=ISO-8859-1');
$cliente = new nusoap_client('http://ctw.automundial.com.co/desarrollos/reporteweb/WebServices/wsMarketPlace.php');
$sandkey = crypt('Crypt*Auto.99858Key'.date("Ymd"), '$1$cK8pdNwY1$') . "\n";
$clientes[0] = array('clicod' => "1087997536", 'clinom' => "alexander", 'clidir' => "AV Simpreviva 123", 'client' => "AV Falsa 123", 'clipob' => "11001", 'clitel' => "4641544", 'climcu' => "", 'clidcu' => "", 'clines' => "alexander", 'cliobs' => "Cliente WEBSERVICE Pagina Automundial", 'clifax' => "", 'clicel' => "", 'clireg' => "1", 'clitpr' => "", 'clirgn' => "001", 'clieml' => "info@automundial.co");
print_r($clientes);
$cantidad[0] = array("dettiq"=>"", "detart"=>"2368", "detcan"=>"1", "detcre"=>"930172.4137931", "detiva"=>"172640", "detdes"=>"0", "dettot"=>"1102812.4137931", "detpiva"=>"1.16", "detpdes"=>"0", "detcon"=>"112", "detpma"=>"0");
$cantidad[1] = array("dettiq"=>"", "detart"=>"2931", "detcan"=>"5", "detcre"=>"1339336", "detiva"=>"969679", "detdes"=>"127237", "dettot"=>"7030175", "detpiva"=>"16", "detpdes"=>"9.50", "detcon"=>"112", "detpma"=>"0");
$detalle_productos = array();
foreach ($cantidad as $c) {
	$detalle=array('dettiq' =>$c['dettiq'], 'detart' =>$c['detart'], 'detcan' =>$c['detcan'], 'detcre' =>number_format($c['detcre'],2, '.', ''), 'detiva' =>number_format($c['detiva'],2, '.', ''), 'detdes' =>number_format($c['detdes'],2, '.', ''), 'dettot' =>number_format($c['dettot'],2, '.', ''), 'detpiva' =>$c['detpiva'], 'detpdes' =>$c['detpdes'], 'detcon' =>"112", 'detpma' =>"0");
	array_push($detalle_productos, $detalle);

}
$id_pedido='161'; #Pedido de plataforma marketplace
$transaccion='013779608';
$INCliente = array( "INCliente" =>
	array('key' => $sandkey, 'clicod' => $clientes[0]['clicod'], 'clinom' => $clientes[0]['clinom'], 'clidir' => $clientes[0]['clidir'], 'client' => $clientes[0]['client'], 'clipob' => $clientes[0]['clipob'], 'clitel' => $clientes[0]['clitel'], 'climcu' => $clientes[0]['climcu'], 'clidcu' => $clientes[0]['clidcu'], 'clines' => $clientes[0]['clines'], 'cliobs' => $clientes[0]['cliobs'], 'clifax' => $clientes[0]['clifax'], 'clicel' => $clientes[0]['clicel'], 'clireg' => $clientes[0]['clireg'], 'clitpr' => $clientes[0]['clitpr'], 'clirgn' => $clientes[0]['clirgn'], 'clieml' => $clientes[0]['clieml'])
);
/****Envia web service para la del cliente en automundial*/
$resultado = $cliente->call('ValCliente',$INCliente);
print_r($resultado);
if($resultado['msn']=="OK"){
	$INPedido = array( "INPedido" =>
		array(
			'key' => $sandkey,          #Llave acceso
			'cotcli' => $clientes[0]['clicod'],                              #Nit Cliente
			'cottip' => "01",                                               #Forma de pago
			'cotpln' => "01",                                              #Plazo
			'cotcan' => "1",                                            #Cantidad Total
			'cotdes' => number_format(0,2, '.', ''),                                     #Total Descuento
			'cotiva' => number_format(96275.862068966,2, '.', ''),                                      #Total Iva
			'cottot' => number_format(698000,2, '.', ''),      #Total de la compra
			'cotobs' =>"Pedido de prueba", #Observación
			'cotent' =>"Inmediato", #Forma de entrega
			'cotsuc' =>"01", #Sucursal Cliente
			'cotorc' => "",   #Orden de compra
			'cotweb' =>$id_pedido, #Código Pedido MarketPlace
			'cotidtran' =>$transaccion, #Código Seguimiento PSE
			//'cotdet' =>$detalle_productos
			'cotdet' => $detalle_productos
		)
	);
	/****Envia web service para la creacion del pedido*/
	$resultado2 = $cliente->call('GenPedido',$INPedido);
}
print_r($resultado2);
</code></pre>
