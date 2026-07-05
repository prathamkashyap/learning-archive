# Docker Compose

## Context

Compose is what I use when an app has more than one container. Instead of long `docker run` commands, I keep services, ports, volumes, and environment variables in one YAML file.

## Basic Compose File

```yaml
services:
  app:
    build: .
    ports:
      - "3000:3000"
    environment:
      NODE_ENV: development
    volumes:
      - .:/app

  db:
    image: postgres:16
    environment:
      POSTGRES_PASSWORD: postgres
    volumes:
      - db-data:/var/lib/postgresql/data

volumes:
  db-data:
```

## Commands

```bash
docker compose up
docker compose up -d
docker compose down
docker compose down -v
docker compose ps
docker compose logs -f
docker compose exec app sh
docker compose build
docker compose pull
```

## Environment Files

Compose reads `.env` in the same directory:

```env
POSTGRES_PASSWORD=postgres
APP_PORT=3000
```

Use variables:

```yaml
ports:
  - "${APP_PORT}:3000"
```

## Common Mistakes

- Using `docker-compose` old syntax when the installed command is `docker compose`.
- Running `down -v` and deleting database data by accident.
- Forgetting to rebuild after changing a Dockerfile.
- Putting secrets in Compose files committed to Git.

## Quick Reference

| Task | Command |
| --- | --- |
| Start foreground | `docker compose up` |
| Start background | `docker compose up -d` |
| Stop | `docker compose down` |
| Stop and delete volumes | `docker compose down -v` |
| Service shell | `docker compose exec <service> sh` |
