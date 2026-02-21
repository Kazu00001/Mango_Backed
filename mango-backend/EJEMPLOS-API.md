# 🧪 Ejemplos de Uso de la API

## Iniciar el Servidor

```bash
cd mango-backend
npm run start:dev
```

El servidor se ejecutará en: `http://localhost:3000/api`

---

## Endpoints de Usuarios

### 1. Obtener todos los usuarios

```bash
curl http://localhost:3000/api/users
```

**Respuesta:**
```json
[
  {
    "id": "1",
    "name": "Usuario Demo",
    "email": "demo@example.com"
  }
]
```

---

### 2. Obtener un usuario por ID

```bash
curl http://localhost:3000/api/users/1
```

**Respuesta:**
```json
{
  "id": "1",
  "name": "Usuario Demo",
  "email": "demo@example.com"
}
```

---

### 3. Crear un nuevo usuario

```bash
curl -X POST http://localhost:3000/api/users \
  -H "Content-Type: application/json" \
  -d '{
    "name": "Juan Pérez",
    "email": "juan@example.com"
  }'
```

**Respuesta:**
```json
{
  "id": "1709165234567",
  "name": "Juan Pérez",
  "email": "juan@example.com"
}
```

---

### 4. Actualizar un usuario

```bash
curl -X PUT http://localhost:3000/api/users/1 \
  -H "Content-Type: application/json" \
  -d '{
    "name": "Juan Pérez Actualizado",
    "email": "juan.nuevo@example.com"
  }'
```

**Respuesta:**
```json
{
  "id": "1",
  "name": "Juan Pérez Actualizado",
  "email": "juan.nuevo@example.com"
}
```

---

### 5. Eliminar un usuario

```bash
curl -X DELETE http://localhost:3000/api/users/1
```

**Respuesta:** Status 204 (No Content)

---

## Pruebas de Validación

### Error: Email inválido

```bash
curl -X POST http://localhost:3000/api/users \
  -H "Content-Type: application/json" \
  -d '{
    "name": "Test",
    "email": "email-invalido"
  }'
```

**Respuesta de error:**
```json
{
  "statusCode": 400,
  "message": ["email must be an email"],
  "error": "Bad Request"
}
```

### Error: Campos faltantes

```bash
curl -X POST http://localhost:3000/api/users \
  -H "Content-Type: application/json" \
  -d '{
    "name": "Test"
  }'
```

**Respuesta de error:**
```json
{
  "statusCode": 400,
  "message": [
    "email should not be empty",
    "email must be an email"
  ],
  "error": "Bad Request"
}
```

---

## Pruebas con HTTPie (alternativa a curl)

Si prefieres usar HTTPie (más legible):

```bash
# Instalar HTTPie
brew install httpie

# GET
http GET localhost:3000/api/users

# POST
http POST localhost:3000/api/users name="Juan" email="juan@example.com"

# PUT
http PUT localhost:3000/api/users/1 name="Juan Updated"

# DELETE
http DELETE localhost:3000/api/users/1
```

---

## Pruebas con Postman o Thunder Client

1. **Importar colección**: Puedes crear una colección con estos endpoints
2. **Base URL**: `http://localhost:3000/api`
3. **Headers**: `Content-Type: application/json`

---

## Verificar que el servidor esté corriendo

```bash
curl http://localhost:3000/api
```

Si responde, el servidor está activo.

---

## Logs del servidor

Al ejecutar en modo desarrollo, verás logs como:

```
[Nest] 12345  - 20/02/2024, 23:30:00     LOG [NestFactory] Starting Nest application...
[Nest] 12345  - 20/02/2024, 23:30:00     LOG [InstanceLoader] AppModule dependencies initialized
[Nest] 12345  - 20/02/2024, 23:30:00     LOG [RoutesResolver] UsersController {/api/users}
[Nest] 12345  - 20/02/2024, 23:30:00     LOG [RouterExplorer] Mapped {/api/users, GET} route
[Nest] 12345  - 20/02/2024, 23:30:00     LOG [NestApplication] Nest application successfully started
🚀 Servidor ejecutándose en http://localhost:3000/api
```

---

¡Listo para usar! 🎉
