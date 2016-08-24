

Diccionario de datos de las tablas relacionadas en el reporte desapachos logisticas.

Tabla: deslfac

Descripcion: Tabla que permite llevar los registro sobre el despacho de facturas y otros documentos a fines.

Estructura de datos:

|Column Name|Type|Size|Scale|Nullable|Descripción|
|:-----:|:-----:|:-----:|:-----:|:-----:|-----|
|desltip|char|2||YES|Tipo despacho FA=Factura, CM=CartaMala, TR=Traslado, TC=TrasladoCascos SREE, OT=Otros, NC=NC|
|deslcod|char|11||NO|Nit del cliente|
|deslubi|char|3||NO|Ubicación (Locslizacion)|
|deslnum|int|4|2|NO|Numero del documento, esta ligado al tipo de despacho|
|deslfec|date|4||NO|Fecha Ingreso|
|deslhfa|char|5||NO|Hora Ingreso|
|deslfre|date|4||NO|Fecha de registro|
|deslhre|char|5||NO|Hora Registro|
|desldig|char|8||NO|Usuario que digita|
|deslres|char|8||NO|Responsable Conductor o Vendedor|
|deslcon|int|4|2|NO|Concecutivo Despacho|
|deslcre|int|4|2|YES|Consecutivo recepción cartera|
|deslobs|char|300||YES|Observacion Despacho|
|deslfde|date|4||YES|Fecha Despacho|
|deslhde|char|5||YES|Hora Despacho|
|deslflg|date|4||YES|Fecha recepción logística|
|deslhlg|char|5||YES|hora recepción logística|
|deslrec|char|8||YES|Usuario que recepciona|
|deslpla|char|7||YES|Placa|
|deslkil|int|4|2|YES|Kilometraje|
|deslcau|char|2||YES|Causa rechazo del despacho|
|deslpsr|decimal|16|2|YES|Pesaje Real|
|deslpsu|decimal|16|2|YES|Pesaje Usuario|
|deslnit|char|11||YES|Nit de la trasnportadora|
|desltde|char|1||YES|tipo despacho flete o propio|
|desltve|char|3||YES|Categoria de vehiculo|
|deslpob|char|5||YES|Codigo de la ciudad/poblacion destino|
|deslguia|char|20||YES|Codigo de guia, si quien transporta es automundial entonces el valor ingresado es 0|
|deslvfle|decimal|14|2|YES|Valor Flete|

Tabla: facli

Descripcion: Maestro de clientes

Estructura de datos:

|Column Name|Type|Size|Scale|Nullable|Descripción|
|:-----:|:-----:|:-----:|:-----:|:-----:|-----|
|clicod|char|11||YES|Nit del cliente|
|clidig|char|1||YES|Digito de verificacion|
|clicar|char|5||YES|Codigo de Carné|
|clinom|char|50||YES|Nombre del cliente|
|clidir|char|50||YES|Direccion Del cliente|
|client|char|50||YES|Direccion de envio|
|cliocu|char|2||YES|Ocupacion del cliente|
|clitel|char|15||YES|Telefono Cliente|
|clipob|char|5||YES|Codigo de la poblacion|
|cliven|char|4||YES|Codigo del vendedor|
|clifin|date|4||YES|Fecha de creacion del cliente|
|climcu|smallint|2|2|YES|Mes cumpleaños|
|clidcu|smallint|2|2|YES|Dia Cumpleaños|
|clines|char|30||YES|Contacto|
|cliemc|smallint|2|2|YES||
|cliedc|smallint|2|2|YES||
|clitip|char|2||YES|Tipo de cliente|
|clicla|char|1||YES||
|cliesp|char|1||YES|Imprime remision ("R")|
|cliemp|char|11||YES|Codigo de la empresa a la que pertenece|
|clirep|smallint|2|2|YES||
|cliobs|char|70||YES|Ultima Observacion|
|cliact|char|1||YES|Estado en cartera del Cliente|
|cliflg|char|1||YES|( C = al facturar agrupa por codigo de articulo )|
|cliusu|char|10||YES|Usuario que crea al cliente|
|cligru|char|3||YES|Segmento|
|clisub|char|3||YES|Subsegmento|
|clite2|char|15||YES|Numero de Telefono 2 |
|clifax|char|15||YES|Numero de fax|
|clicel|char|15||YES|Numero de celular|
|clireg|char|1||YES|Tipo de regimen del cliente|
|clitpr|char|30||YES||
|clifve|date|4||YES||
|clivve|decimal|14|2|YES||
|clifpg|date|4||YES|Fecha ultimo pago|
|clivpg|decimal|14|2|YES|Valor del ultimo pago|
|clifbl|date|4||YES||
|clifmd|date|4||YES||
|clisuc|char|1||YES|Cliente maneja sucursal (S = "SI" / N = "No")|
|clicon|char|4||YES|Codigo del conductor|
|clipro|char|4||YES|Codigo del Segmento|
|clivis|decimal|5|3|YES||
|clirec|decimal|5|3|YES||
|clipll|int|4|2|YES|Potencial de Llanta Nueva|
|clipre|int|4|2|YES|Potencial de Reencauche|
|clifcv|date|4||YES||
|clizon|char|3||YES|Codigo de la zona del cliente|
|clirgn|char|3||YES|Codigo de la regional del cliente|
|clieml|char|50||YES|E-Mail del cliente|
|clirut|char|4||YES|Ruta del cliente|
|cliszo|char|3||YES|Subzona del cliente|

Tabla: faven

Descripcion: Tabla maestra de vendedores/conductores

Estrucutra de datos:

|Column Name|Type|Size|Scale|Nullable|Descripción|
|:-----:|:-----:|:-----:|:-----:|:-----:|-----|
|vencod|char|4||YES|Codigo del vendedor|
|vennom|char|30||YES|Nombre  del vendedor|
|venced|char|11||YES|Cedula de ciudadania|
|vendir|char|30||YES|Direccion |
|ventel|char|30||YES|Telefono|
|venzon|char|3||YES|Zona que le Corresposnde|
|vencat|char|2||YES|Categoria del vendedor|
|vening|date|4||YES|Fecha de ingreso|
|venegr|date|4||YES|Fecha de  retiro|
|vencno|char|8||YES||
|ventip|char|1||YES|Tipo|
|venubi|char|3||YES|Codigo de la Localizacion|

Tabla: cppro

Descripcion: Tabla maestra de proveedores de la compañia

|Column Name|Type|Size|Scale|Nullable|Descripción|
|:-----:|:-----:|:-----:|:-----:|:-----:|-----|
|procod|char|11||YES|Codigo Interno automundial|
|pronom|char|50||YES|Nombre de la Empresa|
|prodir|char|30||YES|Direccion|
|prociu|char|5||YES|Codigo de la ciudad|
|protel|char|30||YES|Telefono Priveedor|
|pronit|char|11||YES|Numero decedula /nit Cliente|
|procon|char|30||YES|Contacto|
|propla|int|4|2|YES|Plazo en dias|
|proret|char|1||YES|Si es auto retenedor  (S/N)|
|protip|char|1||YES|Tipo de proveedor  (1 = Nacional  / 2 = Extranjero)|
|proiva|char|1||YES|Tipo de regimen de iva|
|profec|date|4||YES|Fecha de creacion del proveedor|
|prousu|char|10||YES|Usuario Quien lo creo|
|procue|char|10||YES|Cuenta|
|proica|char|5||YES|Actividad economica|
|prodig|char|1||YES|Digito de verificacion|
|profax|char|15||YES|Numero de fax|
|protdo|char|1||YES||
|proica2|char|5||YES||
|protar|decimal|6|3|YES||
|protcu|char|1||YES||
|procta|char|15||YES||
|procic|char|4||YES||
|proban|char|3||YES||
|proeml|char|50||YES|Email Proveedor|

Tabla: vepob

Descripcion: Tabla parametrica con las poblaciones/ciudades segun el dane

|Column|Type|Size|Scale|Nullable|Descripción|
|:-----:|:-----:|:-----:|:-----:|:-----:|-----|
|pobcod|char|5||YES|Codigo poblacion|
|pobnom|char|30||YES|Nombre poblacion|
|pobzon|char|3||YES|Zona|
|pobdep|char|2||YES|Departamento|
|pobpai|char|3||YES|Pais|
|pobcbb|char|4||YES|--|

Tabla: vetve

Descripcion: Tabla que almacena el codigo y descripcion de las categorias de los vehiculos

|Column Name|Type|Size|Scale|Nullable|Descripción|
|:-----:|:-----:|:-----:|:-----:|:-----:|-----|
|tvecod|char|3||YES|Codigo|
|tvenom|char|30||YES|Descripción de la categoria del vehiculo|

Tabla: siubi

Descripcion: Tabla maestra de ubicaciones/localizaciones de la compañia

|Column Name|Type|Size|Scale|Nullable|Descripción|
|:-----:|:-----:|:-----:|:-----:|:-----:|-----|
|ubicod|char|3||NO|Codigo|
|ubinom|char|40||NO|Nombre de ubicación|
|ubidir|char|50||NO|Direccion|
|ubiciu|char|5||NO|Codigo de la ciudad o poblacion|
|ubitel|char|50||NO|Telefono|
|ubitip|char|1||YES|Tipo B=Bodega, P=Planta|
|ubireg|char|3||YES|Codigo de la regional|
|ubipla|char|3||YES|Codigo de la planta asociada|
|ubialm|char|2||YES|Definir si la ubicación es alamacen o no|

Tabla: caulog

Descripcion: Tabla que contiene el codigo y descripcion de las causas de rechazo de un despacho

|Column Name|Type|Size|Scale|Nullable|Descripción|
|:-----:|:-----:|:-----:|:-----:|:-----:|-----|
|logcod|char|2||NO|Codigo|
|lognom|char|50||NO|Descripción de la causa de no entrega del despacho|

Tabla: fasem

Descripcion: Tabla parametrica que contiene el codigo y descripcion de los segmentos operacionales de Automundial

|Column Name|Type|Size|Scale|Nullable|Descripción|
|:-----:|:-----:|:-----:|:-----:|:-----:|-----|
|semcod|char|4||NO|Codigo|
|semnom|char|30||NO|Nombre segmento|

# Queries

Query general que optiene todos los datos
```sql
SELECT deslfac.desltip, deslfac.deslcod, deslfac.deslubi, deslfac.deslnum,
deslfac.deslfec, deslfac.deslcon, deslfac.deslpla, deslfac.deslnit,
deslfac.deslres, deslfac.deslcre, deslfac.deslrec, deslfac.desltve,
deslfac.deslpob, deslfac.desltde, deslfac.deslfre, deslfac.deslflg,
deslfac.deslcau, siubi.ubinom,    facli.clinom,    faven.vennom,
cppro.pronom,    vepob.pobnom,    vetve.tvenom,    deslfac.deslpsu,
deslfac.deslvfle,caulog.lognom,   deslfac.deslpsr, facli.clipro,
fasem.semnom
FROM deslfac, facli, faven,OUTER(cppro), vepob, vetve, siubi, OUTER(caulog),OUTER(fasem)
WHERE deslfre >= \"",fechai,"\"
AND deslfre <= \"",fechaf,"\"
AND deslcod = clicod
AND deslres = vencod
AND deslnit = procod
AND deslpob = pobcod
AND desltve = tvecod
AND deslubi = ubicod
AND deslcau = logcod
AND clipro = semcod
ORDER BY 3,6,15,16,1,4,2,5
```

De acuerdo al tipo de despacho se ejecutan los siguientes querys que tienen como finalidad llenar una tabla temporal con la siguiente estructura:

```sql
CREATE TEMP TABLE categ(
    despacho   INTEGER,
    documento  INTEGER,
    catcod  CHAR(10),
    cuantos  INTEGER,
    peso   DECIMAL(12,2)
   )WITH NO LOG
CREATE UNIQUE INDEX icateg ON categ(despacho,documento,catcod);
/*
Donde:
 - despacho = # despacho de la tabla deslfac campo deslnum
 - documeto = # de documento de la tabla deslfac compo deslcod
 - catcod = codigo de la categoria del despacho es decir si el despacho es SREE, CRAM, NAL entre otros
 - cuantos = es la cantidad a despachar
 - peso = peso que tiene la mercancia a despachar
*/
```

Los siguientes queries que se generan a partir del tipo, tienen como estructura en el SELECT de pasar como referencia y en el mismo orden la informacion de Nit Cliente, Nombre Cliente, Codigo Regional, Nombre regional, Codigo Categoria, Peso del articulo, Cantidad del articulo.

```sql
/*
Cuando el tipo es FA (Factura)
se reciben los parametros de la consulta anterior los cuales son:
p_deslfac.deslnum es el numero de documento
p_deslfac.deslfec es la fecha de despacho
p_deslfac.deslubi es la ubicacion de despacho
*/
SELECT movcli,clinom,clirgn,regnom,artcat,artcom,SUM(movdetcan)
FROM famovdet,famov,ivart,facli,fareg
WHERE movdetdoc = movdoc
AND movdetano = movano
AND movdetmes = movmes
AND movdetfue = movfue
AND movdetart = artcod
AND movdetdoc = p_deslfac.deslnum
AND movfec = p_deslfac.deslfec
AND movdetfue = p_deslfac.deslubi
AND movcli = clicod
AND clirgn = regcod
GROUP BY 1,2,3,4,5,6
```

```sql
/*
Cuando el tipo es CM (Carta Mala)
se reciben los parametros de la consulta anterior los cuales son:
p_deslfac.deslnum es el numero de documento
*/
SELECT tiqcli,clinom,zonreg,regnom,tiqdis,artcom,COUNT(*)
FROM cardetmal,cstiq,ivart,facli,vezon,fareg
WHERE maldetdoc = p_deslfac.deslnum
AND maldettiq = tiqnum
AND maldetubi = tiqpla
AND tiqart = artcod
AND tiqcli = clicod
AND zoncod = tiqzon
AND zonreg = regcod
GROUP BY 1,2,3,4,5,6
```

```sql
/*
Cuando el tipo es TR (Traslado)
se reciben los parametros de la consulta anterior los cuales son:
p_deslfac.deslnum es el numero de documento
p_deslfac.deslfec es la fecha de despacho
p_deslfac.deslubi es la ubicacion de despacho
*/
SELECT "860001615","AUTOMUNDIAL S.A.", ubireg,regnom, ivart.artcat,
ivart.artcom, SUM(ivmovdet.movdetcan)
FROM ivmov, ivmovdet, ivart, siubi, fareg
WHERE ivmov.movser = p_deslfac.deslubi
AND ivmovdet.movdetdoc = p_deslfac.deslnum
AND ivmov.movfec = p_deslfac.deslfec
AND ivmov.movfue = ivmovdet.movdetfue
AND ivmov.movdoc = ivmovdet.movdetdoc
AND ivmov.movano = ivmovdet.movdetano
AND ivmov.movmes = ivmovdet.movdetmes
AND ivmov.movser = ivmovdet.movdetubi
AND ivmovdet.movdetfue = "12"
AND ivmovdet.movdetcon = "105"
AND ivmovdet.movdetart = artcod
AND ivmov.movse1 = siubi.ubicod
AND siubi.ubireg = fareg.regcod
GROUP BY 1,2,3,4,5,6
```

```sql
/*
Cuando el tipo es TC (Traslado Cascos SREE)
se reciben los parametros de la consulta anterior los cuales son:
p_deslfac.deslnum es el numero de documento
p_deslfac.deslfec es la fecha de despacho
p_deslfac.deslubi es la ubicacion de despacho
*/
SELECT "860001615","AUTOMUNDIAL S.A.",ubireg,regnom,artcat,artcom,SUM(movdetcan)
FROM prmovdet,ivart,siubi,fareg
WHERE movdetubi = p_deslfac.deslubi
AND movdetdoc = p_deslfac.deslnum
AND movdetano = YEAR(p_deslfac.deslfec)
AND movdetmes = MONTH(p_deslfac.deslfec)
AND movdetfue = "12"
AND movdetcon = "105"
AND movdetart = artcod
AND movdetude = ubicod
AND ubireg = regcod
GROUP BY 1,2,3,4,5,6
```

Con base a esa informacion se hacen los respecctivos insert o update a la tabla temporal.
las regalas para insertar o actualiar son las siguientes.

```sql
/*A continuacion se relacionan las siguientes variables pes_art y cant_art que son el peso delarticulo y la cantidad del articulo respectivamente*/
IF pes_art > 0 THEN
  LET pes_art = pes_art * cant_art
ELSE
  LET pes_art = cant_art
END IF

/*Se ejecuta la consulta a la tabla temporal con las condiciones de los resultados de las anteriores consultas de los diferentes tipos.
categoria = categoria del articulo, es decir si es NAL, SREE, PRO, NOTR entre otras categorias
documento = proviene de la tabla deslfac, campo deslnum y es el numero del tipo de documento
despacho = proviene de la tabla deslfac, campo deslcon y es el consecutivo del despacho
*/
SELECT COUNT(*)
FROM categ a
WHERE a.catcod = categoria
AND a.documento = p_deslfac.deslnum
AND a.despacho = p_deslfac.deslcon
```
De acuerdo al resultado anterior, si no existen registros entonces se ejecuta el query a continuacion que tiene como finalidad realizar la insercion a la tabla temporal los datos de consecutivo de despacho, numero de documento, categoria, cantidad , peso.
```sql
INSERT INTO categ VALUES(p_deslfac.deslcon,p_deslfac.deslnum, categoria,cant_art,pes_art)
```
Si SI existe el registro, entonces se hace una actualizacion el registro.
```sql
/*Se realiza la consulta a la taba temporal para optener los registros de cantidad y peso para hacer la actualizacion de los mismos. La consulta se realiza con las condicionales de:
categoria = categoria del articulo, es decir si es NAL, SREE, PRO, NOTR entre otras categorias
documento = proviene de la tabla deslfac, campo deslnum y es el numero del tipo de documento
despacho = proviene de la tabla deslfac, campo deslcon y es el consecutivo del despacho  */
SELECT a.cuantos INTO cant_art2
FROM categ a
WHERE a.catcod = categoria
AND a.documento = p_deslfac.deslnum
AND a.despacho = p_deslfac.deslcon

/*Se actualiza los campos "cuantos" y "peso" sumandoles la nueva cantidad a la cantidad ya existente. La consulta se realiza con las condicionales de:
categoria = categoria del articulo, es decir si es NAL, SREE, PRO, NOTR entre otras categorias
documento = proviene de la tabla deslfac, campo deslnum y es el numero del tipo de documento
despacho = proviene de la tabla deslfac, campo deslcon y es el consecutivo del despacho  */
LET cant_art2 = cant_art2 + cant_art
UPDATE categ SET categ.cuantos = cuantos + cant_art2,
categ.peso = peso + pes_art
WHERE categ.catcod = categoria
AND categ.documento = p_deslfac.deslnum
AND categ.despacho = p_deslfac.deslcon
```
# Estructura reporte

A continuacion se describen las columnas generadoras del reporte

|Tabla|Campos reporte|Descripcion|
|----|----|----|
|deslfac|deslfre|FECHA|
|deslfac|deslcon|NUMERO DESPACHO|
|deslfac|desltip|TIPO DESPACHO|
|deslfac|deslnum|NUMERO DOCUMENTO|
|deslfac|deslfec|FECHA DOCUMENTO|
|deslfac|deslcod|CLIENTE|
|facli|clinom|NOMBRE CLIENTE|
|facli|clipro|COD. SEGMENTO (SEM)|
|fasem|semnom|NOMBRE SEGMENTO (SEM)|
|fareg|regional|COD. REGIONAL GENERADORA DE FLETE|
|fareg|nregional|NOMBRE REGIONAL GENERADORA DE FLETE|
|deslfac|deslpla|PLACA|
|deslfac|deslnit|NIT TRANSPORTADOR|
|cppro|pronom|NOMBRE TRANSPORTADOR|
|deslfac|desltve|COD. TIPO VEHICULO|
|vetve|tvenom|NOMBRE TIPO VEHICULO|
|deslfac|deslubi|UBICACION|
|siubi|ubinom|NOMBRE UBICACION|
|fareg|r_despacho|REGIONAL DESPACHO|
|fareg|nr_despacho|NOMBRE REGIONAL DESPCAHO|
|deslfac|deslpob|DESTINO|
|vepob|pobnom|NOMBRE DESTINO|
|deslfac|tdenom|CLASE DESPACHO esta ligado con el campo desltde|
|deslfac|deslcau|CAUSA|
|caulog|lognom|NOMBRE CAUSA|
|CALCULADO|c_reen|CANT. REENCAUCHE|
|CALCULADO|p_sree|PESO REENCAUCHE|
|CALCULADO|c_sotr|CANT. SERV OTR|
|CALCULADO|p_sotr|PESO SERV OTR|
|CALCULADO|c_notr|CANT. NUEVA OTR|
|CALCULADO|p_notr|PESO NUEVA OTR|
|CALCULADO|c_potr|CANT. CRAM OTR|
|CALCULADO|p_potr|PESO CRAM OTR|
|CALCULADO|c_pree|CANT. CRAM CAMION|
|CALCULADO|p_pree|PESO CRAM CAMION|
|CALCULADO|c_nal|CANT. LLANTA NACIONAL|
|CALCULADO|p_nal|PESO LANTA NACIONAL|
|CALCULADO|c_imp|CANT. LLANTA IMPORTADA|
|CALCULADO|p_imp|PESO LLANTA IMPORTADA|
|CALCULADO|c_acc|CANT. ACCESORIOS|
|CALCULADO|p_acc|PESO ACCESORIOS|
|CALCULADO|c_maree|CANT. MAREE|
|CALCULADO|p_maree|PESO MAREE|
|CALCULADO|c_mpa|CANT. MPA|
|CALCULADO|p_mpa|PESO MPA|
|CALCULADO|c_rech|CANT. RECHAZOS|
|CALCULADO|p_rech|PESO RECHAZOS|
|CALCULADO|c_ajus|CANT. AJUSTES|
|CALCULADO|p_ajus|PESO AJUSTES|
|CALCULADO|c_dfin|CANT. DISPO. FINAL|
|CALCULADO|p_dfin|PESO DISPO. FINAL|
|CALCULADO|c_resi|CANT. RESIDUOS|
|CALCULADO|p_resi|PESO RESIDUOS|
|CALCULADO|c_otro|CANT. VARIOS|
|CALCULADO|p_otro|PESO VARIOS|
|CALCULADO|uni_tot|CANTIDADES TOTAL|
|CALCULADO|pes_tot|PESO TOTAL|
|deslfac|deslpsu|PESO SUGERIDO|
|deslfac|deslvfle|VALOR FLETE|

Las variables a continuacion se inicializan en 0

c_reen, p_sree, c_sotr, p_sotr, c_notr, p_notr, c_potr, p_potr, c_pree, p_pree, c_nal, p_nal, c_imp, p_imp, c_acc, p_acc, c_maree, p_maree, c_mpa, p_mpa, c_rech, p_rech, c_ajus, p_ajus, c_dfin, p_dfin, c_resi, p_resi, c_otro, p_otro, pes_uni = 0

Y en relacion a la categoria del tipo de despacho se realiza la sumatoria

Primero se realiza la consulta a la tabla temporal con las condiciones de deslnum (Numero de documento) y deslcon (Consecutivo de despacho).
```sql
SELECT a.catcod, a.cuantos, a.peso
 FROM categ a
WHERE a.documento = deslnum
  AND a.despacho = deslcon
```
De acuerdo al resultado optenido se realiza la sumatoria para cada una de las variables de acuerdo a la categoria de cada uno de los registros almacenados en la tabla resumen
```sql
CASE cat

  WHEN "SREE"
      c_reen = c_reen + cant
      p_sree = p_sree + pes_uni

  WHEN "SOTR"
      c_sotr = c_sotr + cant
      p_sotr = p_sotr + pes_uni

  WHEN "NOTR"
      c_notr = c_notr + cant
      p_notr = p_notr + pes_uni

  WHEN "POTR"
      c_potr = c_potr + cant
      p_potr = p_potr + pes_uni

  WHEN "PREE"
      c_pree = c_pree + cant
      p_pree = p_pree + pes_uni

  WHEN "NAL"
      c_nal = c_nal + cant
      p_nal = p_nal + pes_uni

  WHEN "IMP"
      c_imp = c_imp + cant
      p_imp = p_imp + pes_uni

  WHEN "ACC"
      c_acc = c_acc + cant
      p_acc = p_acc + pes_uni

  WHEN "MAREE"
      c_maree = c_maree + cant
      p_maree = p_maree + pes_uni

  WHEN "MPA"
      c_mpa = c_mpa + cant
      p_mpa = p_mpa + pes_uni

  WHEN "RECHA"
      c_rech = c_rech + cant
      p_rech = p_rech + pes_uni

  WHEN "AJUSTE"
      c_ajus = c_ajus + cant
      p_ajus = p_ajus + pes_uni

  WHEN "DESP"
      c_resi = c_resi + cant
      p_resi = p_resi + pes_uni

  OTHERWISE
      c_otro = c_otro + cant
      p_otro = p_otro + pes_uni
END CASE
```
