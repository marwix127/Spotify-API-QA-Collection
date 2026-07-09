# 🎯 Estrategia de Cobertura de Pruebas

La colección está organizada en 5 flujos clave que cubren las funcionalidades críticas de la API:

## Estructura de la colección

### 01 - Autenticación y Setup
Gestiona los escenarios de autenticación y configuración inicial. Incluye flujos válidos de registro e inicio de sesión, así como casos de prueba negativos: registrar un usuario duplicado, registrar con datos inválidos e intentar iniciar sesión con credenciales incorrectas.

### 02 - Funcionalidad Básica
Valida las operaciones básicas de lectura y escritura para las entidades principales del catálogo: agregar y obtener Álbumes y Canciones.

### 03 - Flujo CRUD Artistas
Cubre el ciclo de vida CRUD completo para Artistas: crear un nuevo artista, listar todos los artistas, obtener un artista específico por ID y actualizar un artista existente.

### 04 - Flujo de Integración Playlists
Prueba el flujo de integración completo de playlists: crear una playlist, listar todas las playlists, obtener una playlist por ID, agregar una canción a una playlist y eliminar una canción de una playlist.

### 05 - Limpieza
Realiza la limpieza del entorno después de las pruebas eliminando la playlist creada durante el flujo de integración, asegurando que el entorno quede restablecido entre ejecuciones.


## 🔑 Habilidades de QA

- **Flow Testing (Pruebas Encadenadas):** Uso de variables de entorno para pasar datos dinámicos (`ID` recién creado o `Token`) entre requests.

- **Testing Negativo:** Validación de endpoints con datos incorrectos o nulos (ej. `GET` con ID inexistente, `POST` sin autenticación) para confirmar el manejo de errores (`400`, `404`).

- **Validación de Esquema Avanzada:** Assertions personalizadas para validar que los IDs sean `number` (Int de Prisma) y que los campos opcionales (`bio`, `image`) manejen correctamente el valor `null`.

- **Gestión de Entornos:** Configuración de `base_url` y manejo seguro del token de autenticación (`Bearer`).

---

## ⚙️ Guía de Instalación y Ejecución

Para ejecutar esta suite de pruebas, necesitarás Postman instalado y tu "Spotify API" ejecutándose localmente.

### 1. Requisitos Previos

1. Tener instalada la aplicación Postman.
2. Tener el backend de la API (ver repositorio relacionado: https://github.com/marwix127/spotify-api levantado y accesible (ej. en `http://localhost:3000`).

### 2. Importación

1. Descarga los archivos `Spotify API QA Automation.postman_collection.json` y `Spotify API QA.postman_environment.json` de este repositorio.
2. En Postman, haz clic en **"Import"**.
3. Selecciona ambos archivos JSON.

### 3. Configuración del Entorno

1. En el menú desplegable de Entornos de Postman, selecciona `Spotify API QA`.
2. Ve a la gestión de Entornos y actualiza la variable `base_url` si es necesario (ej. `http://localhost:3000`).
3. Asegúrate de que la variable `admin_token` no esté vacía (se llenará automáticamente al correr el `POST /login`).

### 4. Ejecución de la Suite

1. Haz clic en el icono **Runner** en la parte inferior de Postman.
2. Arrastra y suelta toda la colección al Runner.
3. Asegúrate de seleccionar el entorno correcto y presiona **"Run"**.

---

## 🟢 DEMOSTRACIÓN VISUAL

<img width="1091" height="966" alt="image" src="https://github.com/user-attachments/assets/a6f70028-d875-46a1-8ff3-f8fbb3aba8e4" />

