# BackJs_ET - User Service

Microservicio desarrollado en Node.js para la gestión de usuarios.

## Tecnologías

* Node.js 18
* Express
* MySQL
* Docker
* Amazon ECS Fargate
* Amazon ECR
* GitHub Actions

## Funcionalidades

* Registro de usuarios
* Consulta de usuarios
* Eliminación de usuarios
* Persistencia en MySQL

## Configuración

Variables de entorno:

```env
DB_HOST=
DB_PORT=3306
DB_USER=
DB_PASSWORD=
DB_NAME=users_db
PORT=8081
```

## Docker

Construcción local:

```bash
docker build -t backjs-et .
```

Ejecución:

```bash
docker run -p 8081:8081 backjs-et
```

## Endpoints

### Registrar usuario

```http
POST /api/users/register
```

### Obtener usuarios

```http
GET /api/users
```

### Obtener usuario por ID

```http
GET /api/users/:id
```

### Eliminar usuario

```http
DELETE /api/users/:id
```

## CI/CD

GitHub Actions automatiza:

1. Build Docker.
2. Login en Amazon ECR.
3. Publicación de imagen.
4. Versionamiento mediante tags.
aa
Archivo:

```text
.github/workflows/deploy.yml
```

## AWS

Infraestructura utilizada:

* Amazon ECS Fargate
* Amazon ECR
* CloudWatch Logs
* IAM

## Seguridad

* Variables sensibles almacenadas como GitHub Secrets.
* Puerto expuesto mínimo: 8081.
* Imagen desplegada mediante contenedores aislados.
