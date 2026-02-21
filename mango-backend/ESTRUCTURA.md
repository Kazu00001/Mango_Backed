# 🥭 Mango Backend

Backend API construido con NestJS para aplicaciones modernas.

## 📁 Estructura del Proyecto

```
src/
├── modules/              # Módulos de la aplicación
│   ├── users/           # Módulo de usuarios (ejemplo)
│   │   ├── dto/        # Data Transfer Objects
│   │   ├── users.controller.ts
│   │   ├── users.service.ts
│   │   └── users.module.ts
│   └── auth/           # Módulo de autenticación (próximamente)
│
├── common/              # Código compartido
│   ├── decorators/     # Decoradores personalizados
│   ├── filters/        # Filtros de excepciones
│   ├── guards/         # Guards de autorización
│   ├── interceptors/   # Interceptors
│   ├── pipes/          # Pipes de validación
│   └── middleware/     # Middlewares personalizados
│
├── config/             # Configuraciones
│   └── configuration.ts
│
├── database/           # Configuración de base de datos
├── utils/              # Utilidades generales
├── app.module.ts       # Módulo principal
└── main.ts            # Punto de entrada
```

## 🚀 Inicio Rápido

### Instalación

```bash
# Instalar dependencias
npm install

# Copiar archivo de entorno
cp .env.example .env
```

### Ejecución

```bash
# Desarrollo
npm run start:dev

# Producción
npm run build
npm run start:prod
```

El servidor se ejecutará en `http://localhost:3000/api`

## 📡 Endpoints Disponibles

### Usuarios

| Método | Endpoint | Descripción |
|--------|----------|-------------|
| GET    | `/api/users` | Obtener todos los usuarios |
| GET    | `/api/users/:id` | Obtener usuario por ID |
| POST   | `/api/users` | Crear nuevo usuario |
| PUT    | `/api/users/:id` | Actualizar usuario |
| DELETE | `/api/users/:id` | Eliminar usuario |

### Ejemplo de Request

```bash
# Crear usuario
curl -X POST http://localhost:3000/api/users \
  -H "Content-Type: application/json" \
  -d '{
    "name": "Juan Pérez",
    "email": "juan@example.com"
  }'

# Obtener todos los usuarios
curl http://localhost:3000/api/users
```

## 🛠️ Características Configuradas

- ✅ Validación automática de datos con `class-validator`
- ✅ Transformación de datos con `class-transformer`
- ✅ Manejo global de excepciones
- ✅ Logging de requests
- ✅ CORS habilitado
- ✅ Variables de entorno con `@nestjs/config`
- ✅ Prefijo global `/api` para todas las rutas
- ✅ TypeScript configurado

## 📦 Dependencias Principales

- **NestJS** - Framework backend
- **TypeScript** - Lenguaje de programación
- **class-validator** - Validación de DTOs
- **class-transformer** - Transformación de objetos
- **@nestjs/config** - Gestión de configuración

## 🔧 Scripts Disponibles

```bash
npm run start          # Iniciar en modo desarrollo
npm run start:dev      # Desarrollo con hot-reload
npm run start:prod     # Producción
npm run build          # Compilar para producción
npm run test           # Ejecutar tests
npm run test:e2e       # Tests end-to-end
npm run lint           # Verificar código con ESLint
```

## 📝 Siguientes Pasos

1. **Configurar Base de Datos**
   - Instalar TypeORM o Prisma
   - Configurar conexión en `/src/database`

2. **Agregar Autenticación**
   - Implementar módulo de Auth con JWT
   - Crear guards de autenticación

3. **Agregar Swagger**
   ```bash
   npm install @nestjs/swagger
   ```

4. **Configurar Logging**
   - Integrar Winston o Pino para logs avanzados

## 📚 Recursos

- [Documentación NestJS](https://docs.nestjs.com)
- [TypeScript](https://www.typescriptlang.org/)
- [Class Validator](https://github.com/typestack/class-validator)

## 👨‍💻 Desarrollo

Para agregar un nuevo módulo:

```bash
nest g module modules/nombre-modulo
nest g controller modules/nombre-modulo
nest g service modules/nombre-modulo
```

---

**Creado con ❤️ usando NestJS**
