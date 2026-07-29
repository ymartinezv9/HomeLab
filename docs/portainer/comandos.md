# Comandos útiles

## Ver contenedor

```bash
docker ps
```

---

## Ver logs

```bash
docker logs portainer
```

---

## Reiniciar

```bash
docker restart portainer
```

---

## Detener

```bash
docker stop portainer
```

---

## Iniciar

```bash
docker start portainer
```

---

## Actualizar

```bash
docker compose pull

docker compose up -d
```

---

## Eliminar

```bash
docker compose down
```

Eliminar también el volumen:

```bash
docker volume rm portainer_data
```
