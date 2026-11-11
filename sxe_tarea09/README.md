# Tarea 09 · Implantación de Odoo

### <ins>Adrián Sande Domínguez</ins>

### 1º EJERCICIO - BASES DE DATOS: Captura del gestor con demo y primo, e idioma y país con que se crearon.

Después de hacer el despliegue correspondiente y completar todas las operaciones en Docker Compose, se accederá al servicio Odoo a través de la url: http://localhost:8069  

Una vez hecho esto se verá la siguiente pantalla:

![1](/CAPTURAS%20SXE/Captura%20desde%202026-11-09%2009-32-04.png)

Aquí se establecerán todos los datos para crear o restaurar una base de datos. En este caso habrá que crear una nueva, para ello se rellenará cada campo con su información correspondiente. Esta primera base de datos se creará añadiendo la opción demo, que hará que se cuente con ciertas funcionalidades base preinstaladas con datos de demostración, que servirán para explorar y hacer operaciones sin afectar a la base de datos real.

Después de esperar unos minutos ya estará listo el servicio y se verá la pantalla inicial.

![2](/CAPTURAS%20SXE/Captura%20desde%202026-11-09%2009-33-49.png)

Para acceder al gestor de bases de datos y poder crear una nueva se entrará en la url que se ve arriba en el buscador. Es la misma con la que se entra al servicio añadiendo /web/database/manager (en la imagen se ve ya creada la otra base de datos, en la siguiente parte de mostrará y explicará el como se hizo).

![3](/CAPTURAS%20SXE/Captura%20desde%202026-11-09%2013-56-13.png)

Se hace clic en "Create database" y se rellenarán los mismos campos que la primera vez

![4](/CAPTURAS%20SXE/Captura%20desde%202026-11-09%2013-53-47.png)

Después de unos minutos ya estará creada la base de datos y el servicio estará operativo

![5](/CAPTURAS%20SXE/Captura%20desde%202026-11-09%2013-54-24.png)

### PASOS PREVIOS

Se instalarán los recursos Contactos, Ventas, Facturación e Inventario (algunos de ellos ya venian instalados)

![6](/CAPTURAS%20SXE/Captura%20desde%202026-11-09%2009-38-08.png)

Si se accede al apartado facturas ya se verá que la localización fiscal está en España, ya que se utilizan los euros como divisa (esto es relevante, se explicará más adelante)

![7](/CAPTURAS%20SXE/Captura%20desde%202026-11-09%2009-55-53.png)

### 2º EJERCICIO - TIPOS DE PRODUCTO localiza en demo un producto de cada tipo, fíjate en si tiene impuestos asignados y haz una captura de su ficha

Para acceder a la pantalla que se ve en la imagen habrá que hacer el siguiente proceso: "Ventas" -> En la parte superior "Productos" -> "Productos".

Se verán todos los productos creados.

1. Producto tipo: Bienes

![8](/CAPTURAS%20SXE/Captura%20desde%202026-11-09%2012-24-38.png)

Aparece con un impuesto automaticamente del 21%, que corresponde al IVA de la fiscalidad española.

2. Producto tipo: Servicio

![9](/CAPTURAS%20SXE/Captura%20desde%202026-11-09%2012-25-28.png)

Aparece sin impuesto, pero se le podría añadir un IVA del tipo servicio del 21%

3. Producto tipo: Combinación

![10](/CAPTURAS%20SXE/Captura%20desde%202026-11-09%2012-26-23.png)

No tiene IVA

**¿PORQUE ALGUNOS APARECEN CON IVA Y OTROS NO?**

Al crear la base de datos con los datos demo esto viene así por las categorías de cada producto. Los bienes pertenecen a categorías que ya tienen puesto el IVA del 21% de forma fija, por eso ya viene con el asignado. Los servicios y combinación están sin impuestos asignado para poder ver ejemplos reales de productos donde el IVA se añade manualmente según el tipo de venta que sea. El campo servicio tiene un campo para añadir el impuesto aunque no se añada de forma automática, mientras que los productos combinación no aparece ya que al ser varios productos en uno su IVA variará según los productos que lo compongan 

### 3º EJERCICIO. RECORRIDO. Haz este recorrido y guarda una captura de cada paso.

1. Contactos: abre un contacto de empresa y uno de persona. Fíjate en la diferencia entre Compañía e Individuo y en cómo las personas quedan vinculadas a su empresa.

En primer lugar se accederá a la utilidad *"Contactos"*.

Una vez aquí habrá una lista de contactos. Se accede a cualquiera y se verá la información que se ve en pantalla, este primer ejemplo es una compañia.

![11](/CAPTURAS%20SXE/Captura%20desde%202026-11-09%2012-43-33.png)

El siguiente es un individuo, el cual está vinculado a la empresa, (este fué un error mío ya que no elegí un individuo propiamente dicho, si no un elemento de una empresa)

![12](/CAPTURAS%20SXE/Captura%20desde%202026-11-09%2012-46-29.png)

**DIFERENCIAS ENTRE COMPAÍA E INDIVIDUO**

1 -> La compañía es un elemento principal que actúa como padre para otros elementos mas pequeños, mientras que un individuo puede ser individual o puede estar vinculado a esta

2 -> El individuo tiene el campo "puesto de trabajo, la compañia no

3 -> La compañia tiene individuos vinculados, el individuo tiene la empresa a la que pertenece

4 -> La compañia tiene NIF, el individuo hereda sus datos fiscales

Este individuo es el mejor ejemplo de vinculación ya que obligatoriamente tiene que pertenecer a una empresa madre. Cuenta con un código y en vez de un NIF ya que utiliza el de la empresa.

2. Contactos: crea un cliente nuevo con su CIF y dirección, y asígnale una etiqueta

En contactos se le da al icono que dice "nuevo" y se realiza todo el proceso que se ve en la imagen. En este ejemplo es la creación de una compañia cliente

![13](/CAPTURAS%20SXE/Captura%20desde%202026-11-09%2012-53-43.png)

3. Productos: crea un servicio Hora de soporte a 40 € con Impuesto de ventas del 21 % y un bien Libro técnico a 25 € con el 4 %. Marca Ventas en los dos.

Para acceder a la pantalla que se ve en la imagen habrá que hacer el siguiente proceso: "Ventas" -> En la parte superior "Productos" -> "Productos".

Se verán todos los productos creados. Se hace clic en el apartado "Nuevo" y se rellena cada campo con la información que se ve en las imagenes para cumplir las instrucciones indicadas

![14](/CAPTURAS%20SXE/Captura%20desde%202026-11-09%2012-55-36.png)

![15](/CAPTURAS%20SXE/Captura%20desde%202026-11-09%2012-58-05.png)

4. Ventas: crea un presupuesto para ese cliente con esos dos productos, envíalo (sin correo real), confírmalo y fíjate en que pasa a ser pedido de venta.

Para acceder a la pantalla que se ve en la imagen habrá que hacer el siguiente proceso: "Ventas" -> En la parte superior "Pedidos" -> "Presupuestos".

Aquí se verán los presupuestos. Se le da a nuevo para crear uno. Se añade en el primer apartado el cliente que se creó anteriormente y se añaden los dos productos (En la imagen se ve como se rellenó toda la información)

![16](/CAPTURAS%20SXE/Captura%20desde%202026-11-09%2013-05-26.png)

Para continuar se la da a enviar y se verá una plantilla preeliminar del mensaje que se va a enviar

![17](/CAPTURAS%20SXE/Captura%20desde%202026-11-09%2013-06-27.png)

Se le da a continuar y aparecerá una plantilla preeliminar de un email como el que posteriormente se enviará.

![18](/CAPTURAS%20SXE/Captura%20desde%202026-11-09%2013-07-00.png)

Ya aparecerá como enviado

![19](/CAPTURAS%20SXE/Captura%20desde%202026-11-09%2013-13-18.png)

Se le da a confirmar y pasará a la última fase en la que el pedido ya está en fase de venta

![20](/CAPTURAS%20SXE/Captura%20desde%202026-11-09%2013-13-59.png)

5. Facturación: desde el pedido, crea la factura y comprueba que cada línea lleva su IVA y que el total cuadra. Confírmala, imprímela en PDF y registra el pago. Comprueba la etiqueta Pagado 

En la misma pantalla se le da a crear factura y se selecciona la opción "factura normal" -> "crear borrador"

![21](/CAPTURAS%20SXE/Captura%20desde%202026-11-09%2013-14-37.png)

Se verá un borrador de la factura con toda la información que fué añadida. Se confirmará el borrador.

![22](/CAPTURAS%20SXE/Captura%20desde%202026-11-09%2013-15-13.png)

Por último aparecerá la plantilla de email con el mensaje y los archivos listo para ser enviados

![23](/CAPTURAS%20SXE/Captura%20desde%202026-11-09%2013-15-32.png)

Ya aparecerá en estado "Enviada"

![24](/CAPTURAS%20SXE/Captura%20desde%202026-11-09%2013-15-52.png)

Se le da a la opción de "Pagar" y se crea el pago

![25](/CAPTURAS%20SXE/Captura%20desde%202026-11-09%2013-16-35.png)

Y ya aparecerá la factura pagada, y ya se le podrá dar a la opción de imprimir para imprimir en PDF

![26](/CAPTURAS%20SXE/Captura%20desde%202026-11-09%2013-16-47.png)

6. Facturación: localiza una factura de proveedor de los datos de demostración y compara sus campos con una de cliente.

Para acceder a la pantalla que se ve en la imagen habrá que hacer el siguiente proceso: "Facturación" -> En la parte superior "Proveedores" -> "Facturas".

Se abre la que se ve en la imagen que viene con los datos de demostración y es de proveedor (se me olvidó la captura a una factura de cliente así que lo explicaré en texto)

**DIFERENCIAS**

1 -> El campo de contacto aparece con la etiqueta "Proveedor"

2 -> Muestra el campo "Referencia de factura", en el que se registra el número de factura que envio el proveedor. Este campo en el cliente corresponde a la referencia de la venta

3 -> En el campo "Banco destinatario" aparece la cuenta bancaria de donde se le ingresará el dinero al proveedor, mientras que en una factura de cliente estaría la cuenta de nuestra empresa para realizar el cobro

4 -> En la parte de impuestos se ve el impuesto de compra, mientras que en una de cliente se mostraría automaticamente el impuesto de venta

5 -> La factura de proveedor permite registrar la fecha en la que se recibió el documento por parte de la empresa, mientras que en la de cliente esto se genera de forma automática.

![27](/CAPTURAS%20SXE/Captura%20desde%202026-11-09%2013-18-41.png)

7. Chatter: en la parte derecha o inferior de cualquier registro está el historial de cambios, mensajes y actividades. Programa una actividad (una llamada) para el cliente

Para acceder a la pantalla que se ve en la imagen habrá que hacer el siguiente proceso: Contactos -> Se clica en el cualquier contacto (en este caso el cliente que se creó con anterioridad).

Abajo aparece una opción que dice "Actividad", se clicará en ella. Aperecerá la pantalla emergente que se ve en la imagen en la que se puede programar una actividad. 

Se elige la opción llamada, se rellena con la información que se ve en la imagen y se crea

![28](/CAPTURAS%20SXE/Captura%20desde%202026-11-09%2013-24-51.png)

Ya se ve abajo la tarea programada

![29](/CAPTURAS%20SXE/Captura%20desde%202026-11-09%2013-25-12.png)

### 4º EJERCICIO. BÚSQUEDA GUARDADA. en Facturación → Clientes → Facturas, muestra solo las facturas publicadas, agrupadas por cliente, en vista lista, y guárdalo como favorito.

Se entra en la ubicación mencionada, y se verá la siguiente pantalla:

![30](/CAPTURAS%20SXE/Captura%20desde%202026-11-09%2013-36-28.png)

Aquí se verán todas las facturas. Para aplicar el filtro se hace clic en la flecha a la derecha del todo de la barra de búsqueda donde se podrán añadir filtros de busqueda. Para cumplir los requisitos del ejercicio habrá que seleccionar la opción "Registrado", "Socio" y guardar dicha selección en favoritos con una etiqueta.

![31](/CAPTURAS%20SXE/Captura%20desde%202026-11-09%2013-41-13.png)

Se utiliza dicho filtro y ya se verán las facturas con estos requisitos en formato lista

![32](/CAPTURAS%20SXE/Captura%20desde%202026-11-10%2010-35-39.png)

### 5º EJERCICIO: MODO DESARROLLADOR Con el modo desarrollador activo, averigua el nombre técnico de dos campos del formulario de contacto y el modelo de una factura.

Para esto se accederá al modo desarrollador con la url que se ve en la imagen, añadiendo después de odoo "?debug=1". Se verá la siguiente pantalla que ya mostrará que se entró en este modo, además que se verá el icono de un escarabajo al lado de la opció de chateo indicando esto también

![33](/CAPTURAS%20SXE/Captura%20desde%202026-11-09%2013-43-36.png)

Otra forma de hacerlo será acceder a la utilidad "ajustes" y acceder a "Herramientas de administrador" -> "Activar modo de desarrollador con activos"

![34](/CAPTURAS%20SXE/Captura%20desde%202026-11-09%2013-44-26.png)

Para hacer las comprobaciones que pide el enunciado desde aquí será tan facil como en la pantalla que se ve en la imagen acceder a "Compañias" y se entrar en la compañia que se ve

![35](/CAPTURAS%20SXE/Captura%20desde%202026-11-09%2013-44-51.png)

Si se mantiene el puntero del ratón en la interrogación de algún campo se mostrará el nombre técnico de estos.

**NOMBRE TÉCNICO** -> vat

![36](/CAPTURAS%20SXE/Captura%20desde%202026-11-09%2013-46-44.png)

**NOMBRE TÉCNICO** -> category_id

![37](/CAPTURAS%20SXE/Captura%20desde%202026-11-09%2013-46-57.png)

En una factura el nombre técnico del campo modelo es: account.move

| Nombre | Nombre técnico |
| :--- | :--- |
| nif | vat |
| etiquetas | category_id |
| modelo (factura) | zccount.move |

### 6º EJERCICIO:  Incidencias: tabla con fecha, síntoma, causa y solución de cada problema encontrado.

| Fecha | Síntoma | Causa                                                                                                                                                                                                                                                   | Solución                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                         |
| :--- | :--- |:--------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------|:-----------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------|
| 11/11/2026 | Divisa | al crear la base de datos con los datos de demo, a pesar de poner idioma y lugar en España, la información fiscal aparecía en dolares estadounidenses. Esto se debe a que estos datos de prueba vienen de una empresa ficticia con esta localización    | Clique en el icono de una empresa en la parte de arriba del menú, y seleccioné la empresa que ya aparecía con la localización en España (que es la que se estableció al crear la base de datos) y se corrigió este error, dandome ya así los campos en euros y con sus respectivos impuestos. Cabe recalcar que a pesar de ello algunos campos aparecen aún en dolares, utilicé la IA para consultar este error, y es porque se queda anclado en esa información, a pesar de ello la información fiscal ya está puesta en España, por tanto es solo un error visual y no afecta al desarrollo de las operaciones |
| 11/11/2026 | Impuesto en producto | Al crear el producto libro técnico, Odoo me asignó automaticamente un impuesto del 21% a pesar de que le había puesto del 4% al crearlo, esto pasa porque Odoo añade los impuestos predetermiandos, y hace que a veces se sobreescriba esta información | lo solucioné simplemente creandolo de nuevo, de esta forma ya aplicó los cambios y se estableció correctamente.                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                  |
| 11/11/2026 | Capturas de pantalla del apartado 1 del ejercicio 3 | La captura de pantalla no es como tal un individuo (como declaré entre parentesis en el apartado), si no una dirección dentró de una empresa (un departamento)                                                                                          | La explicación de diferencias que puse es sola escrita y no se ve de forma gráfica en las imagenes (Al haberlo añadido, debajo de esta tabla explico la diferencia entre este elemento y una compañia)                                                                                                                                                                                                                                                                                                                                                                                                           |
| 11/11/2026 | Nombre técnico de una factura | Se me olvido comprobar este campo con una captura de pantalla | añadí la respuesta unicamente en formato de texto en el apartado correspondiente                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                 |

TABLA DE DIFERENCIAS ENTRE DEPARTAMENTO Y COMPAÑIA

1-> Este elemento pertenece obligatoriamente a una compañia, la compañia no pertenece a nadie

2-> El departamento se puede clasificar en base a su función, mientras que la compañía en base los departamentos que tiene vinculados

3-> El departamento almacena una dirección física específica, mientras que la compañía una dirección fiscal

### 7º EJERCICIO: Declaración de uso de IA: herramienta, para qué la usaste y qué cambiaste de su salida, o "No se ha usado IA".

- Utilicé la IA de Gemini para intentar resolver el problema que mencioné en el primer punto del ejercicio anterior, sin embargo no me dió una solución, simplemente me dijo que es un problema interno de Odoo al crear la base de datos con los datos de demostración, pero que a pesar de ello no influía en la fiscalidad, solo erá visual. El prompt que utilicé para intentar resolverlo fue: "He hecho todos los cambios para que la información fiscal este en España, me aparece todo en euros y con los impuestos correspondientes, porque algunos campos, como los objetos de ejemplo en ventas, me siguen apareciendo con dolares aunque abajo aparezca el impuesto español y un campo en euros"

- Le consulte a la IA de Gemini porque los productos de tipo Bienes aparecian con impuesto automaticamente, mientras que los de servicio y combinación no, la respuesta está en la pregunta que añadí en el ejercicio 1. El prompt que utilicé fué el siguiente: "Tengo una base de datos con datos de demostración en el servicio Odoo. Tengo la fiscalidad española, porque los productos tipo bienes vienen con el impuesto añadido automaticamente, mientras que los de servicio y combinación no"

- Utilicé la IA de Gemini para corregir la ortografía y expresión en las explicaciones. El prompt que utilicé fue: "Dime que faltas ortográficas hay en esta frase ... Y que expresiones mas técnicas podría utilizar"

