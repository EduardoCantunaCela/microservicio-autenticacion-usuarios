# Microservicio de Gestión de Usuarios  
### Autenticación basada en Tokens con Laravel Sanctum

## 👥 Grupo 4 — Integrantes
- Sandy Mariño  
- Jonathan Hernández  
- Marco Chacón  
- Carlos Fernández  
- Carlos Cantuña
- Sergio Condo  

---

## 🎯 Objetivo del Proyecto
Implementar un microservicio de **autenticación y gestión de usuarios** utilizando **Laravel Sanctum**, permitiendo emitir y validar **API Tokens** para proteger otros microservicios dentro del sistema.

Cada usuario posee un **perfil** que determina su nivel de acceso:

- `administrador`
- `editor`
- `usuario`

Este microservicio será consumido por otros módulos del sistema para validar permisos y autenticar solicitudes.

---

## 🛠️ Tecnologías Utilizadas
- **Laravel 11.x**
- **Laravel Sanctum** (API Tokens)
- **MySQL** + phpMyAdmin
- **Postman / Thunder Client**
- **Git & GitHub**

---

## 🗄️ Estructura Final de la Tabla `users`

| Campo             | Tipo                                                    | Descripción                   |
|-------------------|---------------------------------------------------------|-------------------------------|
| `id`              | BIGINT UNSIGNED (PK)                                    | Identificador del usuario     |
| `name`            | VARCHAR(255)                                            | Nombre del usuario            |
| `email`           | VARCHAR(255) UNIQUE                                     | Correo electrónico            |
| `email_verified_at` | TIMESTAMP NULL                                        | Fecha de verificación         |
| `password`        | VARCHAR(255)                                            | Contraseña en hash            |
| `perfil`          | ENUM('administrador','editor','usuario') DEFAULT 'usuario' | Rol del usuario          |
| `remember_token`  | VARCHAR(100) NULL                                       | Token de sesión               |
| `created_at`      | TIMESTAMP NULL                                          | Fecha de creación             |
| `updated_at`      | TIMESTAMP NULL                                          | Fecha de actualización        |

---

## 📦 Instalación del Proyecto

### 1. Clonar el repositorio
```bash
git clone https://github.com/TU-USUARIO/microservicio-autenticacion-usuarios.git
cd microservicio-autenticacion-usuarios

---

### 2. Instalar dependencias
composer install

### 3. Configurar archivo .env
cp .env.example .env

### Configurar conexión a MySQL:
DB_DATABASE=usuarios
DB_USERNAME=root
DB_PASSWORD=

### 4. Generar APP_KEY
php artisan key:generate

### 5. Ejecutar migraciones
php artisan migrate

---

## 📦 Instalación del Proyecto
Registro
POST /api/register

Inicio de sesión
POST /api/login

Cerrar sesión
POST /api/logout

Obtener usuario autenticado
GET /api/user


(Dependen del controlador implementado por el equipo.)

📘 Descripción General

Este microservicio permite:

Registrar usuarios

Generar tokens de autenticación

Validar tokens desde otros microservicios

Asignar y verificar roles (perfil)

Administrar sesiones mediante Laravel Sanctum

Actúa como autoridad central de autenticación dentro de una arquitectura basada en microservicios.
