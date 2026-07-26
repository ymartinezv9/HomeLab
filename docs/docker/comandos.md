# Comandos útiles

## Información

```bash
docker --version
docker compose version
docker info
```

---

## Imágenes

```bash
docker pull nginx
docker images
docker rmi <imagen>
```

---

## Contenedores

```bash
docker run hello-world

docker ps

docker ps -a

docker stop <contenedor>

docker start <contenedor>

docker restart <contenedor>

docker rm <contenedor>
```

---

## Logs

```bash
docker logs <contenedor>

docker logs -f <contenedor>
```

---

## Redes

```bash
docker network ls

docker network inspect bridge
```

---

## Volúmenes

```bash
docker volume ls

docker volume inspect <volumen>
```

---

## Docker Compose

```bash
docker compose up -d

docker compose down

docker compose ps

docker compose logs
```

---

## Limpieza

Eliminar contenedores detenidos.

```bash
docker container prune
```

Eliminar imágenes no utilizadas.

```bash
docker image prune
```

Eliminar recursos no utilizados.

```bash
docker system prune -a
```
