# TodoCamisetas API - Backend en PHP

## Descripción

API RESTful desarrollada en PHP puro para la gestión de camisetas de fútbol y clientes B2B, cumpliendo los requisitos de la empresa TodoCamisetas. Permite CRUD de camisetas, clientes y tallas, así como la obtención dinámica de precios finales según reglas de negocio.

---

## Estructura del Proyecto

```
/public/index.php           # Punto de entrada de la API
/routes/routes.php          # Enrutamiento de las solicitudes
/controllers/               # Lógica de negocio (controladores)
    CamisetaController.php
    ClienteController.php
    TallaController.php
/models/                    # Acceso a datos (modelos)
    Camiseta.php
    Cliente.php
    Talla.php
/config/database.php        # Conexión a la base de datos
/todocamisetas.sql          # Script para crear la base de datos y tablas
/README.md                  # Este archivo
```

---

## Endpoints Principales

### Camisetas

- `GET /camisetas`  
  Lista todas las camisetas.

- `GET /camisetas/{id}`  
  Muestra una camiseta por ID.

- `POST /camisetas`  
  Crea una nueva camiseta.

- `PUT /camisetas/{id}`  
  Actualiza una camiseta existente.

- `DELETE /camisetas/{id}`  
  Elimina una camiseta.

- `GET /camisetas/{id}/precio/cliente/{cliente_id}`  
  Devuelve el precio final de una camiseta para un cliente específico.

### Clientes

- `GET /clientes`
- `GET /clientes/{id}`
- `POST /clientes`
- `PUT /clientes/{id}`
- `DELETE /clientes/{id}`

### Tallas

- `GET /tallas`
- `POST /tallas`
- `PUT /tallas/{id}`
- `DELETE /tallas/{id}`

---

## Reglas de Negocio

- El precio final de una camiseta depende de la categoría del cliente y si existe una oferta.
- No se puede eliminar un cliente si tiene camisetas asociadas.
- Relación muchos a muchos entre camisetas y tallas.

---

## Instalación y Uso

1. Clona el repositorio en tu servidor local.
2. Crea la base de datos usando el archivo `todocamisetas.sql`.
3. Configura los datos de conexión en `/config/database.php`.
4. Inicia el servidor PHP:
   ```
   php -S localhost:8000 -t public
   ```
5. Prueba los endpoints usando Postman o similar.

---

## Autores

- Matías López
- Camila Fuentes

---

## Licencia

MIT
