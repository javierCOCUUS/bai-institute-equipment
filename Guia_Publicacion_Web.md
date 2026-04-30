# Guía de Publicación: Tu Web en GitHub Pages

Para que tus socios puedan ver el portal desde cualquier dispositivo (móvil, tablet, PC) sin necesidad de enviar archivos, sigue estos pasos sencillos:

## 1. Crear el repositorio en GitHub
1. Entra en [github.com](https://github.com) e inicia sesión.
2. Haz clic en el botón **"New"** (nuevo repositorio).
3. Nombre del repositorio: `BAI-Portal` (o el que prefieras).
4. Déjalo como **Public**.
5. Haz clic en **"Create repository"**.

## 2. Subir tus archivos (Vía Comandos)
Abre una terminal en tu carpeta `c:\demo pista\BAI\BAI_Machinery_Proposal` y ejecuta estos comandos uno a uno:

```powershell
# Inicializar el repositorio local
git init

# Añadir todos los archivos
git add .

# Crear el primer commit
git commit -m "Lanzamiento Portal BAI"

# Conectar con tu cuenta (Cambia 'TU_USUARIO' por tu nombre real de GitHub)
git remote add origin https://github.com/TU_USUARIO/BAI-Portal.git

# Subir los archivos
git branch -M main
git push -u origin main
```

## 3. Activar la Web (GitHub Pages)
1. En la página de tu repositorio en GitHub, ve a la pestaña **Settings** (Arriba a la derecha).
2. En el menú de la izquierda, busca la sección **Pages**.
3. En "Build and deployment", asegúrate de que esté seleccionado:
   - Source: **Deploy from a branch**.
   - Branch: **main** / **(root)**.
4. Haz clic en **Save**.

## 4. ¡Listo!
En un par de minutos, GitHub te dará una dirección parecida a esta:
`https://TU_USUARIO.github.io/BAI-Portal/`

---

### ¿Por qué usar este método?
*   **Profesionalismo**: Puedes enviar el link por WhatsApp o Email y se abre al instante con un diseño interactivo.
*   **Actualización**: Cada vez que cambiemos algo en el código, solo tienes que hacer un `git push` y la web se actualiza sola para todos tus socios.
*   **Gratis**: No pagas ni dominio ni servidor (hosting).

---
**¿Quieres que te ayude a preparar el primer comando o prefieres intentar subirlo tú primero?**
