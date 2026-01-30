# twenty-crm xCloud script
- modified from original twenty-crm `docker-compose.yml` and `.env`

## Description
Allows you to deploy twenty-crm on xCloud

## Prerequisites
- Must make proper changes to .env
- Make sure no other apps running on port 3000

## Configuration
Key configuration options and how to set them.

## Environment Variables

The following environment variables must be configured in `.env`:

- **SERVER_URL**: Your domain from xCloud (e.g., `https://short.domain.net`)
- **APP_SECRET**: 32-character random string generated via `openssl rand -base64 32`
- **PG_DATABASE_PASSWORD**: PostgreSQL password (change from default - try not to use special characters in it)
- **STORAGE_TYPE**: `local` or `s3` for file storage
- **STORAGE_S3_***: S3 bucket credentials (if using S3)

The stack includes:
- **nginx**: Reverse proxy (port 3000)
- **server**: Twenty CRM application
- **worker**: Background job processor
- **db**: PostgreSQL database
- **redis**: Caching layer

All services have health checks and auto-restart enabled.