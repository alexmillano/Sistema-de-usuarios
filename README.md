# Sistema-de-usuarios

API REST para la gestión de usuarios con autenticación segura mediante JWT. Incluye registro, login y operaciones CRUD completas, con un dashboard en React para interactuar con el sistema.

---

## 📋 Tabla de Contenidos

- Características
- Tecnologías
- Estructura del proyecto
- Instalación y uso
- Variables de entorno
- Endpoints de la API


---

## ✨ Características

- ✅ Registro de usuarios con validación de datos
- ✅ Login con generación de token JWT
- ✅ Rutas protegidas mediante middleware de autenticación
- ✅ CRUD completo de usuarios (crear, leer, actualizar, eliminar)
- ✅ Encriptación de contraseñas con bcrypt
- ✅ Dashboard en React con login y gestión de usuarios

---

## 🛠 Tecnologías

| Capa | Tecnología |
|------|------------|
| Runtime | Node.js 18+ |
| Framework backend | Express.js |
| Base de datos | MySQL 8 |
| Autenticación | JSON Web Tokens (JWT) |
| Encriptación | bcrypt |
| Frontend | React 18 |
| Cliente HTTP | Axios |

---

## 📁 Estructura del proyecto

```
sistema-usuarios/
├── backend/
│   ├── src/
│   │   ├── controllers/
│   │   │   └── user.controller.js
│   │   ├── middlewares/
│   │   │   └── auth.middleware.js
│   │   ├── routes/
│   │   │   ├── auth.routes.js
│   │   │   └── user.routes.js
│   │   ├── config/
│   │   │   └── db.js
│   │   └── app.js
│   ├── .env.example
│   └── package.json
└── frontend/
    ├── src/
    │   ├── components/
    │   ├── pages/
    │   └── App.jsx
    └── package.json
```

---

## 🚀 Instalación y uso

### Pre-requisitos

- Node.js 18+
- MySQL 8+
- npm

### 1. Clonar el repositorio

```bash
git clone https://github.com/Alexmillano/sistema-usuarios.git
cd sistema-usuarios
```

### 2. Configurar el backend

```bash
cd backend
npm install
cp .env.example .env
# Completar las variables en .env
```

### 3. Crear la base de datos

```bash
mysql -u root -p < src/config/database.sql
```

### 4. Iniciar el servidor

```bash
npm run dev
```

El servidor correrá en `http://localhost:3000`

### 5. Configurar y correr el frontend

```bash
cd ../frontend
npm install
npm run dev
```

El cliente correrá en `http://localhost:5173`

---

## 🔐 Variables de entorno

Crear un archivo `.env` en `/backend` basado en `.env.example`:

```env
PORT=3000
DB_HOST=localhost
DB_USER=root
DB_PASSWORD=tu_password
DB_NAME=sistema_usuarios
JWT_SECRET=tu_clave_secreta_jwt
JWT_EXPIRES_IN=24h
```

---

## 📡 Endpoints de la API

### Autenticación

| Método | Endpoint | Descripción | Auth requerida |
|--------|----------|-------------|----------------|
| POST | `/api/auth/register` | Registrar nuevo usuario | ❌ |
| POST | `/api/auth/login` | Iniciar sesión y obtener token | ❌ |

### Usuarios

| Método | Endpoint | Descripción | Auth requerida |
|--------|----------|-------------|----------------|
| GET | `/api/users` | Obtener todos los usuarios | ✅ |
| GET | `/api/users/:id` | Obtener usuario por ID | ✅ |
| PUT | `/api/users/:id` | Actualizar usuario | ✅ |
| DELETE | `/api/users/:id` | Eliminar usuario | ✅ |

