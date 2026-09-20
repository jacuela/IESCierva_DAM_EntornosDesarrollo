- [7. Herramientas de Apoyo al Desarrollo de Software](#7-herramientas-de-apoyo-al-desarrollo-de-software)
  - [7.1. Herramientas de Desarrollo](#71-herramientas-de-desarrollo)
  - [7.2. Herramientas CASE (Computer Aided Software Engineering)](#72-herramientas-case-computer-aided-software-engineering)
    - [7.2.1. Funcionalidad](#721-funcionalidad)
    - [7.2.2. Clasificación según fases](#722-clasificación-según-fases)
  - [7.3. Entornos de Desarrollo Integrado (IDE)](#73-entornos-de-desarrollo-integrado-ide)
  - [7.4. Control de Versiones: Git](#74-control-de-versiones-git)
  - [7.5. Contenedores: Docker](#75-contenedores-docker)


# 7. Herramientas de Apoyo al Desarrollo de Software

> 💡 **Punto de partida:** ¿Alguna vez te has preguntado cómo un programador puede crear una aplicación completa sin escribir todo el código desde cero? ¿O cómo se gestiona el trabajo en equipo cuando 10 personas modifican el mismo proyecto? La respuesta está en las herramientas de apoyo.

> 💡 **¿Por qué me importa?**
> Porque sin las herramientas adecuadas, desarrollar es como construir una casa con las manos. Un IDE como Rider te ahorra horas, Git te salva de errores catastróficos, y Docker evita el "funciona en mi máquina". Son tus herramientas de trabajo diario.
> 

**Objetivos de aprendizaje:**

- Conocer las herramientas principales del desarrollo de software
- Entender qué son las herramientas CASE y para qué sirven
- Diferenciar entre editores simples e IDEs
- Saber elegir la herramienta adecuada según el contexto

## 7.1. Herramientas de Desarrollo

En la práctica, para llevar a cabo varias de las etapas del desarrollo de software, se utilizan **herramientas informáticas**. Su finalidad principal es automatizar las tareas y ganar fiabilidad y tiempo. Esto permite a los desarrolladores centrarse en los requerimientos del sistema y el análisis, que son las causas principales de los fallos del software. 

> 💡 **Analogía:** Las herramientas de desarrollo son como los instrumentos de un mecánico. Puedes cambiar una rueda con una llave inglesa básica, pero con las herramientas adecuadas el trabajo es más rápido, seguro y profesional.

**Categorías de herramientas:**

| Categoría | Herramientas populares | Función |
|-----------|----------------------|---------|
| **IDEs** | Visual Studio Code, Visual Studio, IntelliJ | Escribir código |
| **Depuradores** | Visual Studio Debugger, Chrome DevTools | Encontrar errores |
| **Control de versiones** | Git, SVN, Mercurial | Gestionar cambios |
| **Gestores de paquetes** | NuGet, npm, maven, gradle | Instalar librerías |
| **Testing** | JUnit, pytest, Jest | Verificar código |


## 7.2. Herramientas CASE (Computer Aided Software Engineering)

Las **herramientas CASE** son un conjunto de aplicaciones que se utilizan en el desarrollo de software con el objetivo de reducir costes y tiempo del proceso, mejorando la productividad.

> 💡 **Nota:** CASE significa "Ingeniería de Software Asistida por Computadora", como CAD (Diseño Asistido por Computadora) pero para software.

### 7.2.1. Funcionalidad

- **Automatización de tareas repetitivas** en análisis, diseño y codificación
- **Generación automática de código** a partir de modelos
- **Creación de diagramas** (UML, ER, flujo)
- **Validación de requisitos** y consistencia
- **Documentación automática** del proyecto
- **Gestión de la configuración** del software

### 7.2.2. Clasificación según fases

Las herramientas CASE se clasifican según las fases del ciclo de vida en las que trabajan:

| Tipo | Fases | Ejemplos |
|------|-------|----------|
| **U-CASE** (Upper) | Planificación, Análisis | StarUML, Enterprise Architect |
| **M-CASE** (Middle) | Análisis, Diseño | Rational Rose, Visual Paradigm |
| **L-CASE** (Lower) | Codificación, Pruebas | Visual Studio, IDEs con generación de código |

**Herramientas CASE gratuitas/libres:**
- **ArgoUML:** http://argouml.tigris.org/ - Herramienta UML open source
- **Dia:** http://dia-installer.de/ - Diagramas diversos
- **StarUML:** https://staruml.io/ - UML con versión gratuita
- **PlantUML:** https://plantuml.com/ - UML mediante texto

Herramientas modernas: PlantUML (diagramas UML desde texto), Draw.io/diagrams.net (diagramas arrastrando), Mermaid (diagramas en Markdown).

> 📝 **Nota:** En ciclos de desarrollo, las herramientas CASE se usan especialmente en las fases de análisis y diseño para crear diagramas UML que documenten el sistema antes de programar.

## 7.3. Entornos de Desarrollo Integrado (IDE)

Un **Entorno de Desarrollo Integrado (IDE)** es una herramienta que facilita y posibilita el desarrollo de software. Agrupa diversas herramientas de desarrollo (editor de código, compilador, depurador) en una única interfaz gráfica para aumentar la productividad del programador.

**Componentes de un IDE:**

| Componente | Descripción | Ejemplo |
|------------|-------------|---------|
| **Editor avanzado** | Resaltado, sangrado, navegación | IntelliSense, snippets |
| **Compilador integrado** | Traducir sin salir del IDE | Build, Compile |
| **Depurador visual** | Puntos de ruptura, inspección | Breakpoints, watch |
| **Autocompletado** | Sugerencias de código | IntelliSense |
| **Refactorización** | Renombrar, extraer métodos | Rename, Extract |
| **Gestor de proyectos** | Organizar archivos | Solution Explorer |
| **Control de versiones** | Git integrado | Git panel |

**IDEs populares por lenguaje:**

| Lenguaje | IDE principal | Alternativas |
|----------|--------------|--------------|
| **C#** | JetBrains Rider | Visual Studio Code, Visual Studio |
| **Java** | IntelliJ IDEA | Eclipse, NetBeans |
| **Python** | PyCharm | VS Code, Spyder |
| **C/C++** | CLion | Visual Studio, VS Code |
| **JavaScript** | WebStorm | VS Code, Atom |
| **General** | Visual Studio Code | Sublime, Vim |


Visual Studio Code es un IDE que nativamente soporta HTML, CSS, PHP, es decir, programación web. Pero por medio de extensiones, es capaz de soportar otros lenguajes, como Java. 


> 💡 **Dato:** El primer IDE fue "Eclipse" (1999), desarrollado por IBM para Java. Antes, los programadores editaban archivos de texto en terminals y compilaban manualmente.

**Comparativa: Editor vs IDE**

| Característica | Editor simple | IDE |
|----------------|---------------|-----|
| Peso | Ligero | Pesado |
| Velocidad | Rápido | Más lento |
| Configuración | Manual | Viene todo integrado |
| Depuración | Externa | Integrada |
| Autocompletado | Básico | Avanzado |
| Ejemplos | VS Code, Vim | Rider, IntelliJ |
| Mejor para | Scripts, pequeños proyectos | Proyectos grandes |

**¿Cuándo usar cada uno?**
- **Editor (VS Code)**: Scripts, proyectos pequeños, rápido para abrir y editar archivos sueltos, cuando trabajas con múltiples lenguajes.
- **IDE (Rider, Visual Studio)**: Proyectos grandes de C#/Java, cuando necesitas depuración avanzada, refactorización automática, y herramientas integradas.

---

## 7.4. Control de Versiones: Git

**Git** es la herramienta de control de versiones más utilizada en el mundo. Permite registrar los cambios realizados en archivos a lo largo del tiempo, de modo que puedas recuperar versiones anteriores y trabajar en equipo sin pisarte los unos a los otros.

> 💡 **Analogía:** Git es como el "Historial" de Google Docs, pero mucho más potente. Cada "guardado" (commit) es una fotografía de tu proyecto en ese momento. Si algo se rompe, puedes volver a la foto anterior.

**Conceptos básicos de Git:**

| Concepto | Descripción |
|----------|-------------|
| **Repositorio (repo)** | Carpeta que Git está vigilando. Contiene todo el historial de cambios |
| **Commit** | Una "foto" del proyecto en un momento dado. Cada commit tiene un mensaje que describe qué cambió |
| **Rama (branch)** | Una línea de desarrollo paralela. Puedes crear ramas para experimentar sin afectar al código principal |
| **Merge** | Unir dos ramas en una. Git intenta fusionar los cambios automáticamente |
| **Push/Pull** | Subir (push) o bajar (pull) cambios a/from un repositorio remoto (GitHub, GitLab) |

**Comandos básicos:**

```bash
git init                    # Crear un repositorio nuevo
git add .                   # Preparar todos los cambios
git commit -m "mensaje"     # Guardar una foto del proyecto
git push                    # Subir a GitHub/GitLab
git pull                    # Bajar cambios del repositorio
git log --oneline           # Ver historial de commits
git branch feature/nombre   # Crear una rama
git checkout feature/nombre # Cambiar a esa rama
git merge feature/nombre    # Fusionar la rama con la actual
```

**Convención de mensajes de commit:**
```
[tipo] Descripción corta

Tipos: feat (nueva función), fix (corrección), docs (documentación),
refactor (reestructurar), test (añadir test), chore (mantenimiento)

Ejemplos:
[feat] Añadir carrito de compras
[fix] Corregir login con emails mayúsculas
[docs] Actualizar guía de instalación
[test] Añadir tests para servicio de pagos
```

Esta convención facilita la generación automática de changelogs y la búsqueda en el historial.


> 📝 **Nota:** Se debería usar Git en todos los proyectos. Es una habilidad fundamental en cualquier empresa de software. GitHub y GitLab son las plataformas más populares para alojar repositorios remotos.

## 7.5. Contenedores: Docker

**Docker** es una plataforma que permite empaquetar una aplicación junto con todas sus dependencias (librerías, configuraciones, bases de datos) en un "contenedor" que se ejecuta de forma idéntica en cualquier ordenador.

> 💡 **Analogía:** Docker es como una "caja de embalar" para software. Metes tu aplicación con todo lo que necesita dentro de la caja, y esa caja funciona igual en tu portátil, en el servidor de la empresa o en la nube. El problema clásico "en mi ordenador funciona" desaparece.

**Conceptos clave:**

| Concepto | Descripción |
|----------|-------------|
| **Contenedor** | Instancia aislada de una aplicación con todo su entorno |
| **Imagen** | Plantilla de solo lectura que define el contenedor (como un "molde") |
| **Dockerfile** | Archivo de texto con instrucciones para crear la imagen |
| **Docker Hub** | Repositorio público de imágenes (como GitHub pero para contenedores) |

**¿Por qué Docker en desarrollo?**

- **Reproducibilidad**: Todo el equipo trabaja con el mismo entorno
- **Aislamiento**: Cada servicio (app, base de datos, caché) corre en su propio contenedor
- **Portabilidad**: Funciona igual en Windows, Linux y Mac
- **Rapidez**: Frente a los tradicionales software de virtualización de sistemas operativos (VirtualBox), los contenedores arrancan en segundos, no en minutos como una máquina virtual

> 📝 **Ejemplo:** Usar Docker para levantar la base de datos (SQL Server, PostgreSQL) sin instalarla en tu ordenador.

**Ejemplo de Dockerfile para app C#:**
```dockerfile
FROM mcr.microsoft.com/dotnet/sdk:10.0
WORKDIR /app
COPY . .
RUN dotnet publish -c Release -o out
FROM mcr.microsoft.com/dotnet/aspnet:10.0
WORKDIR /app
COPY --from=0 /app/out .
ENTRYPOINT ["dotnet", "MiApp.dll"]
```

Este Dockerfile: (1) usa la imagen de SDK para compilar, (2) compila la app en modo Release, (3) usa una imagen ligera solo con el runtime para ejecutar, (4) copia el ejecutable compilado, (5) define el punto de entrada.

**docker-compose.yml para app + base de datos:**
```yaml
version: '3.8'
services:
  app:
    build: .
    ports:
      - "5000:80"
    depends_on:
      - db
  db:
    image: postgres:16
    environment:
      POSTGRES_PASSWORD: secret
    ports:
      - "5432:5432"
```

Con `docker-compose up` levantas la app y la base de datos simultáneamente. Cada servicio corre en su propio contenedor aislado.

---
