# README

This is a simple repo to deploy Taiga.io on Coolify. You can start a `Public Repository` on your Coolify and enter this repo's url. Then configure the env and start to use Taiga

## Environment Variables

Add to the Enviroment of the app

```
# Required:
POSTGRES_PASSWORD=your-secure-database-password
TAIGA_DOMAIN=yourdomain.com
SECRET_KEY=your-very-long-and-secure-secret-key

# Optional:
POSTGRES_DB=taiga
POSTGRES_USER=taiga
TAIGA_SCHEME=https
RABBITMQ_USER=taiga
RABBITMQ_PASS=taiga
EMAIL_BACKEND=console
WEBSOCKETS_SCHEME=wss

# SMTP:
EMAIL_BACKEND=smtp
EMAIL_HOST=smtp.yourprovider.com
EMAIL_PORT=587
EMAIL_HOST_USER=your-email@domain.com
EMAIL_HOST_PASSWORD=your-email-password
EMAIL_USE_TLS=True
```

## Common troubleshooting issues
### Database connection error

- Check if `POSTGRES_PASSWORD` is configured
- Ensure service `taiga-db` is fully started

### Domain access error
-  Check if DNS record points to Coolify server
-  Ensure `TAIGA_DOMAIN` matches actual domain

###  Websocket events error
- Check if `WEBSOCKETS_SCHEME` is appropriate (ws for http, wss for https)
- Ensure `SECRET_KEY` is identical for all services

###  Important notes
- Security: Change `SECRET_KEY` and `POSTGRES_PASSWORD` to strong values
- Backup: Coolify automatically backs up volumes, but separate database backup should be configured
- Performance: For large teams, consider increasing resources for database service
- Updates: Monitor Taiga repository for image version updates
