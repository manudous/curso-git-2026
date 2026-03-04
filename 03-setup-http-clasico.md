# Setup HTTP Clásico: El fin de las contraseñas

<img src="./images/logo.png" width="120px">

<div style="page-break-before:always"></div>

El método de _"Usuario y Contraseña"_ por HTTPS fue el estándar durante años por su sencillez, pero hoy es una técnica del pasado.

## El concepto

Al conectar con GitHub por HTTPS, Git solicitaba las credenciales de tu cuenta en cada operación de escritura. Esto tenía varios problemas:

- Vulnerable a ataques de fuerza bruta.
- No permite gestionar permisos de forma granular.
- Cualquier persona con tu contraseña tiene acceso total a tu cuenta.

## La evidencia histórica

Desde el **13 de agosto de 2021**, GitHub bloqueó oficialmente el uso de contraseñas de cuenta para todas las operaciones de Git.

> **Fuente oficial:** [GitHub Blog - Support for password authentication was removed](https://github.blog/changelog/2021-08-12-git-password-authentication-is-shutting-down)

## Reproduciendo el error

Partimos del repositorio local que creamos en el paso anterior (`mi-proyecto`) y del repositorio vacío que ya creamos en GitHub.

### 1. Vinculamos el repo local con el remoto

```bash
git remote add origin https://github.com/tu-usuario/mi-proyecto.git
```

### 2. Intentamos hacer push metiendo las credenciales en la URL

La forma más directa de forzar el método clásico es incluir usuario y contraseña directamente en la URL. Así evitamos que el gestor de credenciales del sistema interfiera:

```bash
git push https://tu-usuario:tu-contraseña@github.com/tu-usuario/mi-proyecto.git main
```

> Sustituye `tu-usuario` y `tu-contraseña` por los datos reales de tu cuenta de GitHub.

### 3. El error

GitHub rechaza la operación y devuelve este mensaje:

```bash
remote: Invalid username or token. Password authentication is not supported for Git operations.
fatal: Authentication failed for 'https://github.com/tu-usuario/mi-proyecto.git/'
```

Queda demostrado que este método ya no funciona. Por eso necesitamos métodos de autenticación modernos: **token HTTP** o **SSH**, que veremos en los siguientes apartados.
