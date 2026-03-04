# Configuración de usuario

<img src="./images/logo.png" width="120px">

<div style="page-break-before:always"></div>

Es importante antes de comenzar establecer tu nombre de usuario y dirección de correo electrónico, ya que en los _"commits"_ que realicemos se guardará dicha información.

1. Configurar tu nombre de usuario en _Git_:

```bash
$ git config --global user.name "Nombre prueba"
```

2. Configurar tu dirección de correo electrónico:

```bash
$ git config --global user.email prueba@ejemplo.com
```

4. Configurar la rama por defecto a `main`:

```bash
$ git config --global init.defaultBranch main
```

Si quieres comprobar tu configuración, puedes usar el comando:

```bash
$ git config --list
```
