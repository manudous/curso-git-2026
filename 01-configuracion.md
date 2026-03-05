# Configuración de usuario

<img src="./images/logo.png" width="120px">

<div style="page-break-before:always"></div>

Antes de empezar a trabajar con Git, hay que decirle quién eres. Cada vez que hagas un commit, Git va a guardar tu nombre y tu email junto al cambio. Así cualquier miembro del equipo sabe quién hizo qué.

Son tres comandos que solo ejecutas una vez:

1. Tu nombre de usuario:

```bash
git config --global user.name "Tu Nombre"
```

2. Tu dirección de correo:

```bash
git config --global user.email tu@email.com
```

3. La rama por defecto a `main` (el estándar actual):

```bash
git config --global init.defaultBranch main
```

Para comprobar que todo ha quedado bien guardado:

```bash
git config --list
```

![Salida de git config --list](./images/git-config-list.png)

Con esto ya tienes Git configurado y listo. En el siguiente vídeo vamos a crear nuestro primer repositorio.
