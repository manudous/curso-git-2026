# Curso: Dominando Git y la Conexión con la Nube

<img src="./images/logo.png" width="120px">

<div style="page-break-before:always"></div>

## Introducción

En esta sección vamos a ver como instalar Git, la herramienta de control de versiones más usada del mundo. Y no solo eso, también aprenderás a conectarla con servicios en la nube como GitHub para que puedas trabajar en equipo o guardar tu código de forma segura.

Pero antes de nada, necesitas tener Git instalado en tu máquina. Eso es lo que vamos a hacer ahora mismo.

## Dónde encontrar Git e instalarlo

Abre el navegador y ve a la página oficial de Git:

[Insatalar Git](https://git-scm.com/)

Ahí verás un botón de descarga que ya detecta automáticamente tu sistema operativo. Haz clic y descarga el instalador.

![Descargar Git](./images/download-git-windows.png)

Si estás en **Windows**, ejecuta el instalador que acabas de descargar. Te va a hacer varias preguntas durante la instalación. **Mi recomendación**: deja todas las opciones por defecto y pulsa _Next_ hasta el final. No necesitas cambiar nada.

Al terminar, abre la aplicación **Git Bash** que el instalador habrá dejado en tu sistema. Es una terminal que usaremos durante todo el curso.

![Git Bash](./images/git-bash.png)

Si estás en **Mac**, la forma más sencilla es instalar las **Xcode Command Line Tools**. Abre el Terminal y escribe:

```
xcode-select --install
```

Acepta la ventana que aparece y espera a que termine. Cuando acabe, Git ya estará disponible.

Si prefieres tener la versión más reciente de Git, puedes instalarlo también a través de **Homebrew** con:

```
brew install git
```

---

_[PANTALLA – Linux]_

Si estás en **Linux**, usa el gestor de paquetes de tu distribución. En Ubuntu o Debian:

```
sudo apt install git
```

En Fedora o RHEL:

```
sudo dnf install git
```

---

_[CÁMARA + PANTALLA]_

Una vez instalado, para comprobar que todo ha ido bien, abre tu terminal y escribe:

```
git --version
```

Si te devuelve un número de versión, perfecto. Git está instalado y listo.

---

_[CÁMARA]_

Con esto ya tienes Git en tu máquina. En el siguiente vídeo configuramos Git con tu nombre y tu correo para que queden registrados en cada cambio que hagas.

Nos vemos ahí.

---

## Índice del Curso

1. [Configuración de Usuario](./01-configuracion.md)
2. [Creando un Repositorio Local y en GitHub](./02-creando-repo.md)
3. [Setup HTTP Clásico (User/Pass)](./03-setup-http-clasico.md)
4. [Autenticación Moderna con Token](./04-setup-http-token.md)
5. [Conexión Profesional con SSH](./05-setup-ssh.md)
