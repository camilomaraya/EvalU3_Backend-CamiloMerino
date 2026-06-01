# ProviEmplea API

API REST para la plataforma de empleo ProviEmplea de la Municipalidad de Providencia. Implementa búsqueda inversa de empleo donde las empresas buscan talentos mediante curriculum ciego.

## Stack Tecnológico

- PHP 8.2 + Laravel 11
- MySQL 8.0
- Docker + Nginx
- Swagger/OpenAPI 3.0 (L5-Swagger)

## Instalación

```bash
# Clonar repositorio
git clone https://github.com/TU_USUARIO/proviemplea_eva3.git
cd proviemplea_eva3/backend

# Copiar variables de entorno
cp .env.example .env

# Levantar contenedores
docker compose up -d --build

# Instalar dependencias
docker compose exec app composer install

# Generar clave
docker compose exec app php artisan key:generate

# Permisos
docker compose exec --user root app chmod -R 777 storage bootstrap/cache

# Ejecutar migraciones
docker compose exec app php artisan migrate

# Generar documentación Swagger
docker compose exec app php generate-swagger.php
```

## Endpoints disponibles

| Método | Endpoint | Descripción |
|--------|----------|-------------|
| GET | /api/health | Estado del servicio |
| GET | /api/personas | Listar CV ciegos |
| POST | /api/personas | Registrar talento |
| GET | /api/personas/{id} | Ver perfil completo |
| PUT | /api/personas/{id} | Actualizar perfil |
| DELETE | /api/personas/{id} | Desactivar perfil |
| PATCH | /api/personas/{id}/validar | Validar perfil |
| GET | /api/empresas | Listar empresas |
| POST | /api/empresas | Registrar empresa |
| GET | /api/empresas/{id} | Ver empresa |
| PUT | /api/empresas/{id} | Actualizar empresa |
| DELETE | /api/empresas/{id} | Desactivar empresa |
| PATCH | /api/empresas/{id}/validar | Validar empresa |
| GET | /api/admin/contactos | Listar contactos |
| POST | /api/admin/contactos | Crear solicitud |
| PATCH | /api/admin/contactos/{id}/estado | Actualizar estado |
| GET | /api/admin/estadisticas | Estadísticas generales |

## Documentación Swagger UI

Con los contenedores corriendo: [http://localhost:8080/api/documentation](http://localhost:8080/api/documentation)

- Camilo Meriño
- Repositorio: https://github.com/camilomaraya/EvalU3_Backend-CamiloMerino.git

## Evaluación

Evaluación U3 — Desarrollo Backend — Instituto Profesional San Sebastián
