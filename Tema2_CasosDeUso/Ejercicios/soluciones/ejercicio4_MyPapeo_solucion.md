# Ejercicio 4: MyPepeo.com

## Enunciado

Necesita crearse el diagrama de casos de uso del nuevo sitio web MyPapeo.com, en el que cualquier cliente puede realizar un pedido a un restaurante por internet.  

El proceso se inicia cuando el cliente crea un pedido. El cliente tendrá que elegir uno de los restaurantes asociados a nuestro sistema. Existen restaurantes de todas las temáticas (chileno, mexicano, indio, etc.). Una vez seleccionado el restaurante, puede optar por elegir alguno de los menús que el restaurante propone o ir incluyendo plato a plato su pedido.  

Una vez elegida la comida, se realizará la configuración del envío del pedido, para lo cual el  usuario tendrá que proporcionar una dirección de entrega y un método de pago (PayPal, VISA, etc.).  

Introducida la información anterior, se procede a cobrar el pedido con lo cual el sistema se comunicará con una pasarela de pago externa (terminal virtual del banco, PayPal, etc.) y, una vez recibido y comprobado el pago, se enviará el pedido al restaurante.  

Los restaurantes tienen en MyPapeo.com una cuenta en la que irán acumulando el dinero de todos los pedidos recibidos. Cuando lo estimen oportuno, podrán volcar el contenido de esa cuenta en una cuenta bancaria configurada a tal efecto. 

Al día siguiente de recibir el pedido el sistema envía automáticamente un email al cliente para que escriba una crítica del restaurante. Esa crítica se añadirá a la ficha del restaurante. Los demas clientes podrán si quieren consultar las criticas del restaurante para seleccionar o no dicho restaurante.

Basado en el documento . Una empresa propietaria de inmuebles necesita un sistema.


## Diagrama

![alt text](imagenes/ejercicio4_mypapeo_casos_de_uso.png)