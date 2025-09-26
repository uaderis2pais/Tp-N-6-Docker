## Levantar la API con Docker Compose

1. Abrir una terminal en la raíz del proyecto.
2. Construir y levantar los contenedores:

```bash
docker-compose up --build
```
La API queda disponible en:

http://localhost:3000


Rutas disponibles
Método	        Ruta	        Descripción
GET	            /items	      Obtener todos los items
GET	            /items/:id	  Obtener un item por ID
POST	          /items	      Crear un nuevo item
PUT	            /items/:id	  Actualizar un item por ID
DELETE	        /items/:id	  Eliminar un item por ID


Estructura de la base de datos
Tabla items:

Columna	      Tipo	         Descripción
id	          SERIAL	      ID del item (primary key)
name	        VARCHAR(255)	Nombre del item
description	  TEXT	        Descripción del item
created_at	  TIMESTAMP	    Fecha de creación (default now())


Notas
-La base de datos se persiste gracias al volumen Docker db_data.
-Al levantar el contenedor db por primera vez, se ejecuta el script init.sql para crear la tabla items
