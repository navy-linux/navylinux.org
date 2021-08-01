
---
title : "Navy Linux 8.4 Stable Docker Image Now Available"

description: >
    Navy Foundation is proud to announce the Stable Docker Image of the Navy Linux Available now

---
# Navy Linux 8.4 Stable Docker Image

Navy Foundation is proud to announce the stable Docker image of the Navy Linux Available now, Here is the [Docker Hub  container](https://hub.docker.com/r/navylinux/navylinux) to download Navy Linux container.

### Docker Pull Command

```bash
docker pull navylinux/navylinux
```

### Source code

https://github.com/navy-linux/docker-images

### Example Dockerfile for Nginx

```bash
FROM navylinux:8
RUN yum -y update
RUN yum -y install nginx
EXPOSE 80/tcp
CMD ["nginx", "-g daemon off;"]

```
