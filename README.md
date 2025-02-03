# Desafío - Like Me (Parte I)

Este repositorio contiene el código fuente y los archivos necesarios para completar el **Desafío - Like Me (Parte I)**, que consiste en desarrollar un servidor backend utilizando **Express.js** y **PostgreSQL** para gestionar posts en una red social llamada "Like Me". El servidor debe permitir la creación y consulta de posts, así como la interacción de likes.

## Descripción del Desafío

El desafío consiste en crear un servidor que disponga de las siguientes funcionalidades:

1. **Habilitar CORS**: Utilizar el paquete `cors` para permitir solicitudes desde un cliente React.
2. **Conexión a PostgreSQL**: Usar el paquete `pg` para conectarse e interactuar con una base de datos PostgreSQL.
3. **Ruta GET**: Crear una ruta GET para devolver todos los posts almacenados en la base de datos.
4. **Ruta POST**: Crear una ruta POST para agregar nuevos posts a la base de datos.


## Requisitos Previos

Antes de comenzar, asegúrate de tener instalado lo siguiente:

- [Node.js](https://nodejs.org/) 
- [PostgreSQL](https://www.postgresql.org/) 


## Configuración del Proyecto

### 1. Clonar el Repositorio

Si deseas clonar este repositorio, ejecuta el siguiente comando en tu terminal:

en tu consola escribe:

git clone https://github.com/tu-usuario/like-me-desafio.git
cd like-me-desafio

2. Instalar Dependencias
   
Instala las dependencias necesarias ejecutando:

tu consola:

npm install

3. Configurar la Base de Datos
Crear la Base de Datos: Ejecuta el siguiente comando en tu consola de PostgreSQL (psql) o en una herramienta gráfica como pgAdmin:


CREATE DATABASE likeme;

Crear la Tabla posts: Dentro de la base de datos likeme, crea la tabla posts con el siguiente comando SQL:


CREATE TABLE posts (
    id SERIAL PRIMARY KEY,
    titulo VARCHAR(25),
    img VARCHAR(1000),
    descripcion VARCHAR(255),
    likes INT DEFAULT 0
);

Configurar las Credenciales de la Base de Datos: En el archivo server.js, actualiza las credenciales de la base de datos según tu configuración local:

const pool = new Pool({
    user: "postgres", // Usuario de PostgreSQL
    host: "localhost", // Host de la base de datos
    database: "likeme", // Nombre de la base de datos
    password: "tu-contraseña", // Contraseña de PostgreSQL
    port: 5432, // Puerto de PostgreSQL
});
4. Ejecutar el Servidor
Una vez configurada la base de datos, inicia el servidor con el siguiente comando:

node server.js
El servidor estará disponible en http://localhost:3000.

5. Ejecutar la Aplicación React 
Si deseas probar la aplicación React proporcionada, asegúrate de que el servidor esté en funcionamiento y sigue las instrucciones del archivo README.md dentro de la carpeta de la aplicación React.
