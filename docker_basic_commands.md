
# Docker Basic Commands Guide

## 1. Install & Verify
```bash
docker --version
docker info
```

---

# 2. Pull an Image
Download an image from Docker Hub.

```bash
docker pull <image_name>
docker pull nginx
docker pull ubuntu:22.04
```

---

# 3. List Images
```bash
docker images
```

---

# 4. Run a Container
Run a container from an image.

```bash
docker run <image_name>
docker run nginx
```

Run with options:

```bash
docker run -d -p 8080:80 nginx
```

Options:
- `-d` → Run in background
- `-p` → Port mapping
- `--name` → Name the container

Example:

```bash
docker run -d -p 8080:80 --name mynginx nginx
```

---

# 5. List Containers

Show running containers:

```bash
docker ps
```

Show all containers:

```bash
docker ps -a
```

---

# 6. Stop Container

```bash
docker stop <container_id_or_name>
docker stop mynginx
```

---

# 7. Start Container

```bash
docker start <container_id_or_name>
```

---

# 8. Restart Container

```bash
docker restart <container_id_or_name>
```

---

# 9. Remove Container

Container must be stopped first.

```bash
docker rm <container_id_or_name>
```

Force remove:

```bash
docker rm -f <container_id_or_name>
```

---

# 10. View Container Logs

```bash
docker logs <container_id_or_name>
```

Follow logs:

```bash
docker logs -f <container_id_or_name>
```

---

# 11. Execute Command Inside Container

```bash
docker exec -it <container_name> bash
```

Example:

```bash
docker exec -it mynginx bash
```

---

# 12. Remove Image

```bash
docker rmi <image_name>
docker rmi nginx
```

Force remove:

```bash
docker rmi -f nginx
```

---

# 13. Remove Unused Containers

```bash
docker container prune
```

---

# 14. Remove Unused Images

```bash
docker image prune
```

Remove all unused images:

```bash
docker image prune -a
```

---

# 15. Remove Everything (Clean Docker)

⚠️ This removes all containers, images, networks, and cache.

```bash
docker system prune -a
```

---

# 16. Docker Volumes

List volumes:

```bash
docker volume ls
```

Remove volume:

```bash
docker volume rm <volume_name>
```

Remove unused volumes:

```bash
docker volume prune
```

---

# 17. Docker Networks

List networks:

```bash
docker network ls
```

Remove network:

```bash
docker network rm <network_name>
```

---

# Quick Workflow Example

```bash
# Pull image
docker pull nginx

# Run container
docker run -d -p 8080:80 --name mynginx nginx

# Check containers
docker ps

# Stop container
docker stop mynginx

# Remove container
docker rm mynginx

# Remove image
docker rmi nginx
```
