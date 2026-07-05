# Docker Cheatsheet

## Most Used

```bash
docker --version
docker ps
docker ps -a
docker images
docker build -t app-name .
docker run -p 3000:3000 app-name
docker logs -f container-name
docker exec -it container-name sh
docker compose up -d
docker compose down
```

## Command Reference

| Action | Command |
| --- | --- |
| Build | `docker build -t name .` |
| Run | `docker run name` |
| Run with port | `docker run -p host:container name` |
| Background | `docker run -d name` |
| Logs | `docker logs -f name` |
| Shell | `docker exec -it name sh` |
| Stop | `docker stop name` |
| Remove container | `docker rm name` |
| Remove image | `docker rmi image` |
| Compose start | `docker compose up -d` |
| Compose stop | `docker compose down` |

## Things I Forget Often

- `docker ps` only shows running containers; use `docker ps -a` for stopped ones.
- `docker compose down -v` removes volumes.
- A container name can be used as a hostname inside the same Docker network.
- Rebuild after changing `Dockerfile` or dependency installation steps.

## Interview Questions

| Question | Short answer |
| --- | --- |
| Image vs container? | Image is the template; container is a running or stopped instance. |
| Volume vs bind mount? | Volume is Docker-managed; bind mount maps a host path. |
| Why Compose? | It defines multi-container apps in one file. |
| Why containers? | Repeatable runtime and isolated dependencies. |
