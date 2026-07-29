# Solución de problemas

## No carga la interfaz web

### Verificar

```bash
docker ps
```

---

## Revisar logs

```bash
docker logs portainer
```

---

## Puerto ocupado

Verificar:

```bash
sudo ss -tulpn | grep 9443
```

Modificar el puerto en:

```yaml
ports:
  - "9444:9443"
```

---

## Docker Socket

### Error

```text
Cannot connect to Docker daemon
```

### Solución

Verificar el montaje:

```yaml
- /var/run/docker.sock:/var/run/docker.sock
```

---

## Reiniciar

```bash
docker restart portainer
```

---

## Verificar volumen

```bash
docker volume ls
```

Debe existir:

```text
portainer_data
```
