# Ayudantia 3
## Desarrollo Web Santo Tomas


### Trabajo de hoy

**Agenda Telefónica Node.js + MySQL**

Esta guia consiste en crear una  agenda telefónica desarrollado con Node.js y MySQL.

## Crear una nueva carpeta para tu proyecto

```bash
mkdir agenda-telefonica-node-mysql
cd agenda-telefonica-node-mysql
```

### Iniciamos 
```bash
npm init -y
```
### Instalamos dependencias
```bash
npm install express body-parser ejs method-override mysql nodemon --save
````
### Dockerizar
```bash
version: '3.8'

services:
  mysqldb:
    image: mysql:8.0
    restart: unless-stopped
    environment:
      MYSQL_ROOT_PASSWORD: 123456  # Cambia esto por tu contraseña deseada
      MYSQL_DATABASE: lonko_db     # Cambia esto por el nombre de tu base de datos
    ports:
      - "3307:3306"                # Mapeo del puerto de MySQL (host:docke)
    volumes:
      - db-data:/var/lib/mysql     # Volumen para persistir datos de MySQL
    command: --default-authentication-plugin=mysql_native_passwordnpm insta

volumes:
  db-data:
```

### Crear bd en MySQL
```sql
CREATE DATABASE agenda_telefonica;
USE agenda_telefonica;
CREATE TABLE contactos (
    id INT AUTO_INCREMENT PRIMARY KEY,
    nombre VARCHAR(255) NOT NULL,
    telefono VARCHAR(20) NOT NULL
);
```

### Arbol de directorios
```bash
agenda-telefonica-node-mysql/
│
├── views/
│   ├── contactos.ejs
│   ├── editar_contacto.ejs
│   ├── nuevo_contacto.ejs
│   └── index.ejs
│
├── docker-compose.yml
└── package.json
```

