# Zona Fit (Sistema de Gimnasio)

Este proyecto es una aplicación de escritorio para la gestión de clientes de un gimnasio llamado "Zona Fit". La aplicación permite realizar operaciones CRUD (Crear, Leer, Actualizar, Eliminar) sobre los clientes.

El sistema está desarrollado en Java utilizando el framework **Spring Boot** para la lógica de negocio y la persistencia de datos, y **Java Swing** para la interfaz gráfica de usuario.

## Características

  * Listar todos los clientes registrados.
  * Agregar nuevos clientes (Nombre, Apellido, Membresía).
  * Modificar la información de un cliente existente.
  * Eliminar un cliente de la base de datos.

## Tecnologías Utilizadas 🛠️

  * **Java 21**
  * **Spring Boot 3.5.6**:
      * Spring Data JPA (para la persistencia de datos).
      * Spring Context (para la inyección de dependencias).
  * **Java Swing**: Para la interfaz gráfica de usuario.
  * **FlatLaf (Dark)**: Una biblioteca para dar un aspecto moderno ("look and feel" oscuro) a la interfaz Swing.
  * **MySQL**: Como motor de base de datos.
  * **Lombok**: Para reducir el código repetitivo en las clases modelo.
  * **Maven**: Como gestor de dependencias y construcción del proyecto.

## Configuración y Ejecución 🚀

### Prerrequisitos

1.  **JDK 21** o superior instalado.
2.  **MySQL Server** instalado y en ejecución.
3.  Un IDE de Java (como IntelliJ IDEA o VSCode con extensiones de Java) o **Maven** en la línea de comandos.

### 1\. Configuración de la Base de Datos

El proyecto espera conectarse a una base de datos MySQL.

1.  Asegúrate de que tu servidor MySQL esté corriendo (normalmente en el puerto `3306`).

2.  Crea una base de datos llamada `zona_fit_db`:

    ```sql
    CREATE DATABASE zona_fit_db;
    ```

3.  El proyecto está configurado para que Spring Data JPA cree automáticamente la tabla `cliente` la primera vez. Si prefieres crearla manualmente, puedes usar:

    ```sql
    USE zona_fit_db;

    CREATE TABLE cliente (
        id INT NOT NULL AUTO_INCREMENT,
        nombre VARCHAR(255),
        apellido VARCHAR(255),
        membresia INT,
        PRIMARY KEY (id)
    );
    ```

4.  Verifica las credenciales de la base de datos en el archivo `src/main/resources/application.properties`. Por defecto, son:

      * **Usuario**: `root`
      * **Contraseña**: `admin`

    Si tus credenciales son diferentes, actualiza este archivo:

    ```properties
    spring.datasource.url=jdbc:mysql://localhost:3306/zona_fit_db
    spring.datasource.username=TU_USUARIO_ROOT
    spring.datasource.password=TU_CONTRASENA
    ```

### 2\. Ejecución de la Aplicación

La aplicación es una aplicación de escritorio Swing (no una aplicación web). El punto de entrada principal es la clase `ZonaFitSwing.java`.

Para ejecutar el proyecto:

1.  Abre el proyecto en tu IDE preferido (IntelliJ, Eclipse, VSCode).
2.  Espera a que Maven descargue todas las dependencias (listadas en `pom.xml`).
3.  Localiza el archivo `src/main/java/gm/zona_fit/ZonaFitSwing.java`.
4.  Ejecuta el método `main` de esta clase.

Esto iniciará la aplicación Spring y abrirá la ventana principal de la interfaz gráfica para la gestión de clientes.
