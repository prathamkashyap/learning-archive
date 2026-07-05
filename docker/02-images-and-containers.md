# Docker Images and Containers

## Context

The image/container split is the Docker idea I check most often. Build images from project files, then run containers from those images.

## Build Images

```bash
docker build -t app-name .
docker build -t app-name:dev .
docker build --no-cache -t app-name .
```

Example Dockerfile shape:

```dockerfile
FROM node:22-alpine
WORKDIR /app
COPY package*.json ./
RUN npm ci
COPY . .
EXPOSE 3000
CMD ["npm", "run", "dev"]
```

## Run Containers

```bash
docker run app-name
docker run --name app-dev app-name
docker run -p 3000:3000 app-name
docker run -d -p 3000:3000 --name app-dev app-name
```

## Inspect and Debug

```bash
docker ps
docker ps -a
docker logs app-dev
docker logs -f app-dev
docker exec -it app-dev sh
docker inspect app-dev
```

## Stop and Remove

```bash
docker stop app-dev
docker start app-dev
docker restart app-dev
docker rm app-dev
docker rmi app-name
```

## Common Mistakes

- Rebuilding the image but running an old container.
- Forgetting `-p host:container`, then wondering why the app is not reachable.
- Using `latest` everywhere and losing track of what changed.
- Running a command in the container and forgetting it disappears when the container is replaced.

## Quick Reference

| Task | Command |
| --- | --- |
| Build image | `docker build -t app-name .` |
| Run in background | `docker run -d --name app app-name` |
| Map port | `docker run -p 8080:80 nginx` |
| See logs | `docker logs -f app` |
| Shell into container | `docker exec -it app sh` |
| Remove stopped container | `docker rm app` |
