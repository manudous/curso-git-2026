# Curso: Dominando Git y la Conexión con la Nube

<img src="./images/logo.png" width="120px">

<div style="page-break-before:always"></div>

## Introducción

En el vídeo anterior vimos que las contraseñas de GitHub ya no funcionan para autenticarse desde la terminal. La alternativa más sencilla por HTTPS son los **Personal Access Tokens**, o PAT. Son básicamente contraseñas técnicas que genera GitHub, con permisos y caducidad que tú controlas.

Vamos a ver cómo generarlo y cómo usarlo.

## ¿Qué ventajas tiene un token frente a una contraseña?

Antes de ponernos manos a la obra, merece la pena entender por qué esto es mejor:

- **Scope limitado:** puedes darle permisos solo para repositorios, sin acceso al resto de tu cuenta.
- **Caducidad:** se puede configurar para que expire automáticamente.
- **Revocable:** si se compromete, lo borras y generas uno nuevo sin tocar tu contraseña principal.

## Generando el token en GitHub

Entra en [github.com](https://github.com), haz clic en tu avatar arriba a la derecha y selecciona **Settings**.

![Menú de usuario en GitHub](./images/github-settings-menu.png)

Baja hasta el final del menú lateral izquierdo y haz clic en **Developer settings**.

![Developer settings en el menú lateral](./images/github-developer-settings.png)

En el menú izquierdo selecciona **Personal access tokens** > **Tokens (classic)**.

![Sección Personal access tokens](./images/github-pat-menu.png)

Haz clic en **Generate new token** > **Generate new token (classic)**.

![Botón Generate new token](./images/github-generate-token.png)

Rellena los campos:

- **Note:** un nombre descriptivo, por ejemplo `curso-git`.
- **Expiration:** el tiempo que quieres que dure. Para el curso puedes poner 30 días.
- **Scopes:** marca **`repo`** (da acceso completo a repositorios públicos y privados).

![Configuración del token: nombre, expiración y scopes](./images/github-token-config.png)

Haz clic en **Generate token**. GitHub te mostrará el token **una sola vez**. Cópialo ahora porque no volverás a verlo.

![Token generado, copiar antes de salir](./images/github-token-copy.png)

## Limpiando las credenciales anteriores

Antes de probarlo, tenemos que borrar las credenciales que puedas tener guardadas de GitHub. Si no lo hacemos, el sistema usará las antiguas y no te pedirá el token.

En **Windows**, abre el **Administrador de credenciales** y elimina cualquier entrada relacionada con GitHub.

![Administrador de credenciales de Windows](./images/windows-credential-manager.png)

![Eliminar credenciales de GitHub](./images/delete-github-credential.png)

En **Mac**, abre **Acceso a Llaveros** y haz lo mismo.

## Usando el token para hacer push

Partimos del repositorio `mi-proyecto` con el remote ya configurado. Si no lo tienes, añádelo:

```bash
git remote add origin https://github.com/tu-usuario/mi-proyecto.git
```

Hacemos push:

```bash
git push origin main
```

Se abrirá un diálogo para introducir las credenciales.

![Diálogo de credenciales](./images/github-token-prompt.png)

Introducimos el token que acabamos de generar y hacemos clic en **Sign in**. Si todo está bien, veremos el mensaje de éxito en la terminal:

```bash
Enumerating objects: 5, done.
Counting objects: 100% (5/5), done.
Delta compression using up to 16 threads
Compressing objects: 100% (3/3), done.
Writing objects: 100% (3/3), 289 bytes | 289.00 KiB/s, done.
Total 3 (delta 1), reused 0 (delta 0), pack-reused 0 (from 0)
remote: Resolving deltas: 100% (1/1), completed with 1 local object.
To https://github.com/tu-usuario/mi-proyecto.git
   871fcff..7013a5f  main -> main
```

El repositorio local ya está sincronizado con GitHub.

---

Este método funciona y es sencillo, pero tiene una pega: el token caduca y tienes que renovarlo. Si buscas algo más cómodo y profesional, el siguiente vídeo es para ti: vamos a ver cómo conectar con SSH, que una vez configurado no te vuelve a pedir nada.

Nos vemos ahí.

---
