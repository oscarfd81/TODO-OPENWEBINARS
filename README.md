# 📋 Fullstack Path: API REST con Spring Boot (Práctica OpenWebinars)

Este repositorio contiene el proyecto práctico central del curso **"Desarrollo de una aplicación web con Spring Boot"** impartido por **OpenWebinars**. A través de esta implementación, se han aplicado conceptos avanzados de persistencia, seguridad y diseño de APIs RESTful.

---

## 🎯 Objetivo del Proyecto
Desarrollar un sistema de backend robusto para una **To-Do List** (Gestión de Tareas) que no solo permita el almacenamiento de información, sino que garantice la integridad y privacidad de los datos mediante lógica de negocio y seguridad por usuario.

---

## 🚀 Funcionalidades Desarrolladas

### 🔹 Gestión de Tareas (CRUD)
* **Persistencia Automatizada:** Uso de `@GeneratedValue` con secuencias para un control preciso de IDs.
* **Operaciones Completas:***
     * Crear nuevas tareas.
    * Editar detalles de tareas existentes.
    * Borrado físico de registros.
    * Listado total y búsqueda filtrada por ID.

### 🔹 Gestión de Usuarios
* **Registro de Cuentas:** Endpoint dedicado para dar de alta nuevos usuarios en el sistema.
* **Autenticación:** Implementación de seguridad para restringir el acceso a usuarios no autorizados.

---

## 🔐 Lógica de Seguridad Aplicada (Owner-Based Access)

La parte más avanzada de esta práctica se centra en que la API es "consciente" de quién la está usando. Se ha implementado **Method Security** para asegurar que:

* **Aislamiento de Datos:** Un usuario **solo** puede ver las tareas que él mismo ha creado.
* **Protección de Acciones:** Si un usuario intenta editar o borrar una tarea mediante un ID que no le pertenece, el sistema intercepta la petición y lanza una excepción de seguridad.
* **Control de Autoría:** Cada tarea queda vinculada automáticamente al `username` del autor en el momento de la creación.

> **Tecnologías clave:** `@PreAuthorize`, `@PostAuthorize` y comprobación de `authentication.principal`.

---

## 🛠️ Stack Tecnológico

* **Framework:** Spring Boot 3+
* **Seguridad:** Spring Security (Basic Auth & Method Security)
* **Base de Datos:** H2 Database (Runtime)
* **Persistencia:** Spring Data JPA / Hibernate
* **Herramientas de Test:** Postman

---

## 📖 Aprendizajes Clave del Curso
Durante el desarrollo de esta práctica en OpenWebinars, se han consolidado los siguientes conocimientos:
1.  Configuración de **Spring Security** para aplicaciones desacopladas.
2.  Manejo de **CORS** para futuras conexiones con Frontend (Angular/React).
3.  Uso de **SQL Scripts (`import.sql`)** sincronizados con secuencias de JPA.
4.  Validación de **propiedad de recursos** a nivel de controlador.

---

## ⚙️ Ejecución Local

1. Clonar el repositorio.
2. Configurar el puerto en `application.properties` (por defecto `9090`).
3. Ejecutar `./mvnw spring-boot:run`.
4. Acceder a la consola H2 para verificar tablas en `/h2-console`.

---
*Proyecto realizado como parte de la formación continua en la plataforma OpenWebinars.*
