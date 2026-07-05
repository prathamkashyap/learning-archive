# Docker Volumes, Mounts, and Networks

## Context

Containers are disposable, so persistent data needs a separate place. Networks matter because real apps usually have more than one service.

## Volumes

Create and inspect a named volume:

```bash
docker volume create postgres-data
docker volume ls
docker volume inspect postgres-data
```

Use it:

```bash
docker run -d \
  --name postgres \
  -e POSTGRES_PASSWORD=postgres \
  -v postgres-data:/var/lib/postgresql/data \
  postgres:16
```

## Bind Mounts

Bind the current project into a container for development:

```bash
docker run -it --rm \
  -v "$PWD":/app \
  -w /app \
  node:22-alpine sh
```

Named volume vs bind mount:

| Type | Best for | Example |
| --- | --- | --- |
| Named volume | Database data | `db-data:/var/lib/postgresql/data` |
| Bind mount | Live source code | `./src:/app/src` |

## Networks

```bash
docker network create app-net
docker network ls
docker network inspect app-net
```

Run two containers on the same network:

```bash
docker run -d --name redis --network app-net redis:7
docker run -it --rm --network app-net redis:7 redis-cli -h redis ping
```

## Common Mistakes

- Using bind mounts for database data in a way that breaks file permissions.
- Removing a container and assuming the named volume was removed too.
- Trying to connect to another container through `localhost`.
- Forgetting that Compose creates a default network for services.

## Quick Reference

| Task | Command |
| --- | --- |
| Create volume | `docker volume create <name>` |
| Use volume | `-v name:/container/path` |
| Use bind mount | `-v "$PWD":/app` |
| Create network | `docker network create <name>` |
| Attach network | `--network <name>` |
