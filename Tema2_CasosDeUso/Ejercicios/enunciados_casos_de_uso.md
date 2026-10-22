# Ejercicios de Diagramas de Casos de Uso

## Instrucciones
- Crea los diagramas usando _Draw.io_. Guarda el archivo en tu pendrive por si tuvieras que modificar algo. Exporta el diagrama a .png o .jpg
- Para entregar las tareas, crea una carpeta TU_NOMBRE_EjercicioX, y dentro del mismo incluye un MarkDown con la solución/soluciones. En el artchivo MarkDown incluya la imagen. 
- Comprime la carpeta de la tarea en .zip y súbela al aula virtual.


CARPETA TU_NOMBRE_EJERCICIO  
&nbsp;&nbsp;&nbsp;&nbsp;|  
&nbsp;&nbsp;&nbsp;&nbsp;|-- resolucion.md  
&nbsp;&nbsp;&nbsp;&nbsp;|  
&nbsp;&nbsp;&nbsp;&nbsp;|--CARPETA IMG  
&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;    |  
&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;    | imagen.png  


- Para cada ejercicio, identifica los **Actores**, los **Casos de Uso** y las relaciones **<<include>>** (obligatorio/siempre ocurre) y **<<extend>>** (opcional/excepción)(Puedes hacer esta última con linea discontinua).
- Crear solo la ficha textual cuando se indique. 

## Ejercicio 1: La Tienda Online "CyberShop" (Carrito de Compra)

Una empresa de e-commerce necesita modelar su proceso de ventas. Cualquier usuario web puede buscar productos en el catálogo. Sin embargo, para realizar una compra, el usuario debe ser un **Cliente Registrado**. El proceso de **"Realizar Compra"** es el núcleo del sistema.
Para realizar la compra, el sistema **siempre** debe **"Verificar Stock"** de los productos. Además, durante la compra, si el cliente tiene un cupón promocional, puede **"Aplicar Descuento"** (esto no pasa siempre).
El pago se realiza dentro del proceso de compra, pero puede fallar. Si el pago es con tarjeta de crédito, el sistema conecta con una pasarela externa.
Existe un **Administrador** que puede gestionar el catálogo (CRUD de productos) y bloquear usuarios fraudulentos.

## Ejercicio 2: Gestión de Fincas "La Urbana" (CRUD Completo)

Una empresa propietaria de inmuebles necesita un app para gestionar el negocio. 
* El propietario gestiona los inmuebles. El propietario debe poder dar de alta, baja, modificar y consultar (CRUD) dichos inmuebles.
* Existe un inquilino (será requisito previo presentar nómina o aval). El inquilino puede alquilar un inmueble.
* Para alquilar, siempre es necesario identificarse. El inquilino también puede desalquilar o consultar sus recibos, acciones que también requieren identificación obligatoria.

FICHA TEXTUAL: Crear la del caso de uso "Alquilar Inmueble". 



## Ejercicio 3: Biblioteca online

Piensa en una biblioteca online para que la gente pueda leer libros (en soporte digital) que otros usuarios han aportado. Es decir, los libros son aportados por los propios usuarios. Incluye un usuario administrador, que puede hacer todo.

Con un compañero, piensa en los requisitos y diseña el diagrama de casos de uso. Se libre de pensar en la funcionalidad, generando entre 5 y 15 casos de uso.


## Ejercicio 4: Web MyPapeo.com.
Necesita crearse el diagrama de casos de uso del nuevo sitio web MyPapeo.com, en el que cualquier cliente puede realizar un pedido a un restaurante por internet.  

El proceso se inicia cuando el cliente crea un pedido. El cliente tendrá que elegir uno de los restaurantes asociados a nuestro sistema. Existen restaurantes de todas las temáticas (chileno, mexicano, indio, etc.). Una vez seleccionado el restaurante, puede optar por elegir alguno de los menús que el restaurante propone o ir incluyendo plato a plato su pedido.  

Una vez elegida la comida, se realizará la configuración del envío del pedido, para lo cual el  usuario tendrá que proporcionar una dirección de entrega y un método de pago (PayPal, VISA, etc.).  

Introducida la información anterior, se procede a cobrar el pedido con lo cual el sistema se comunicará con una pasarela de pago externa (terminal virtual del banco, PayPal, etc.) y, una vez recibido y comprobado el pago, se enviará el pedido al restaurante.  

Los restaurantes tienen en MyPapeo.com una cuenta en la que irán acumulando el dinero de todos los pedidos recibidos. Cuando lo estimen oportuno, podrán volcar el contenido de esa cuenta en una cuenta bancaria configurada a tal efecto. 

Al día siguiente de recibir el pedido el sistema envía automáticamente un email al cliente para que escriba una crítica del restaurante. Esa crítica se añadirá a la ficha del restaurante. Los demas clientes podrán si quieren consultar las criticas del restaurante para seleccionar o no dicho restaurante.