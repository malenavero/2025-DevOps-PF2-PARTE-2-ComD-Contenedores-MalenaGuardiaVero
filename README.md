# 2025-DevOps-PF2-PARTE-2-ComD-Contenedores-MalenaGuardiaVero

## Parte 2 - Dockerización de un proyecto existente

### 1. Creación del Repositorio

Se siguieron estos pasos para iniciar el repositorio:

1. Crear un nuevo repositorio en GitHub.
2. Clonar el repositorio en la máquina local.
3. Generar el archivo `README.md`:
    ```bash
    echo "# 2025-DevOps-PF2-PARTE-2-ComD-Contenedores-MalenaGuardiaVero" >> README.md
    ```
4. Realizar el primer commit y subirlo a la rama principal (la renombré como `main`):
    ```bash
    git add .
    git commit -m "primer commit"
    git branch -M main
    git push origin main
    ```

### 2. Incorporación del Proyecto

Se agregó al repositorio el proyecto realizado previamente en la materia de Backend: **Huellitas Felices**, una aplicación de gestión para veterinarias desarrollada en Node.js y MongoDB (Mongoose).

### 3. Contenerización con Docker

En el proyecto original, la base de datos estaba alojada en MongoDB Atlas (nube), por lo que no fue necesario crear un contenedor para la base de datos local.

El contenedor de Docker únicamente incluye la aplicación Node.js, la cual se conecta directamente a MongoDB Atlas mediante la URI definida en el archivo .env. Esto permite desplegar fácilmente la aplicación en cualquier entorno sin modificar la configuración de la base de datos.

Por cuestiones de seguridad, el archivo .env no será subido al repositorio, pero se adjunta en la entrega.

### 4. Comando para Ejecutar el Proyecto

Para levantar la aplicación utilizando Docker Compose, ejecutar:

```bash
docker-compose up --build
```

El puerto de host utilizado es el **3000**.

### 5. Acceso a la Aplicación

Una vez levantado el contenedor, acceder desde el navegador a:

[http://localhost:3000](http://localhost:3000)

### 6. Comando utiles de Docker
**_Levantar la app y construir la imagen_**
```bash
docker-compose up --build
```

**_Ver logs del contenedor_**
```bash
docker-compose logs -f
```

**_Parar los contenedores_**
```bash
docker-compose down
```

**_Listar contenedores activos_**
```bash
docker ps
```
 ## 7. Crear un servicio en Render

 Para esta instancia los pasos que realice son:
 1) En render.com cree un nuevo servicio
 2) Lo conecte con el repositorio del proyecto
 3) Seleccione Environment: Docker
 4) Deje el puerto preselecionado: 3000
 5) Cree las variables de ambiente necesarias.



**Deploy:** [https://huellitas-felices-dockerizado.onrender.com](https://huellitas-felices-dockerizado.onrender.com)

### Usuarios de Prueba

| Email                          | Contraseña | Rol         |
|-------------------------------|------------|-------------|
| emanuel@huellitasfelices.com  | 12345      | Gerencia    |
| admin@huellitasfelices.com    | 12345      | Admin       |
| gonzalo@huellitasfelices.com  | 12345      | Ventas      |
| susana@huellitasfelices.com   | 12345      | Peluquería  |
| paula@huellitasfelices.com    | 12345      | Clínica     |
| cristian@huellitasfelices.com | 12345      | Recepción   |

---
# README ORIGINAL DEL PROYECTO

## Huellitas Felices 🐾

**Huellitas Felices** es una aplicación web para la gestión integral de una veterinaria y peluquería canina. Permite organizar servicios, turnos, stock y clientes, con autenticación y autorización de usuarios.

### Funcionalidades Destacadas

- Autenticación y autorización de usuarios por rol.
- CRUD de productos y control de stock.
- Gestión de mascotas y dueños.
- Agenda de turnos para servicios.
- Buscador de mascotas.
- Vistas dinámicas con Pug.
- Documentación interactiva de la API con Swagger.
- Pruebas automatizadas y manuales con Postman.
- Middlewares personalizados y manejo de errores.
- Flujo de ventas y gestión de carrito.

### Tecnologías Utilizadas

- **Node.js**, **Express.js**, **JavaScript**
- **MongoDB Atlas** (con Mongoose)
- **Pug** (plantillas)
- **Postman**, **Swagger**
- **Nodemon** (desarrollo)

### Estructura del Proyecto

```
huellitasFelices/
├─ bin/
├─ controllers/
├─ data/
├─ middlewares/
├─ models/
├─ postmanCollections/
├─ public/
├─ routes/
├─ scripts/
├─ services/
├─ tests/
├─ utils/
├─ views/
├─ .gitignore
├─ app.js
├─ db.js
├─ eslint.config.mjs
├─ initDataFiles.js
├─ package-lock.json
├─ package.json
└─ swagger.js
```

### Documentación y Acceso

- **Producción:** [https://huellitas-felices.onrender.com](https://huellitas-felices.onrender.com)
- **Swagger Docs:** [https://huellitas-felices.onrender.com/docs](https://huellitas-felices.onrender.com/docs)

### Usuarios de Prueba

| Email                          | Contraseña | Rol         |
|-------------------------------|------------|-------------|
| emanuel@huellitasfelices.com  | 12345      | Gerencia    |
| admin@huellitasfelices.com    | 12345      | Admin       |
| gonzalo@huellitasfelices.com  | 12345      | Ventas      |
| susana@huellitasfelices.com   | 12345      | Peluquería  |
| paula@huellitasfelices.com    | 12345      | Clínica     |
| cristian@huellitasfelices.com | 12345      | Recepción   |

---

### Autores

- Cicchini, Josefina
- Cohen, Rosana
- Cruz Guantay, Francisco Agustin
- Guardia Vero, Malena
