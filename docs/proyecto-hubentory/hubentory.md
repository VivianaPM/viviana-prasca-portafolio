
---

### 🔌 `docs/proyecto-api/index.md`

```markdown
# [Nombre del Proyecto API]

[![GitHub](https://img.shields.io/badge/GitHub-Repositorio-blue?logo=github)](link-al-repositorio)
[![Swagger](https://img.shields.io/badge/Swagger-Documentación-green?logo=swagger)](link-a-swagger)

## El Problema / Objetivo

[Describe qué servicio provee esta API y qué sistemas conecta. Ejemplo: "API RESTful para gestionar usuarios, productos y pedidos de un e-commerce, facilitando la integración con el frontend y sistemas externos."]

## Stack Tecnológico

- **Lenguaje**: Python / Node.js / Java
- **Framework**: FastAPI / Express / Spring Boot
- **Base de Datos**: PostgreSQL / MongoDB / MySQL
- **ORM/ODM**: SQLAlchemy / Mongoose / Hibernate
- **Autenticación**: JWT / OAuth2
- **Contenedores**: Docker
- **Documentación**: Swagger / OpenAPI

## Enfoque Técnico

### Diseño de Base de Datos

[Explica el modelo de datos, las relaciones entre tablas/colecciones y por qué elegiste esa base de datos.]

![Diagrama ER](../../assets/images/api/diagrama-er.png)

*Figura 1: Diagrama Entidad-Relación de la base de datos.*

### Seguridad

[Detalla cómo implementaste la autenticación y autorización.]

- **Autenticación**: JWT con expiración y refresh tokens.
- **Autorización**: Roles y permisos (Admin, User, Guest).
- **Encriptación**: Bcrypt para contraseñas.

### Endpoints Principales

| Método | Endpoint | Descripción | Autenticación |
|--------|----------|-------------|---------------|
| POST | `/api/auth/register` | Registro de nuevo usuario | No |
| POST | `/api/auth/login` | Inicio de sesión | No |
| GET | `/api/users/me` | Obtener perfil del usuario | Sí |
| GET | `/api/products` | Listar productos | Sí |
| POST | `/api/products` | Crear nuevo producto | Sí (Admin) |
| PUT | `/api/products/{id}` | Actualizar producto | Sí (Admin) |
| DELETE | `/api/products/{id}` | Eliminar producto | Sí (Admin) |

### Escalabilidad y Rendimiento

[Explica cómo aseguraste que la API sea eficiente.]

- **Indexación**: Índices en campos de búsqueda frecuente.
- **Caching**: Redis para respuestas frecuentes.
- **Paginación**: Limit y offset en consultas.
- **Rate Limiting**: Límite de peticiones para prevenir abusos.

## Cómo Ejecutar el Proyecto

```bash
# Clonar el repositorio
git clone link-al-repositorio

# Crear y activar entorno virtual (Python)
python -m venv venv
source venv/bin/activate  # En Windows: venv\Scripts\activate

# Instalar dependencias
pip install -r requirements.txt
# o
npm install
# o
mvn install

# Configurar variables de entorno
cp .env.example .env
# Editar .env con tus credenciales

# Ejecutar migraciones (si aplica)
python manage.py migrate
# o
npx prisma migrate deploy

# Levantar la API
python main.py
# o
npm run start
# o
mvn spring-boot:run