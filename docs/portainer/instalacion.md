# Instalación de Portainer

## Objetivo

Desplegar Portainer CE utilizando Docker Compose.

---

## Crear directorio

```bash
mkdir -p ~/docker/portainer
cd ~/docker/portainer
```

---

## Crear docker-compose.yml

```yaml
services:

  portainer:
    image: portainer/portainer-ce:latest
    container_name: portainer

    restart: unless-stopped

    ports:
      - "8000:8000"
      - "9443:9443"

    volumes:
      - /var/run/docker.sock:/var/run/docker.sock
      - portainer_data:/data

volumes:

  portainer_data:
```

---

## Desplegar

```bash
docker compose up -d
```

---

## Verificar

```bash
docker ps
```

Debe existir un contenedor llamado:

```text
portainer
```

---

## Acceder

```.
 https://IP_DEL_SERVIDOR:9443
```

Al primer acceso se solicita crear el usuario administrador.
