# Microservicio de Productos - FullStack3

## Descripción
Este proyecto corresponde a un microservicio desarrollado con **Spring Boot** para la gestión de productos.  
Permite realizar operaciones CRUD sobre la entidad `PRODUCTO`.

Este microservicio forma parte de una arquitectura basada en microservicios, donde el módulo de productos funciona de manera independiente y se conecta a una base de datos **Oracle**.

---

## Tecnologías utilizadas

- Java
- Spring Boot
- Spring Web
- Spring Data JPA
- Oracle Database
- Maven

---

## Funcionalidades

El microservicio permite:

- Listar todos los productos
- Buscar un producto por su ID
- Crear un nuevo producto
- Actualizar un producto existente
- Eliminar un producto

---

## Estructura del proyecto

El proyecto está organizado en capas:

- **controller**: expone los endpoints REST
- **service**: define la lógica de negocio
- **repository**: acceso a datos con JPA
- **model**: entidades del sistema
- **main**: clase principal para levantar la aplicación

---

## Entidad principal

### Producto
La entidad `Producto` contiene los siguientes campos:

- `id`
- `nombre`
- `descripcion`
- `precio`
- `stock`

Además, cuenta con validaciones como:

- campos obligatorios
- longitud mínima y máxima
- precio mayor a 0
- stock no negativo

---

## Endpoints disponibles

### 1. Listar productos
**GET** `/api/productos`

Obtiene la lista de todos los productos registrados.

---

### 2. Buscar producto por ID
**GET** `/api/productos/{id}`

Obtiene un producto específico según su identificador.

---

### 3. Crear producto
**POST** `/api/producto`

Crea un nuevo producto en la base de datos.

#### Ejemplo de body:
```json
{
  "nombre": "Mouse Gamer",
  "descripcion": "Mouse RGB 7200 DPI",
  "precio": 19990,
  "stock": 10
}

---

### 4. Actualizar producto
**PUT** `/api/productos/{id}`

Actualiza la información de un producto existente

#### Ejemplo de body:
```json
{
  "nombre": "Mouse Gamer",
  "descripcion": "Mouse RGB 7200 DPI",
  "precio": 19990,
  "stock": 15
}

---

### 5. Eliminar producto
**DELETE** `/api/productos/{id}`

Elimina un producto de la base de datos

---
