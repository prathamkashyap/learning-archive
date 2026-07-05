# Docker Troubleshooting and Cleanup

## Context

Most Docker problems I hit are not deep architecture problems. They are usually old containers, wrong ports, missing rebuilds, disk usage, or bad environment variables.

## Troubleshooting Flow

```bash
docker ps -a
docker logs <container>
docker inspect <container>
docker exec -it <container> sh
docker image ls
docker volume ls
docker network ls
```

## Common Problems

| Symptom | Check | Fix |
| --- | --- | --- |
| App not reachable | Port mapping | `docker run -p 3000:3000 ...` |
| Code changes missing | Image not rebuilt | `docker compose build` |
| Container exits immediately | Logs | `docker logs <container>` |
| Database data gone | Volume usage | Use named volume |
| Disk full | Docker disk usage | `docker system df` |

## Cleanup Commands

```bash
docker system df
docker container prune
docker image prune
docker volume prune
docker network prune
docker system prune
```

More aggressive cleanup:

```bash
docker system prune -a
```

Use `-a` carefully because it removes unused images, including images you may want to keep.

## Common Mistakes

- Running prune commands without reading what they delete.
- Deleting volumes before exporting database data.
- Debugging app code before checking container logs.
- Forgetting that a port can already be used by a local process.

## Quick Reference

| Need | Command |
| --- | --- |
| Disk usage | `docker system df` |
| Container logs | `docker logs -f <container>` |
| Remove stopped containers | `docker container prune` |
| Remove unused images | `docker image prune` |
| Remove unused volumes | `docker volume prune` |
