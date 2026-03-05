# Curso: Dominando Git y la Conexión con la Nube

<img src="./images/logo.png" width="120px">

<div style="page-break-before:always"></div>

## Introducción

El método con token funciona, pero tiene una pega: caduca. Cuando eso pasa, tienes que volver a generarlo y actualizarlo. No es dramático, pero hay una forma mejor.

SSH es el método que usan los equipos profesionales. Una vez configurado, no vuelve a pedirte nada. Haces push y listo. Y encima es más seguro: en lugar de enviar un token por la red, usas **criptografía asimétrica** para demostrar que eres tú sin revelar nunca nada secreto.

## ¿Cómo funciona SSH?

La idea es sencilla. Se generan dos ficheros vinculados matemáticamente:

- **Llave privada** (`id_ed25519`): se queda en tu máquina. Nunca la compartas.
- **Llave pública** (`id_ed25519.pub`): se sube a GitHub. Es el candado que solo tu llave abre.

Cuando haces un `push`, SSH demuestra criptográficamente que tienes la llave privada correspondiente al candado registrado en GitHub. Sin contraseñas, sin tokens, sin que nada secreto viaje por la red.

## Generando las llaves SSH

Antes de generar nada, comprueba si ya tienes un par de llaves:

```bash
ls ~/.ssh
```

Si ves ficheros `id_ed25519` e `id_ed25519.pub` ya las tienes y puedes saltar al siguiente apartado. Si la carpeta no existe o está vacía, continúa.

Usamos el algoritmo **Ed25519**, más moderno y seguro que RSA:

```bash
ssh-keygen -t ed25519 -C "tu-email@ejemplo.com"
```

El comando te hará dos preguntas:

- **Ruta donde guardar la llave:** pulsa Enter para aceptar la ruta por defecto (`~/.ssh/id_ed25519`).
- **Passphrase:** una contraseña opcional para proteger la llave privada. Puedes dejarla vacía pulsando Enter dos veces.

![Interacción del comando ssh-keygen en la terminal](./images/ssh-keygen-output.png)

Ahora arrancamos el agente SSH y añadimos la llave. El agente es un proceso que gestiona tus llaves en memoria para no tener que reintroducir la passphrase en cada operación:

```bash
eval "$(ssh-agent -s)"
ssh-add ~/.ssh/id_ed25519
```

```bash
Agent pid 12345
Identity added: /home/usuario/.ssh/id_ed25519 (tu-email@ejemplo)
```

## Añadiendo la llave pública a GitHub

Copiamos el contenido de la llave pública:

```bash
cat ~/.ssh/id_ed25519.pub
```

Copia todo el texto que aparece (empieza por `ssh-ed25519` y termina con tu email).

Entramos en [github.com](https://github.com), hacemos clic en el avatar y seleccionamos **Settings**.

![Menú de usuario en GitHub](./images/github-settings-menu.png)

En el menú lateral izquierdo hacemos clic en **SSH and GPG keys**.

![Sección SSH and GPG keys](./images/github-ssh-menu.png)

Hacemos clic en **New SSH key**.

![Botón New SSH key](./images/github-new-ssh-key.png)

Rellenamos los campos:

- **Title:** un nombre descriptivo, por ejemplo `pc-personal`.
- **Key type:** `Authentication Key` (valor por defecto).
- **Key:** pegamos aquí el contenido de `id_ed25519.pub` que copiamos antes.

Hacemos clic en **Add SSH key**.

![Formulario para añadir la llave SSH](./images/github-ssh-form.png)

GitHub confirma que la llave se ha añadido correctamente.

![Llave SSH añadida en GitHub](./images/github-ssh-added.png)

## Verificando la conexión

Antes de hacer el primer push, comprobamos que todo funciona:

```bash
ssh -T git@github.com
```

Si es la primera vez que te conectas a GitHub por SSH, verás un mensaje preguntando si confías en el servidor. Es normal, no es un error. Escribe `yes` y pulsa Enter.

![Warning de autenticidad del host al conectar por SSH por primera vez](./images/ssh-host-warning.png)

La respuesta correcta es:

```bash
Hi tu-usuario! You've successfully authenticated, but GitHub does not provide shell access.
```

## Haciendo push por SSH

Aquí hay un detalle importante. SSH usa una URL diferente a HTTPS, así que da igual si el token sigue guardado en el gestor de credenciales: nunca va a entrar en juego cuando el remote apunta a una dirección SSH.

Cambiamos la URL del remote para que use SSH en lugar de HTTPS:

```bash
git remote set-url origin git@github.com:tu-usuario/mi-proyecto.git
```

Si aún no tienes el remote configurado:

```bash
git remote add origin git@github.com:tu-usuario/mi-proyecto.git
```

Y ahora hacemos push. Verás que no pide nada:

```bash
git push origin main
```

```bash
Enumerating objects: 5, done.
Counting objects: 100% (5/5), done.
Delta compression using up to 16 threads
Compressing objects: 100% (3/3), done.
Writing objects: 100% (3/3), 288 bytes | 288.00 KiB/s, done.
Total 3 (delta 1), reused 0 (delta 0), pack-reused 0 (from 0)
remote: Resolving deltas: 100% (1/1), completed with 1 local object.
To github.com:tu-usuario/mi-proyecto.git
   7013a5f..acdb4f7  main -> main
```

Sin contraseñas, sin tokens, sin interrupciones.

---

Y con esto terminamos esta sección. Ahora tienes Git instalado, configurado, y sabes conectarlo con GitHub de tres formas distintas. Elige la que mejor se adapte a tu flujo de trabajo, aunque si me preguntas a mí, quédate con SSH.

---
