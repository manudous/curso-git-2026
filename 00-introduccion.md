# Curso: Dominando Git y la Conexión con la Nube

<img src="./images/logo.png" width="120px">

<div style="page-break-before:always"></div>

Este curso está diseñado para entender la evolución del control de versiones, desde el envío de archivos por correo hasta la seguridad criptográfica moderna.

## 1. Introducción

Hace años, el control de versiones consistía en guardar archivos en local, pasarlos por USB, correo electrónico o subirlos a servidores FTP. Esto generaba problemas críticos:

- **Sobrescritura:** Un compañero borraba el trabajo de otro.
- **Inconsistencia:** No se sabía cuál era la "versión final".
- **Imposibilidad de auditar:** No sabíamos quién cambió qué, ni cuándo.

A finales de los 90 nació **CVS**, pero el gran salto llegó con los **Sistemas Distribuidos**.

## 2. Sistema de Versiones Distribuido

En Git, cada desarrollador tiene una copia **completa** del código y su historial.

- **Ventaja:** Si el servidor central falla, cualquier copia local sirve para restaurarlo.
- **Desventaja:** Mayor curva de aprendizaje y complejidad en la sincronización.

## 3. ¿Qué es Git?

Creado por **Linus Torvalds** (padre de Linux) en 2005. Se diseñó para ser rápido, simple y capaz de manejar miles de ramas en paralelo.

### Estados de los ficheros

Para entender Git, hay que dominar el ciclo de vida de un archivo:

1. **Untracked:** Git no lo conoce aún.
2. **Modified:** Has cambiado el archivo pero no has guardado la "foto".
3. **Staged:** El archivo está preparado en el área de preparación.
4. **Committed:** El cambio ya es parte de la base de datos local.

[Image of Git lifecycle states: untracked, modified, staged, committed]

---

## Índice del Curso

1. [Configuración de Usuario](./01-configuracion.md)
2. [Creando un Repositorio Local y en GitHub](./02-creando-repo.md)
3. [Setup HTTP Clásico (User/Pass)](./03-setup-http-clasico.md)
4. [Módulo 2: Autenticación Moderna con Token](./04-setup-http-token.md)
5. [Módulo 3: Conexión Profesional con SSH](./03-setup-ssh.md)
