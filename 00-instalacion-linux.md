# Curso: Dominando Git y la Conexión con la Nube

<img src="./images/logo.png" width="120px">

<div style="page-break-before:always"></div>

---

> **[INSTRUCTOR — no grabar]**
>
> Pasos para simular un Ubuntu limpio con Docker antes de grabar:
>
> ```bash
> # Descargar la imagen de Ubuntu
> docker pull ubuntu
>
> # Crear y arrancar el contenedor con nombre
> docker run -it --name ubuntu-git ubuntu
>
> # El prompt cambia a algo como: root@a3f2c1b4d5e6:/#
> # Ya estás dentro del contenedor, simula una máquina Ubuntu limpia
> ```
>
> Para salir y volver a entrar en otra sesión:
>
> ```bash
> exit                              # salir y detener el contenedor
> docker start ubuntu-git           # arrancarlo de nuevo
> docker exec -it ubuntu-git bash   # abrir sesión interactiva
> ```

---

## Introducción

Bienvenido al curso. En este vídeo vemos cómo instalar Git en **Linux**, concretamente en Ubuntu. El proceso es muy sencillo: dos comandos y listo.

## Instalando Git

Abre el terminal y primero actualiza la lista de paquetes disponibles:

```bash
apt update
```

Y luego instala Git:

```bash
apt install git -y
```

## Verificando la instalación

Una vez terminada la instalación, escribe:

```bash
git --version
```

Si te devuelve un número de versión, perfecto. Git está instalado y listo.

```bash
git version 2.43.0
```

> **Nota:** En otras distribuciones el comando cambia ligeramente. En **Fedora o RHEL** usa `sudo dnf install git`. La idea es la misma: usar el gestor de paquetes de tu distribución.

---

Con esto ya tienes Git en tu máquina. En el siguiente vídeo configuramos Git con tu nombre y tu correo para que queden registrados en cada cambio que hagas.

Nos vemos ahí.

---
