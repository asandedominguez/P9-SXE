# Tarea 09 · Implantación de Odoo

### <ins>Adrián Sande Domínguez<ins>

### 1º EJERCICIO - BASES DE DATOS: Captura del gestor con demo y primo, e idioma y país con que se crearon.

Después de hacer el despliegue correspondiente y completar todas las operaciones en Docker Compose, se accederá al servicio Odoo a través de la url: http://localhost:8069  

Una vez hecho esto se verá la siguiente pantalla:

![1](/CAPTURAS%20SXE/Captura%20desde%202026-11-09%2009-32-04.png)

Aquí se establecerán todos los datos para crear o restaurar una base de datos. En este caso habrá que crear una nueva, para ello se rellenará cada campo con su información correspondiente. Esta primera base de datos se creará añadiendo la opción demo, que hará que se cuente con ciertas funcionalidades base preeinstaldas con datos de desmostración, que servirán para explorar y hacer operaciones sin afectar a la base de datos real.

Después de esperar unos minutos ya estará listo el servicio y se verá la pantalla inicial.

![2](/CAPTURAS%20SXE/Captura%20desde%202026-11-09%2009-33-49.png)

Para acceder al gestor de bases de datos y poder crear una nueva se entrará en la url que se ve arriba en el buscador. Es la misma con la que se entra al servicio añadiendo /web/database/manager (en la imagen se ve ya creada la otra base de datos, en la siguiente parte de mostrará y explicará el como se hizo).

![3](/CAPTURAS%20SXE/Captura%20desde%202026-11-09%2013-56-13.png)

Se clica en "Create database" y se rellenarán los mismos campos que la primera vez

![4](/CAPTURAS%20SXE/Captura%20desde%202026-11-09%2013-53-47.png)

Después de unos minutos ya estará creada la base de datos y el servicio estará operativo

![5](/CAPTURAS%20SXE/Captura%20desde%202026-11-09%2013-54-24.png)

### PASOS PREVIOS

Se instalarán los recursos Contactos, Ventas, Facturación e Inventario (algunos de ellos ya venian instalados)

![6](/CAPTURAS%20SXE/Captura%20desde%202026-11-09%2009-38-08.png)

Si se accede al apartado facturas ya se verá que la localización fiscal esta en España, ya que se utilizan los euros como divisa (esto es relevante, se explicará más adelante)

![7](/CAPTURAS%20SXE/Captura%20desde%202026-11-09%2009-55-53.png)

### 2º EJERCICIO - TIPOS DE PRODUCTO localiza en demo un producto de cada tipo, fíjate en si tiene impuestos asignados y haz una captura de su ficha

Para acceder a la pantalla que se ve en la imagen habrá que hacer el siguiente proceso: Ventas -> En la parte superior Productos -> Productos.

Se verán todos los productos creados.

1. Producto tipo: Bienes

![8](/CAPTURAS%20SXE/Captura%20desde%202026-11-09%2012-24-38.png)

Aparece con un impuesto del 21%, que corresponde al IVA de la fiscalidad española.

2. Producto tipo: Servicio

![9](/CAPTURAS%20SXE/Captura%20desde%202026-11-09%2012-25-28.png)

3. Producto tipo: Combinación

![10](/CAPTURAS%20SXE/Captura%20desde%202026-11-09%2012-26-23.png)

**¿PORQUE ALGUNOS APARECEN CON IVA Y OTROS NO?**

Al crear la base de datos con los datos demo el comportamiento está establecido así para que se pueda consultar con ejemplos reales como se verían bienes con IVA fijo y de servicios o combos con IVA flexible.

### 3º EJERCICIO. RECORRIDO. Haz este recorrido y guarda una captura de cada paso.

1. Contactos: abre un contacto de empresa y uno de persona. Fíjate en la diferencia entre Compañía e Individuo y en cómo las personas quedan vinculadas a su empresa.

En primer lugar accederemos a la utilidad *"Contactos"*.

Una vez aquí habrá una lista de contactos. Se accede a cualquiera y se verá la información que vemos en pantalla, este primer ejemplo es una compañia.

![11](/CAPTURAS%20SXE/Captura%20desde%202026-11-09%2012-43-33.png)

El siguiente es un individuo (El cual está vinculado a la empresa, este fué un error mío ya que no elegí un individuo propiamente dicho, si no un elemento de una empresa)

![12](/CAPTURAS%20SXE/Captura%20desde%202026-11-09%2012-46-29.png)

**DIFERENCIAS**

1 -> La compaía tiene un NIF, el individuo un código

2 -> El individuo tiene roles, la compañia no

3 -> La compañia tiene sitio web

4 -> La compañia tiene etiquetas

5 -> El individuo cuenta con apartado para notas, GLN físico y punto lógico operacional

Este individuo es el mejor ejemplo de vinculación ya que obligatoriamente tiene que pertenecer a una empresa madre. Cuenta con un código y en vez de un NIF ya que utiliza el de la empresa.

2. Contactos: crea un cliente nuevo con su CIF y dirección, y asígnale una etiqueta

En contactos le damos al icono que dice nuevo y realizamos todo el proceso que se ve en la imagen. En este ejemplo es la creación de una compañia cliente

![13](/CAPTURAS%20SXE/Captura%20desde%202026-11-09%2012-53-43.png)

3. Productos: crea un servicio Hora de soporte a 40 € con Impuesto de ventas del 21 % y un bien Libro técnico a 25 € con el 4 %. Marca Ventas en los dos.

Para acceder a la pantalla que se ve en la imagen habrá que hacer el siguiente proceso: Ventas -> En la parte superior Productos -> Productos.

Se verán todos los productos creados. Se clica en el apartado "Nuevo" y se rellena cada campo con la información que se ve en las imagenes para cumplir las instrucciones indicadas

![14](/CAPTURAS%20SXE/Captura%20desde%202026-11-09%2012-55-36.png)

![15](/CAPTURAS%20SXE/Captura%20desde%202026-11-09%2012-58-05.png)

4. Ventas: crea un presupuesto para ese cliente con esos dos productos, envíalo (sin correo real), confírmalo y fíjate en que pasa a ser pedido de venta.

Para acceder a la pantalla que se ve en la imagen habrá que hacer el siguiente proceso: Ventas -> En la parte superior Pedidos -> Presupuestos.

Aquí se verán los presupuestos. Se le da a nuevo para crear uno, se añade en el primer aparado el cliente que se creó antes y se añaden los dos productos (En la imagen se ve como se rellenó toda la información)

![16](/CAPTURAS%20SXE/Captura%20desde%202026-11-09%2013-05-26.png)

Para continuar se la da a enviar y se verá una plantilla preeliminar del mensaje que se va a mandar

![17](/CAPTURAS%20SXE/Captura%20desde%202026-11-09%2013-06-27.png)

Se le da acontinuar y aparecerá una plantilla preeliminar de un email

![18](/CAPTURAS%20SXE/Captura%20desde%202026-11-09%2013-07-00.png)

Ya aparecerá como enviada 

![19](/CAPTURAS%20SXE/Captura%20desde%202026-11-09%2013-13-18.png)

Se le da a confirmar y pasará a la última fase en la que el pedido ya está en fase de venta

![20](/CAPTURAS%20SXE/Captura%20desde%202026-11-09%2013-13-59.png)

5. Facturación: desde el pedido, crea la factura y comprueba que cada línea lleva su IVA y que el total cuadra. Confírmala, imprímela en PDF y registra el pago. Comprueba la etiqueta Pagado 

En la misma pantalla se le da a crear factura y se selecciona la opción factura normal -> crear borrador

![21](/CAPTURAS%20SXE/Captura%20desde%202026-11-09%2013-14-37.png)

Se verá un borrador de la factura con toda la información que fué añadida. Se confiarma el borrador

![22](/CAPTURAS%20SXE/Captura%20desde%202026-11-09%2013-15-13.png)

Por último aparecerá la plantilla de email con el mensaje y los archivos listo para ser enviados

![23](/CAPTURAS%20SXE/Captura%20desde%202026-11-09%2013-15-32.png)

Ya aparecerá en estado "Enviada"

![24](/CAPTURAS%20SXE/Captura%20desde%202026-11-09%2013-15-52.png)

Se le da a la opción de "Pagar" y se crea el pago

![25](/CAPTURAS%20SXE/Captura%20desde%202026-11-09%2013-16-35.png)

Y ya aparecerá la factura pagada

![26](/CAPTURAS%20SXE/Captura%20desde%202026-11-09%2013-16-47.png)

6. Facturación: localiza una factura de proveedor de los datos de demostración y compara sus campos con una de cliente.

Para acceder a la pantalla que se ve en la imagen habrá que hacer el siguiente proceso: Facturación -> En la parte superior Proveedores -> Facturas.

Se abré la que se ve en la imagn que viene con los datos de demostración y es de proveedor (se me olvid la captura a una factura de cliente así que lo explicaré en texto)

**DIFERENCIAS**

1 -> El campo de contacto aparece con la etiqueta "Proveedor"

2 -> Muestra el campo "Referencia de factura", en el que se registra el número de factura que envio el proveedor. Este campo no existe en el cliente

3 -> En el campo Banco destinatario aparece la cuenta bancaria del proveedor, mientras que en  una factura de cliente estaría la cuenta del mismo

4 -> En la parte de impuestos se ve el impuesto de compra, mientras que en una de cliente se mostraría automaticamente el impuesto de venta

5 -> La fecha de factura y conyable es diefrente en la de proveedor, meintras que en la cliente es seimpre la misma

![27](/CAPTURAS%20SXE/Captura%20desde%202026-11-09%2013-18-41.png)

7. Chatter: en la parte derecha o inferior de cualquier registro está el historial de cambios, mensajes y actividades. Programa una actividad (una llamada) para el cliente

Para acceder a la pantalla que se ve en la imagen habrá que hacer el siguiente proceso: Contactos -> Se clica en el cualquier contacto (en este caso el cliente que se creó con anterioridad).

Abajo aparece una opción que dice "Actividad", se clicará en ella. Aperecerá la pantalla emergente que se ve en la imagen en la que se puede programar una actividad. 

Se elige la opción llamada, se rellena con la información que se ve en la imagen y se crea

![28](/CAPTURAS%20SXE/Captura%20desde%202026-11-09%2013-24-51.png)

Ya se ve abajo la tarea programada

![29](/CAPTURAS%20SXE/Captura%20desde%202026-11-09%2013-25-12.png)

### 4º EJERCICIO. BÚSQUEDA GUARDADA. en Facturación → Clientes → Facturas, muestra solo las facturas publicadas, agrupadas por cliente, en vista lista, y guárdalo como favorito.
