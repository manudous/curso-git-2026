# Setup HTTP Clásico: El fin de las contraseñas

<img src="./images/logo.png" width="120px">

<div style="page-break-before:always"></div>

Durante años, la forma de conectar con GitHub por HTTPS era simple: te pedía tu usuario y tu contraseña de GitHub, los metías, y listo. Tan sencillo que casi todo el mundo empezaba por aquí.

El problema es que esa sencillez tenía un coste de seguridad alto: cualquier persona que consiguiera tu contraseña tenía acceso total a tu cuenta, sin límites. No había forma de dar acceso parcial ni de revocar el acceso a un dispositivo concreto sin cambiar la contraseña de toda la cuenta.

Por eso **desde el 13 de agosto de 2021**, GitHub bloqueó oficialmente este método para siempre.

> **Fuente oficial:** [GitHub Blog - Support for password authentication was removed](https://github.blog/changelog/2021-08-12-git-password-authentication-is-shutting-down)

## Reproduciendo el error

Partimos del repositorio local `mi-proyecto` con el remote ya configurado. Si no lo tienes aún, añádelo:

```bash
git remote add origin https://github.com/tu-usuario/mi-proyecto.git
```

Ahora intentamos hacer push con nuestras credenciales de GitHub:

```bash
git push origin main
```

El sistema abre el diálogo de credenciales. Introducimos usuario y contraseña de GitHub y aceptamos.

GitHub rechaza la operación con este error:

```bash
remote: Support for password authentication was removed on August 13, 2021.
remote: Please see https://docs.github.com/get-started/getting-started-with-git/about-remote-repositories#cloning-with-https-urls
fatal: Authentication failed for 'https://github.com/tu-usuario/mi-proyecto.git/'
```

![Error de autenticación en la terminal](./images/http-auth-error.png)

El método ya no funciona. La buena noticia es que los métodos modernos son igual de fáciles de configurar y mucho más seguros. En los siguientes vídeos vemos los dos que sí funcionan hoy: **token HTTP** y **SSH**.
