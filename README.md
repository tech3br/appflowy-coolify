# AppFlowy Coolify Deployment

Self-hosted AppFlowy Cloud deployment using Docker Compose, optimized for Coolify.

## 📋 Overview

This repository provides a production-ready Docker Compose setup for deploying [AppFlowy](https://appflowy.io) on [Coolify](https://coolify.io). AppFlowy is an open-source alternative to Notion, and Coolify is a self-hosted Heroku/Netlify alternative.

## 🏗️ Architecture

The deployment includes the following services:

- **NGINX**: Reverse proxy for routing traffic
- **AppFlowy Cloud**: The main application server
- **PostgreSQL**: Database for storing application data
- **Redis**: Caching and session management
- **MinIO**: S3-compatible object storage for files
- **GoTrue**: Authentication service (Supabase Auth)

## 🚀 Quick Start

### Prerequisites

- Docker and Docker Compose installed
- A server with at least 2GB RAM and 20GB storage
- (Optional) A domain name pointed to your server

### Installation Steps

1. **Clone this repository**
   ```bash
   git clone https://github.com/tech3br/appflowy-coolify.git
   cd appflowy-coolify
   ```

2. **Configure environment variables**
   ```bash
   cp .env.example .env
   ```
   
   Edit `.env` and update the following important values:
   - `APPFLOWY_DOMAIN`: Your domain name
   - `POSTGRES_PASSWORD`: A strong database password
   - `REDIS_PASSWORD`: A strong Redis password
   - `MINIO_ROOT_PASSWORD`: A strong MinIO password
   - `GOTRUE_JWT_SECRET`: A random secret (minimum 32 characters)
   - SMTP settings for email functionality

3. **Start the services**
   ```bash
   docker-compose up -d
   ```

4. **Check service health**
   ```bash
   docker-compose ps
   docker-compose logs -f
   ```

5. **Access AppFlowy**
   - Open your browser and navigate to your domain or `http://localhost`
   - Create your first account and start using AppFlowy!

## 🎯 Coolify Deployment

### Deploy on Coolify

1. **Add a new resource** in Coolify dashboard
2. Select **Docker Compose** as the resource type
3. Connect your Git repository: `https://github.com/tech3br/appflowy-coolify`
4. Set the following environment variables in Coolify:
   - All variables from `.env.example`
   - Ensure `APPFLOWY_DOMAIN` matches your Coolify domain
5. Deploy the application

### Coolify-Specific Features

The `docker-compose.yml` includes:
- Coolify management labels (`coolify.managed=true`)
- Traefik proxy integration for automatic HTTPS
- Health checks for all services
- Proper service dependencies

## 🔧 Configuration

### Environment Variables

All configuration is done through environment variables. See `.env.example` for a complete list of available options.

#### Key Settings

- **Domain**: Set `APPFLOWY_DOMAIN` to your actual domain
- **Database**: Configure PostgreSQL credentials
- **Storage**: MinIO settings for file storage
- **Email**: SMTP settings for notifications and user verification
- **Security**: Update all passwords and secrets

### SMTP Configuration

To enable email functionality:

1. Use your email provider's SMTP settings
2. For Gmail, use an App Password (not your regular password)
3. Update the following in `.env`:
   ```
   GOTRUE_SMTP_HOST=smtp.gmail.com
   GOTRUE_SMTP_PORT=587
   GOTRUE_SMTP_USER=your-email@gmail.com
   GOTRUE_SMTP_PASS=your-app-password
   ```

### SSL/TLS Configuration

#### Option 1: Coolify Automatic SSL (Recommended)
Coolify automatically handles SSL certificates via Let's Encrypt when you set a domain.

#### Option 2: Custom SSL Certificates
1. Place your certificates in `nginx/ssl/`:
   - `certificate.crt`: Your SSL certificate
   - `private_key.key`: Your private key
2. Uncomment the HTTPS server block in `nginx/nginx.conf`
3. Restart the nginx service

## 🔍 Troubleshooting

### Check Service Logs
```bash
# All services
docker-compose logs -f

# Specific service
docker-compose logs -f appflowy_cloud
docker-compose logs -f postgres
```

### Restart Services
```bash
# Restart all
docker-compose restart

# Restart specific service
docker-compose restart appflowy_cloud
```

### Reset Everything
```bash
# Stop and remove all containers and volumes
docker-compose down -v

# Start fresh
docker-compose up -d
```

### Common Issues

1. **Port conflicts**: Ensure ports 80 and 443 are not used by other services
2. **Database connection errors**: Verify PostgreSQL is healthy and credentials are correct
3. **Email not working**: Check SMTP settings and firewall rules
4. **Storage issues**: Ensure MinIO is running and accessible

## 📊 Monitoring

### Health Checks
All services include health checks. View status with:
```bash
docker-compose ps
```

### Resource Usage
```bash
docker stats
```

## 🔐 Security Recommendations

1. **Change all default passwords** in `.env`
2. **Use strong passwords** (minimum 16 characters)
3. **Keep Docker images updated**: `docker-compose pull && docker-compose up -d`
4. **Enable firewall rules** to restrict access
5. **Regular backups** of PostgreSQL and MinIO data
6. **Use HTTPS** in production (automatic with Coolify)

## 💾 Backup and Restore

### Backup

```bash
# Backup PostgreSQL
docker-compose exec postgres pg_dump -U ${POSTGRES_USER:-postgres} ${POSTGRES_DB:-appflowy} > backup.sql

# Backup MinIO data
docker-compose exec minio mc mirror /data ./minio-backup
```

### Restore

```bash
# Restore PostgreSQL
cat backup.sql | docker-compose exec -T postgres psql -U ${POSTGRES_USER:-postgres} ${POSTGRES_DB:-appflowy}

# Restore MinIO data
docker-compose exec minio mc mirror ./minio-backup /data
```

## 🆕 Updates

To update to the latest AppFlowy version:

```bash
docker-compose pull
docker-compose up -d
```

**Note**: The docker-compose.yml uses pinned versions for stability and reproducibility. To update to newer versions:
1. Check the latest releases on Docker Hub for each service
2. Update the image tags in docker-compose.yml
3. Test in a non-production environment first
4. Apply the updates to production

**Image Sources**:
- AppFlowy Cloud: [appflowyinc/appflowy_cloud](https://hub.docker.com/r/appflowyinc/appflowy_cloud)
- PostgreSQL: [postgres](https://hub.docker.com/_/postgres)
- Redis: [redis](https://hub.docker.com/_/redis)
- MinIO: [minio/minio](https://hub.docker.com/r/minio/minio)
- GoTrue: [supabase/gotrue](https://hub.docker.com/r/supabase/gotrue)

## 📚 Documentation

- [AppFlowy Documentation](https://docs.appflowy.io)
- [AppFlowy Docker Installation Guide](https://docs.appflowy.io/docs/appflowy/install-appflowy/installation-methods/installing-with-docker)
- [Coolify Documentation](https://coolify.io/docs)
- [AppFlowy GitHub](https://github.com/AppFlowy-IO/AppFlowy-Cloud)

## 🤝 Contributing

Contributions are welcome! Please feel free to submit a Pull Request.

## 📄 License

This deployment configuration is open source. AppFlowy itself is licensed under AGPL-3.0.

## ⚠️ Disclaimer

This is a community-maintained deployment configuration. For production use, please review and adjust settings according to your security requirements.

## 🙏 Acknowledgments

- [AppFlowy Team](https://github.com/AppFlowy-IO) for creating an amazing open-source product
- [Coolify](https://coolify.io) for providing an excellent self-hosting platform
- The open-source community for various contributions and guides