# Microservicio de Usuarios - FullStack3

## Descripción
Este proyecto corresponde a un microservicio desarrollado con **Spring Boot** para la gestión de usuarios.  
Permite realizar operaciones CRUD sobre la entidad `Usuario` y además incorpora un endpoint de login para validar credenciales.

Este microservicio forma parte de una arquitectura basada en microservicios, donde el módulo de usuarios funciona de manera independiente y se conecta a una base de datos **Oracle**.

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

- Listar todos los usuarios
- Buscar un usuario por su ID
- Crear un nuevo usuario
- Actualizar un usuario existente
- Eliminar un usuario
- Validar login mediante correo y contraseña

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

### Usuario
La entidad `Usuario` contiene los siguientes campos:

- `id`
- `nombre`
- `apaterno`
- `amaterno`
- `correo`
- `password`
- `rol`

Además, cuenta con validaciones como:

- campos obligatorios
- validación de correo
- longitud mínima y máxima
- restricción de rol

---

## Endpoints disponibles

### 1. Listar usuarios
**GET** `/api/usuarios`

Obtiene la lista de todos los usuarios registrados.

---

### 2. Buscar usuario por ID
**GET** `/api/usuarios/{id}`

Obtiene un usuario específico según su identificador.

---

### 3. Crear usuario
**POST** `/api/usuarios`

Crea un nuevo usuario en la base de datos.

#### Ejemplo de body:
```json
{
  "nombre": "Pedro",
  "apaterno": "Soto",
  "amaterno": "Ramirez",
  "correo": "psoto@tienda.cl",
  "password": "1234",
  "rol": "CLIENTE"
}

