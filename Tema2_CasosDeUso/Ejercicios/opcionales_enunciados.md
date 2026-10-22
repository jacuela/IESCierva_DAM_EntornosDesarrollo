# MAS EJERCICIOS OPCIONALES

## Ejercicio: El Cajero Automático Avanzado

Un cliente bancario se acerca a un cajero. Su objetivo principal es **"Sacar Dinero"**.
Para sacar dinero, el sistema **siempre** debe **"Validar PIN"** y **"Comprobar Saldo"**.
Si el cliente introduce mal el PIN tres veces, el sistema ejecutará la acción **"Retener Tarjeta"** (esto es una extensión de la validación).
El cliente también puede **"Realizar Transferencia"** y **"Consultar Movimientos"**. Todas estas operaciones requieren, por seguridad, **"Validar PIN"**.
Un **Técnico de Mantenimiento** puede acceder al cajero para **"Reponer Billetes"** y **"Reiniciar Sistema"**, pero requiere una autenticación especial mediante llave física.

## Ejercicio: Sistema de Puntos de Información Universitaria (PIU)

Basado en el documento . La universidad instala kioscos informativos.

* **Usuario Final** (Alumno/Profesor/PAS): Puede **"Obtener Información"**. Para acceder a información privada (notas, nóminas), el sistema debe **"Identificar Usuario"** obligatoriamente.
* **Administrador**: Se encarga de la **"Instalación de PIUs"**. Esto puede implicar "Instalar Nuevo PIU" o "Instalar PIU Existente" (especialización). Esta acción siempre requiere registrar la ubicación.
* **Gestor**: Se encarga del **"Control de Funcionamiento"**. Si detecta un fallo, puede (opcionalmente) **"Realizar Acciones Correctivas"** (como reiniciar).
* **Operador**: Se encarga de la **"Gestión de Red"** y ver estadísticas.
* *Nota:* Todos los actores (Admin, Gestor, Operador, Usuario) deben autenticarse para entrar a sus menús, excepto para ver información pública.

## Ejercicio: App de Comida "Pesadilla en la Cocina"

Basado en el documento . Chicote diseña una app para controlar el caos.

* El **Camarero** utiliza la app para **"Gestionar Comanda"**. Esto incluye anotar platos y enviarlos a cocina.
* El **Cocinero** recibe la comanda y debe **"Confirmar Elaboración"**. Si faltan ingredientes (caso excepcional), debe **"Notificar Falta de Stock"** al sistema, lo cual cancela parcialmente la comanda.
* El **Cliente** (que descargó la app) puede **"Reservar Mesa"** y, tras comer, **"Evaluar Servicio"**.
* Chicote (**Supervisor**) puede ver todas las evaluaciones y **"Despedir Empleado"** si la media baja de 2 estrellas.
* Tanto "Reservar Mesa" como "Gestionar Comanda" incluyen obligatoriamente **"Verificar Disponibilidad"**.

## Ejercicio: Gestión de Biblioteca Municipal

Basado en.
Un **Socio** quiere llevarse libros. El caso de uso principal es **"Realizar Préstamo"**.
Para realizar un préstamo, el sistema debe **"Comprobar Sanciones"** (si tiene multas, no puede llevarse nada).
Si el libro no está disponible, el socio puede **"Realizar Reserva"**.
El **Bibliotecario** se encarga del CRUD de Libros (Alta, Baja, Modificación, Consulta) y del CRUD de Socios.
Además, el Bibliotecario registra la **"Devolución de Libro"**. Si el libro se devuelve tarde, el sistema extiende este caso de uso con **"Imponer Sanción"**.

## Ejercicio: Red Social "FaceSpace"

Basado en.
Un **Usuario Registrado** entra al sistema (Login). Puede **"Publicar Contenido"**.
Puede **"Comentar Publicación"** de otros.
Puede realizar un CRUD sobre su propio **Perfil** (Modificar foto, datos, etc.).
Si el sistema detecta palabras ofensivas en un comentario o publicación, extiende la acción con **"Bloquear Contenido Automáticamente"**.
Un usuario puede **"Denunciar Usuario"**.
Un **Moderador** recibe las denuncias y puede **"Banear Usuario"**.

## Ejercicio: Gestión de Calificaciones Académicas

Basado en .
El **Profesor** accede al sistema. Su tarea principal es **"Rellenar Acta"**.
Para rellenar el acta, puede ir alumno por alumno. El sistema le ofrece una herramienta de ayuda: **"Usar Calculadora"** (es opcional, un `<<extend>>` de rellenar acta) para sumar parciales.
El profesor puede **"Firmar Acta"**. Una vez firmada, no se puede tocar.
El **Alumno** solo puede **"Consultar Notas"**.
El **Administrador** gestiona el CRUD de Asignaturas y Grupos.
Al "Consultar Notas" o "Rellenar Acta", el sistema siempre registra un log de acceso (`<<include>>` **"Registrar Acceso"**).

## Ejercicio: Máquina Expendedora Inteligente

Basado en .
El **Cliente** se acerca a comprar. Selecciona un producto.
El caso de uso es **"Comprar Refresco"**.
Esto incluye siempre **"Validar Monedas"**.
Si el importe es superior, se ejecuta **"Devolver Cambio"**.
Si no hay stock, el sistema ejecuta **"Mostrar Error de Stock"** (extensión).
El **Reponedor** puede **"Reponer Stock"** y **"Recaudar Dinero"**. Ambas acciones requieren **"Abrir Máquina"** con llave electrónica.

## Ejercicio: Clínica Veterinaria (Citas y CRUD)

El sistema debe permitir a un **Recepcionista** gestionar a los pacientes (mascotas). Debe poder hacer CRUD de Mascotas y CRUD de Dueños.
El Recepcionista también puede **"Agendar Cita"**. Al agendar, debe **"Buscar Hueco Libre"** (include).
El **Veterinario** atiende la cita. Realiza el caso de uso **"Redactar Diagnóstico"**. Si es necesario operar, se extiende con **"Programar Cirugía"**.
Al finalizar la consulta, se genera el cobro. **"Cobrar Consulta"** puede hacerse en efectivo o con tarjeta. Si es con tarjeta, incluye **"Conectar con Banco"**.