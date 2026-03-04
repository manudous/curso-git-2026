# 01. Setup HTTP: El fin de las contraseñas

El método de "Usuario y Contraseña" por HTTPS fue el estándar durante años por su sencillez, pero hoy es una técnica del pasado.

## 1. El concepto

Al clonar por HTTPS, Git solicita credenciales en cada operación de escritura. Esto es vulnerable a ataques de fuerza bruta y no permite gestionar permisos de forma granular.

## 2. La Evidencia Histórica

Desde el **13 de agosto de 2021**, GitHub bloqueó oficialmente el uso de contraseñas de cuenta para todas las operaciones de Git.

> **🔗 Fuente Oficial:** [GitHub Blog: Support for password authentication was removed](https://github.blog/changelog/2021-08-12-git-password-authentication-is-shutting-down)

### Demostración en clase: Probando el método obsoleto

Vamos a intentar un push con contraseña para ver el error en vivo.

**Paso 0: Configura tu identidad en Git (si no lo has hecho antes)**

```bash
git config --global user.name "Tu Nombre"
git config --global user.email "tu-email@ejemplo.com"
git config --global init.defaultBranch "main"
```

**Paso 1: Clona un repositorio tuyo por HTTPS**

```bash
git clone https://github.com/tu-usuario/tu-repositorio.git
cd tu-repositorio
```

**Paso 2: Haz un cambio cualquiera**

```bash
echo "# Test" >> README.md
git add README.md
git commit -m "Probando push con contraseña"
```

**Paso 3: Intenta hacer push**

```bash
git push origin main
```

**Paso 4: Git te pedirá credenciales**

Git nos pedirá que nos loguemos en github.com.

![Imagen del error de autenticación al usar contraseña]()

Una vez logueados, el push irá bien, pero este método es inseguro y no se recomienda.
