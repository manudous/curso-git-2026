### 📂 Archivo 3: `02-setup-http-token.md`

**Contenido:** Guía paso a paso para generar y usar Tokens (PAT).

````markdown
# 02. Setup HTTP: Personal Access Tokens (PAT)

Para solucionar el problema de seguridad del Módulo 1, los servidores Git implementaron los **Tokens**.

## 1. ¿Qué es un Token?

Es una contraseña técnica autogenerada. A diferencia de tu clave web:

- **Tiene caducidad:** Puedes configurarlo para que expire en 30 días.
- **Tiene Scopes:** Puedes limitar que solo sirva para leer código, pero no para borrar la cuenta.

## 2. Paso a Paso (GitHub)

1. Ve a **Settings** > **Developer settings**.
2. **Personal access tokens** > **Tokens (classic)**.
3. **Generate new token (classic)**.
4. Dale un nombre (ej: "Clase de FP") y marca el scope **`repo`**.
5. **Copia el token inmediatamente.** GitHub no te lo volverá a mostrar nunca más.

## 3. Uso y Persistencia

Cuando la terminal pida `Password`, pega el Token. Para que no te lo pida en cada comando, usa el gestor de credenciales:

```bash
# Para Windows/Mac/Linux
git config --global credential.helper store
```
````
