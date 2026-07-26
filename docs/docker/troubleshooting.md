# Solución de problemas

## Docker no encuentra paquetes

### Error

```text
Package 'docker-ce' has no installation candidate
Unable to locate package containerd.io
```

### Causa

La versión de Ubuntu no cuenta con soporte oficial en el repositorio de Docker.

### Diagnóstico

Verificar versión del sistema.

```bash
cat /etc/os-release
```

Verificar el repositorio.

```bash
cat /etc/apt/sources.list.d/docker.list
```

### Solución

Mientras Docker publique soporte para la nueva versión, utilizar temporalmente el repositorio de Ubuntu 24.04 (Noble).

Editar:

```bash
sudo nano /etc/apt/sources.list.d/docker.list
```

Cambiar:

```text
resolute
```

por

```text
noble
```

Actualizar:

```bash
sudo apt update
```

---

## Error "STABLE"

### Error

```text
Skipping acquire of configured file 'STABLE/...'
```

### Causa

El componente del repositorio fue escrito en mayúsculas.

### Solución

Editar:

```bash
sudo nano /etc/apt/sources.list.d/docker.list
```

Debe finalizar con:

```text
stable
```

No:

```text
STABLE
```

Actualizar:

```bash
sudo apt update
```

---

## Permission denied

### Error

```text
permission denied while trying to connect to the Docker daemon socket
```

### Solución

```bash
sudo usermod -aG docker $USER
newgrp docker
```

---

## Docker no inicia

Verificar:

```bash
sudo systemctl status docker
```

Reiniciar:

```bash
sudo systemctl restart docker
```

---

## Verificar repositorio

```bash
cat /etc/apt/sources.list.d/docker.list
```

---

## Verificar versión de Ubuntu

```bash
cat /etc/os-release
```

---

## Verificar arquitectura

```bash
dpkg --print-architecture
```
