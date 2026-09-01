# Instalación de Docker Engine

## Objetivo

Instalar Docker Engine y Docker Compose Plugin desde el repositorio oficial de Docker sobre Ubuntu Server.

---

## Actualizar el sistema

```bash
sudo apt update
sudo apt upgrade -y
```

---

## Instalar dependencias

```bash
sudo apt install -y ca-certificates curl gnupg
```

---

## Crear el directorio para las llaves GPG

```bash
sudo install -m 0755 -d /etc/apt/keyrings
```

---

## Descargar la llave GPG

```bash
curl -fsSL https://download.docker.com/linux/ubuntu/gpg | \
sudo gpg --dearmor -o /tmp/docker.gpg
```

---

## Verificar el fingerprint

```bash
gpg --show-keys --fingerprint /tmp/docker.gpg
```

Comparar el fingerprint obtenido con el publicado en la documentación oficial de Docker.

Si coincide, continuar con la instalación.

---

## Instalar la llave

```bash
sudo mv /tmp/docker.gpg /etc/apt/keyrings/docker.gpg
```

Asignar permisos de lectura:

```bash
sudo chmod a+r /etc/apt/keyrings/docker.gpg
```

---

## Agregar el repositorio oficial

```bash
echo \
"deb [arch=$(dpkg --print-architecture) signed-by=/etc/apt/keyrings/docker.gpg] \
https://download.docker.com/linux/ubuntu \
$(. /etc/os-release && echo "$VERSION_CODENAME") stable" | \
sudo tee /etc/apt/sources.list.d/docker.list > /dev/null
```

---

## Actualizar la lista de paquetes

```bash
sudo apt update
```

---

## Instalar Docker Engine

```bash
sudo apt install -y \
docker-ce \
docker-ce-cli \
containerd.io \
docker-buildx-plugin \
docker-compose-plugin
```

---

## Verificar la instalación

Versión de Docker:

```bash
docker --version
```

Versión de Docker Compose:

```bash
docker compose version
```

Estado del servicio:

```bash
sudo systemctl status docker
```

---

## Habilitar Docker al iniciar el sistema

```bash
sudo systemctl enable docker
```

---

## Agregar el usuario al grupo Docker

```bash
sudo usermod -aG docker $USER
```

Aplicar los cambios:

```bash
newgrp docker
```

Verificar permisos:

```bash
docker ps
```

---

## Prueba de funcionamiento

Descargar y ejecutar el contenedor de prueba:

```bash
docker run hello-world
```

La ejecución correcta confirma que:

- Docker Engine está instalado.
- El daemon está en ejecución.
- El usuario puede ejecutar contenedores.
- La comunicación con Docker Hub funciona correctamente.
