# Docker Basics and Architecture

## Context

Docker matters when a project works on one machine but not another. I use it to package the runtime, dependencies, environment variables, ports, and startup commands into a repeatable setup.

## Core Objects

| Object | Meaning | Command to inspect |
| --- | --- | --- |
| Image | Read-only template for containers | `docker images` |
| Container | Running or stopped instance of an image | `docker ps -a` |
| Volume | Docker-managed persistent data | `docker volume ls` |
| Network | Communication layer between containers | `docker network ls` |
| Dockerfile | Build instructions for an image | `docker build .` |
| Compose file | Multi-container app definition | `docker compose up` |

## Installation Checks

```bash
docker --version
docker compose version
docker info
docker run hello-world
```

## Architecture Notes

```text
Docker CLI -> Docker daemon -> Images / Containers / Volumes / Networks
```

- The CLI sends commands.
- The daemon creates and manages Docker objects.
- Images are built once and reused.
- Containers are disposable; data should live in volumes or external services.

## Common Mistakes

- Treating a container like a virtual machine.
- Saving important data only inside a container filesystem.
- Forgetting that `localhost` inside a container means the container itself.
- Installing dependencies manually inside a running container instead of updating the Dockerfile.

## Quick Reference

| Need | Command |
| --- | --- |
| Check daemon | `docker info` |
| Test install | `docker run hello-world` |
| List images | `docker images` |
| List containers | `docker ps -a` |
| List volumes | `docker volume ls` |
| List networks | `docker network ls` |
