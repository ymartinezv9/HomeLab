# Configuración

## Habilitar el servicio

```bash
sudo systemctl enable docker
sudo systemctl start docker
```

---

## Verificar estado

```bash
sudo systemctl status docker
```

---

## Agregar usuario al grupo Docker

```bash
sudo usermod -aG docker $USER
```

Aplicar cambios:

```bash
newgrp docker
```

Verificar permisos:

```bash
docker ps
```

---

## Ejecutar contenedor de prueba

```bash
docker run hello-world
```

Una instalación correcta confirma:

- Docker Engine instalado.
- Docker Compose instalado.
- Docker Daemon funcionando.
- Acceso del usuario al daemon.
- Conectividad con Docker Hub.
