# Curso: Dominando Git y la Conexión con la Nube

<img src="./images/logo.png" width="120px">

<div style="page-break-before:always"></div>

## Introducción

Antes de empezar a trabajar con Git, hay una cosa que tienes que hacer sí o sí: decirle quién eres. Cada vez que hagas un commit, Git va a guardar tu nombre y tu email junto al cambio. Así cualquier miembro del equipo sabe quién hizo qué. Y si trabajas solo, también queda un registro limpio de tu trabajo.

Son tres comandos que solo ejecutas una vez, y en este vídeo los vemos juntos.

## Configurando tu identidad en Git

Abre el terminal y escribe estos tres comandos:

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

Una vez hecho esto, para comprobar que todo ha quedado bien guardado, ejecuta:

```bash
git config --list
```

Verás una lista con toda tu configuración. Ahí tienen que aparecer tu nombre, tu email y la rama por defecto.

```bash
user.name=Tu Nombre
user.email=Tu email
init.defaultbranch=main
```

---

Con esto ya tienes Git configurado y listo para trabajar. En el siguiente vídeo vamos a crear nuestro primer repositorio, tanto en local como en GitHub.

Nos vemos ahí.

---

## Índice del Curso

1. [Configuración de Usuario](./01-configuracion.md)
2. [Creando un Repositorio Local y en GitHub](./02-creando-repo.md)
3. [Setup HTTP Clásico (User/Pass)](./03-setup-http-clasico.md)
4. [Autenticación Moderna con Token](./04-setup-http-token.md)
5. [Conexión Profesional con SSH](./05-setup-ssh.md)

```

```
