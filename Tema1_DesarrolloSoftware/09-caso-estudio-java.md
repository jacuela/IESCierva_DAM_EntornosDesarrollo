# 9. Caso de Estudio: El Lenguaje Java y la Plataforma Java

> 💡 **Punto de partida:** Hemos visto teoría sobre lenguajes, compilación, máquinas virtuales... pero, ¿cómo funciona todo esto en la práctica? Vamos a aplicar todo lo aprendido a un lenguaje real: **Java**.

> 💡 **¿Por qué me importa?**
> Porque Java es el lenguaje que utilizaremos en este curso. Aquí convergen muchos de los conceptos anteriores: Java es un lenguaje de alto nivel que se compila utilizando herramientas del **JDK**, genera **bytecode** y se ejecuta sobre la **JVM**, siguiendo un modelo de desarrollo orientado a objetos.

En los puntos anteriores vimos los conceptos teóricos. Ahora veremos cómo se aplican a un lenguaje real que utilizaremos en DAM.

### Objetivos de aprendizaje

- Conocer qué es Java y el ecosistema Java.
- Clasificar Java según las dimensiones vistas en la unidad.
- Entender el proceso de compilación mediante `javac`.
- Comprender el papel de la JVM y el JIT.
- Diferenciar JDK, JRE y JVM.
- Comprender qué ocurre desde que escribimos un programa Java hasta que se ejecuta.

---

# 9.1. Introducción a Java

**Java** es un lenguaje de programación de propósito general, orientado a objetos y multiplataforma.

Fue desarrollado inicialmente por **Sun Microsystems** bajo la dirección de **James Gosling** y apareció oficialmente en **1995**.

Una de sus características fundamentales es el principio:

> **"Write Once, Run Anywhere" (WORA)**  
> Escribe una vez y ejecuta en cualquier plataforma.

Esto es posible gracias a la **JVM (Java Virtual Machine)**.

### ¿Qué es Java?

Java no es únicamente un lenguaje. Cuando hablamos del ecosistema Java encontramos varios elementos:

- **Lenguaje Java**: sintaxis que utilizamos para programar.
- **JDK**: herramientas necesarias para desarrollar aplicaciones Java.
- **JVM**: máquina virtual que ejecuta el bytecode.
- **Biblioteca estándar de Java**: clases y APIs que podemos utilizar.
- **Herramientas de desarrollo**: `javac`, `java`, `javadoc`, etc.
- **Maven**: herramienta de gestión y construcción de proyectos que utilizaremos habitualmente.

Podemos representarlo así:

```text
                  ECOSISTEMA JAVA
                         │
        ┌────────────────┼────────────────┐
        │                │                │
      JDK              JVM          Bibliotecas
        │                │
   Herramientas      Ejecuta
        │             bytecode
   ┌────┴────┐
 javac      java
```

### JDK, JVM y JRE

Es importante diferenciar estos conceptos:

| Concepto | Significado | Función |
|---|---|---|
| **JVM** | Java Virtual Machine | Ejecuta el bytecode |
| **JRE** | Java Runtime Environment | Entorno necesario para ejecutar Java |
| **JDK** | Java Development Kit | Herramientas necesarias para desarrollar |
| **javac** | Java Compiler | Compila `.java` a `.class` |
| **java** | Lanzador de Java | Inicia la ejecución de un programa |

Actualmente, para desarrollar utilizaremos directamente el **JDK**.

---

# 9.2. Clasificación de Java según lo visto en la unidad

## 9.2.1. Según nivel de abstracción

Java es un lenguaje de **alto nivel**.

Esto significa que utiliza estructuras cercanas al lenguaje humano y proporciona mecanismos que nos permiten programar sin preocuparnos directamente de los detalles del hardware.

Por ejemplo:

```java
int suma = 5 + 3;
System.out.println(suma);
```

No necesitamos indicar qué registro del procesador utilizar ni qué posición concreta de memoria debe ocupar la variable.

El compilador y la JVM se encargan de gran parte de estos detalles.


### Comparación

```java
// Java: alto nivel
int suma = 5 + 3;
```

Frente a instrucciones de bajo nivel:

```asm
MOV AX, 5
ADD AX, 3
```

Y, finalmente, el lenguaje máquina:

```text
10110000 00000101
00000011 00000011
```

> 📝 **Idea importante:** cuanto mayor es el nivel de abstracción, menos necesitamos conocer los detalles internos del hardware para programar.

---

# 9.2.2. Según mecanismo de traducción

Java utiliza un modelo de **compilación a código intermedio + ejecución mediante máquina virtual**.

El proceso simplificado es:

```text
Código fuente
     │
     │ javac
     ▼
Bytecode
.class
     │
     │ JVM
     ▼
JIT
     │
     ▼
Código máquina
     │
     ▼
Procesador
```

Por ejemplo, escribimos:

```java
public class HolaMundo {
    public static void main(String[] args) {
        System.out.println("Hola Mundo");
    }
}
```

El compilador `javac` transforma el código fuente en **bytecode**:

```text
HolaMundo.java
       │
       │ javac
       ▼
HolaMundo.class
```

El archivo `.class` contiene bytecode.

Este bytecode no es código máquina específico de Windows, macOS o Linux.

La JVM de cada sistema se encarga de ejecutarlo.

> 💡 **Esta es una de las claves de Java:** el mismo `.class` puede ejecutarse en diferentes sistemas operativos siempre que exista una JVM compatible.

---

# 9.2.3. Según sistema de tipos

Java es un lenguaje de **tipado estático y fuerte**.

### Tipado estático

El tipo de una variable se determina en tiempo de compilación.

```java
int edad = 25;
String nombre = "Ana";
```

Esto no sería válido:

```java
int edad = "Ana";   // ❌ Error de compilación
```

El compilador detecta que estamos intentando almacenar un `String` en una variable de tipo `int`.

### Tipado fuerte

Java no permite realizar determinadas conversiones entre tipos incompatibles de forma automática.

Por ejemplo:

```java
int numero = 10;
String texto = "Hola";

// numero = texto;   // ❌ Error
```

### Inferencia de tipos

Java también permite utilizar `var` en determinados contextos:

```java
var edad = 25;
var nombre = "Ana";
```

El compilador determina el tipo:

```text
edad   → int
nombre → String
```

Pero `var` **no convierte Java en un lenguaje dinámicamente tipado**.

Una vez determinado el tipo, sigue siendo estático:

```java
var edad = 25;

// edad = "Hola";   // ❌ Error
```

### Comparativa

| Lenguaje | Tipado | Ejemplo |
|---|---|---|
| **Java** | Estático, fuerte | `int x = 5;` |
| **C#** | Estático, fuerte | `int x = 5;` |
| **Python** | Dinámico, fuerte | `x = 5` |
| **JavaScript** | Dinámico, débil | `x = 5; x = "hola";` |

---

# 9.2.4. Según paradigma

Java es principalmente un lenguaje **orientado a objetos**, aunque también incorpora características de otros paradigmas.

### Imperativo

Podemos indicar paso a paso qué debe hacer el programa:

```java
int suma = 0;

for (int i = 1; i <= 10; i++) {
    suma += i;
}

System.out.println("Suma: " + suma);
```

### Orientado a objetos

Java está especialmente diseñado alrededor de clases y objetos:

```java
class Animal {

    String nombre;

    void hablar() {
        System.out.println("...");
    }
}

class Perro extends Animal {

    @Override
    void hablar() {
        System.out.println("Guau!");
    }
}
```

Aquí podemos observar conceptos fundamentales de POO:

- Clases
- Objetos
- Herencia
- Métodos
- Polimorfismo

### Funcional

Java también incorpora características de programación funcional, especialmente desde Java 8.

Por ejemplo, expresiones lambda:

```java
List<Integer> numeros =
        List.of(1, 2, 3, 4, 5, 6, 7, 8, 9, 10);

numeros.stream()
       .filter(x -> x % 2 == 0)
       .forEach(System.out::println);
```

El resultado será:

```text
2
4
6
8
10
```

Por tanto, aunque Java es fundamentalmente orientado a objetos, también permite utilizar técnicas funcionales.



# 9.3. El proceso de compilación en Java

## 9.3.1. ¿Qué es `javac`?

`javac` es el **compilador de Java** incluido en el JDK.

Su función principal es transformar el código fuente:

```text
.java
```

en bytecode:

```text
.class
```

Por ejemplo:

```text
HolaMundo.java
      │
      │ javac
      ▼
HolaMundo.class
```

---

## 9.3.2. Fases de compilación en Java

Cuando compilamos un programa Java, el compilador analiza el código para comprobar que sea correcto.

Podemos relacionarlo con las fases estudiadas anteriormente:

| Fase | Qué hace | Ejemplo |
|---|---|---|
| **Léxico** | Identifica tokens | palabras, operadores, símbolos |
| **Sintáctico** | Comprueba la estructura | paréntesis, llaves, `;` |
| **Semántico** | Comprueba el significado | tipos incompatibles, variables inexistentes |
| **Generación** | Genera bytecode | archivos `.class` |

Por ejemplo:

```java
int numero = "Hola";
```

El código puede tener una estructura sintáctica válida, pero existe un problema de tipos.

El compilador detectará:

```text
incompatible types: String cannot be converted to int
```

---

# 9.3.3. El proceso completo

Podemos representar todo el proceso de esta forma:

```text
┌──────────────────────┐
│ Código fuente        │
│ HolaMundo.java       │
└──────────┬───────────┘
           │
           │ javac
           ▼
┌──────────────────────┐
│ Bytecode             │
│ HolaMundo.class      │
└──────────┬───────────┘
           │
           │ JVM
           ▼
┌──────────────────────┐
│ Carga y verificación  │
└──────────┬───────────┘
           │
           ▼
┌──────────────────────┐
│ JIT                  │
│ Compilación a nativo │
└──────────┬───────────┘
           │
           ▼
┌──────────────────────┐
│ Procesador           │
└──────────────────────┘
```

---

# 9.3.4. Ejemplo práctico

Creamos un archivo:

```text
HolaMundo.java
```

Con este contenido:

```java
public class HolaMundo {

    public static void main(String[] args) {
        System.out.println("¡Hola desde Java!");
    }
}
```

Compilamos:

```bash
javac HolaMundo.java
```

Se genera:

```text
HolaMundo.class
```

Ejecutamos:

```bash
java HolaMundo
```

Y obtenemos:

```text
¡Hola desde Java!
```

### ¿Qué ha ocurrido?

1. Hemos escrito código fuente en Java.
2. `javac` ha compilado el código.
3. Se ha generado `HolaMundo.class`.
4. El archivo contiene bytecode.
5. La JVM carga el bytecode.
6. La JVM utiliza el JIT cuando corresponde.
7. El procesador ejecuta código máquina.

---

# 9.3.5. El archivo `.class`

El archivo `.class` contiene, entre otra información:

- Bytecode.
- Información sobre clases.
- Métodos.
- Variables.
- Tipos.
- Información necesaria para que la JVM pueda ejecutar el programa.

Podemos imaginarlo como:

```text
┌─────────────────────────────┐
│       HolaMundo.class       │
├─────────────────────────────┤
│ Información de la clase     │
│ Métodos                     │
│ Tipos                       │
│ Bytecode                    │
│ Información adicional       │
└─────────────────────────────┘
```

> 💡 **Importante:** El `.class` no contiene directamente las instrucciones específicas de un procesador Intel, AMD o ARM. Contiene bytecode diseñado para ser ejecutado por una JVM.

---

# 9.4. La máquina virtual: JVM y JIT

## 9.4.1. ¿Qué es la JVM?

La **JVM (Java Virtual Machine)** es la máquina virtual que ejecuta el bytecode de Java.

Es uno de los elementos fundamentales del ecosistema Java.

Cuando ejecutamos:

```bash
java HolaMundo
```

la JVM se encarga de cargar y ejecutar el programa.

Entre sus funciones encontramos:

1. Cargar las clases necesarias.
2. Verificar el bytecode.
3. Gestionar la memoria.
4. Ejecutar el bytecode.
5. Utilizar el JIT para mejorar el rendimiento.
6. Gestionar automáticamente la memoria mediante el Garbage Collector.

---

# 9.4.2. Garbage Collector

Java utiliza un **Garbage Collector (GC)** para gestionar automáticamente la memoria.

Por ejemplo:

```java
Persona persona = new Persona();
```

Se crea un objeto en memoria.

Cuando un objeto deja de ser accesible, el Garbage Collector puede recuperar la memoria que ocupa.

```text
Objeto creado
     │
     ▼
Memoria
     │
     │ deja de ser accesible
     ▼
Garbage Collector
     │
     ▼
Memoria recuperada
```

Esto significa que el programador normalmente **no tiene que liberar manualmente la memoria**.

> 💡 **Importante:** El programador no decide exactamente cuándo se ejecuta el Garbage Collector. La JVM lo gestiona automáticamente.

---

# 9.4.3. JIT (Just-In-Time Compilation)

El **JIT** es el componente encargado de convertir determinadas partes del bytecode en **código máquina nativo** durante la ejecución.

Simplificando:

```text
Bytecode
   │
   ▼
  JIT
   │
   ▼
Código máquina
   │
   ▼
CPU
```

El JIT puede analizar qué partes del programa se ejecutan frecuentemente y optimizarlas para conseguir un mejor rendimiento.

> 💡 **Idea importante:** Java no se limita a interpretar el bytecode. La JVM utiliza técnicas de compilación JIT para conseguir un alto rendimiento.

---

# 9.4.4. ¿Por qué Java es multiplataforma?

Supongamos que tenemos:

```text
             Bytecode
                │
       ┌────────┼────────┐
       ▼        ▼        ▼
      JVM      JVM      JVM
    Windows    Linux    macOS
       │        │        │
       ▼        ▼        ▼
     CPU       CPU       CPU
```

El programa Java no necesita conocer directamente las características de cada procesador.

La JVM de cada plataforma se encarga de esa tarea.

---

# 9.5. Java y sus herramientas de desarrollo

Para trabajar con Java utilizaremos principalmente el **JDK**.

Entre las herramientas más importantes encontramos:

| Herramienta | Función |
|---|---|
| `javac` | Compila código Java |
| `java` | Ejecuta programas Java |
| `javadoc` | Genera documentación |
| `jar` | Crea archivos JAR |
| `jshell` | Permite probar código Java de forma interactiva |

Además, utilizaremos un **IDE**, como NetBeans, IntelliJ IDEA o Eclipse, que facilita la escritura, compilación y ejecución de nuestros programas.

---

# 9.5.1. Maven

En nuestros proyectos también utilizaremos **Maven**.

Maven es una herramienta de gestión y construcción de proyectos Java.

Permite:

- Gestionar dependencias.
- Compilar proyectos.
- Ejecutar diferentes fases del proyecto.
- Generar archivos `.jar`.
- Automatizar tareas.

La configuración principal de Maven se encuentra en:

```text
pom.xml
```

Por ejemplo:

```xml
<dependency>
    <groupId>org.example</groupId>
    <artifactId>mi-libreria</artifactId>
    <version>1.0</version>
</dependency>
```

Maven descarga y gestiona automáticamente las dependencias necesarias.

---

# 9.5.2. JAR

Cuando distribuimos una aplicación Java podemos utilizar un archivo:

```text
.jar
```

Un JAR puede contener:

- Clases `.class`
- Recursos
- Información de configuración
- Metadatos

Podemos verlo como un paquete que contiene los elementos necesarios de nuestra aplicación.

Por ejemplo:

```text
MiAplicacion.jar
├── META-INF
├── com/
│   └── ejemplo/
│       ├── Main.class
│       └── Persona.class
└── recursos/
```

---

# 9.6. Comparación con C#

Java y C# presentan muchas similitudes porque ambos fueron diseñados como lenguajes modernos orientados a objetos y utilizan máquinas virtuales.

| Característica | Java | C# |
|---|---|---|
| **Lenguaje** | Java | C# |
| **Compilador** | `javac` | Roslyn |
| **Código intermedio** | Bytecode | IL/CIL |
| **Archivo principal** | `.class` | `.dll` / `.exe` |
| **Máquina virtual** | JVM | CLR |
| **JIT** | Sí | Sí |
| **Gestión de memoria** | Garbage Collector | Garbage Collector |
| **Plataforma** | Multiplataforma | Multiplataforma |
| **Gestor de dependencias** | Maven / Gradle | NuGet |
| **IDE** | NetBeans, IntelliJ, Eclipse | Visual Studio, Rider |



