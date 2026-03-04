### 📂 Archivo 4: `03-setup-ssh.md`

**Contenido:** Configuración profesional con criptografía asimétrica.

````markdown
# 03. Setup SSH: Seguridad Profesional

SSH (Secure Shell) es el método preferido en la industria porque utiliza **criptografía asimétrica**. No envías secretos por la red; solo demuestras que tienes la llave.

## 1. El Concepto de Llave Pública y Privada

- **Llave Privada (`id_ed25519`):** Se queda en tu PC. Es tu firma.
- **Llave Pública (`id_ed25519.pub`):** Se sube a GitHub. Es el candado.

## 2. Generación (Paso a paso)

Usaremos el algoritmo **Ed25519**, más eficiente y seguro que RSA.

```bash
# 1. Generar la llave (Enter a todo)
ssh-keygen -t ed25519 -C "tu-email@ejemplo.com"

# 2. Iniciar el agente de llaves
eval "$(ssh-agent -s)"
ssh-add ~/.ssh/id_ed25519
```
````
