# Curso: Dominando Git y la Conexión con la Nube

<img src="./images/logo.png" width="120px">

<div style="page-break-before:always"></div>

## Introducción

Bienvenido al curso. Antes de empezar a trabajar con Git, necesitas tenerlo instalado en tu máquina. En este vídeo vemos cómo hacerlo en **Mac**.

La forma más sencilla y recomendada en Mac es usar **Homebrew**, el gestor de paquetes más popular para macOS. Si ya lo tienes instalado, perfecto. Si no, lo instalamos primero.

## Instalando Homebrew

Abre el Terminal y ejecuta este comando:

```bash
/bin/bash -c "$(curl -fsSL https://raw.githubusercontent.com/Homebrew/install/HEAD/install.sh)"
```

El script te pedirá la contraseña de tu usuario y se encargará de todo. Cuando termine, comprueba que se ha instalado correctamente:

```bash
brew --version
```

## Instalando Git

Con Homebrew listo, instalar Git es un solo comando:

```bash
brew install git
```

## Verificando la instalación

Una vez terminada la instalación, escribe en el Terminal:

```bash
git --version
```

Si te devuelve un número de versión, perfecto. Git está instalado y listo.

```bash
git version 2.43.0
```

> **Nota:** Mac incluye una versión antigua de Git por defecto. Usando Homebrew te aseguras de tener la versión más reciente.

---

Con esto ya tienes Git en tu Mac. En el siguiente vídeo configuramos Git con tu nombre y tu correo para que queden registrados en cada cambio que hagas.

Nos vemos ahí.

---
