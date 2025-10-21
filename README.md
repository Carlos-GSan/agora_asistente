# n8n Docker Setup

Este proyecto contiene la configuración para ejecutar n8n usando Docker Compose.

## Requisitos

- Docker
- Docker Compose

## Inicio Rápido

1. **Copia el archivo de variables de entorno:**
   ```bash
   cp .env.example .env
   ```

2. **Edita el archivo `.env` con tus configuraciones:**
   ```bash
   nano .env
   ```

3. **Inicia n8n:**
   ```bash
   docker-compose up -d
   ```

4. **Accede a n8n:**
   - Abre tu navegador en: http://localhost:5678
   - Usuario por defecto: `admin`
   - Contraseña por defecto: `admin`

## Comandos Útiles

### Ver logs
```bash
docker-compose logs -f n8n
```

### Detener n8n
```bash
docker-compose down
```

### Reiniciar n8n
```bash
docker-compose restart
```

### Actualizar n8n
```bash
docker-compose pull
docker-compose up -d
```

## Configuración

### Variables de Entorno

- `N8N_HOST`: Hostname donde se ejecuta n8n
- `N8N_PROTOCOL`: Protocolo (http o https)
- `WEBHOOK_URL`: URL para webhooks
- `TIMEZONE`: Zona horaria
- `N8N_BASIC_AUTH_USER`: Usuario para autenticación básica
- `N8N_BASIC_AUTH_PASSWORD`: Contraseña para autenticación básica

### Volúmenes

- `n8n_data`: Almacena los datos de n8n (workflows, credenciales, etc.)
- `./local-files`: Carpeta para archivos locales accesibles desde n8n

## Seguridad

⚠️ **IMPORTANTE**: Cambia las credenciales por defecto antes de usar en producción.

Para producción, considera:
- Usar HTTPS (configura un reverse proxy como Nginx o Traefik)
- Cambiar las credenciales de autenticación
- Configurar backups regulares del volumen `n8n_data`
