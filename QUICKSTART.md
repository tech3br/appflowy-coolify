# AppFlowy Coolify - Quick Start Guide

This is a condensed guide to get AppFlowy running quickly on Coolify.

## Prerequisites

- Docker and Docker Compose installed
- Server with minimum 2GB RAM and 20GB storage
- (Optional) Domain name configured

## 5-Minute Setup

### 1. Clone and Configure

```bash
# Clone the repository
git clone https://github.com/tech3br/appflowy-coolify.git
cd appflowy-coolify

# Copy environment template
cp .env.example .env

# Edit configuration (use nano, vim, or your preferred editor)
nano .env
```

### 2. Minimum Required Changes in .env

```bash
# Change these values before starting:
APPFLOWY_DOMAIN=your-domain.com           # Your domain
POSTGRES_PASSWORD=your-secure-password    # Strong password
REDIS_PASSWORD=your-redis-password        # Strong password
MINIO_ROOT_PASSWORD=your-minio-password   # Strong password
GOTRUE_JWT_SECRET=random-32-char-secret   # Generate with: openssl rand -base64 32
```

### 3. Start Services

```bash
# Start all services
docker compose up -d

# View logs
docker compose logs -f

# Check service health
docker compose ps
```

### 4. Access AppFlowy

- Open your browser: `http://your-domain.com` or `http://localhost`
- Create your first account
- Start using AppFlowy!

## Coolify-Specific Deployment

### In Coolify Dashboard:

1. **Add New Resource** → Docker Compose
2. **Repository**: `https://github.com/tech3br/appflowy-coolify`
3. **Environment Variables**: Add all from `.env.example`
4. **Domain**: Coolify will auto-configure SSL/HTTPS
5. **Deploy**: Click deploy and wait for services to start

## Troubleshooting

### Services not starting?
```bash
docker compose logs --tail=100 [service-name]
```

### Need to restart?
```bash
docker compose restart
```

### Reset everything?
```bash
docker compose down -v  # ⚠️ This deletes all data!
docker compose up -d
```

## What's Included?

- ✅ AppFlowy Cloud application
- ✅ PostgreSQL database
- ✅ Redis caching
- ✅ MinIO S3 storage
- ✅ GoTrue authentication
- ✅ NGINX reverse proxy
- ✅ Automatic health checks
- ✅ Coolify integration labels
- ✅ SSL/HTTPS ready (via Coolify)

## Next Steps

- Configure SMTP for email notifications
- Set up regular backups (see README.md)
- Review security settings
- Customize domains and ports

## Need More Help?

See the detailed [README.md](README.md) for:
- Complete configuration options
- Security recommendations
- Backup and restore procedures
- Advanced customization
- Troubleshooting guide

## Support

- [AppFlowy Documentation](https://docs.appflowy.io)
- [Coolify Documentation](https://coolify.io/docs)
- [GitHub Issues](https://github.com/tech3br/appflowy-coolify/issues)
