# La vida creativa posthumana · Perpetuo

Página complementaria de la mesa sobre IA, literatura y el futuro (28 oct 2026): los textos de la mesa, las preguntas para seguir la conversación y un formulario para suscribirse a Perpetuo.

## Archivos
- `index.html`: toda la página (HTML, CSS y JS en un solo archivo, sin paso de compilación). Los textos están en `TEXTOS`.
- `assets/`: logo y los cuatro signos de puntuación del brandbook (copiados de `escribe`).
- `Correos.gs`: backend en Apps Script (no se publica; va en script.google.com).
- `CNAME`: `ia.perpetuo.global` para GitHub Pages.

## Backend (Apps Script, sin n8n)
1. En script.google.com, desde perpetuo.revista@gmail.com, crear un proyecto y pegar `Correos.gs`.
2. Ejecutar `instalar()` una vez: crea la hoja **"Mesa IA y literatura · Correos"** y pide los permisos.
3. Implementar → Nueva implementación → Aplicación web · Ejecutar como: yo · Acceso: cualquier usuario.
4. Pegar la URL `/exec` en `CONFIG.WEBHOOK_URL` de `index.html`.

Con `WEBHOOK_URL` vacío, la página funciona en **modo demostración**: no envía nada y muestra en la consola lo que habría enviado.

Cada registro: valida el correo y el consentimiento, no repite correos, intenta el alta directa en Substack (si falla, la columna dice "pendiente" para importarlo a mano), manda la lista de textos si la persona lo pidió y anota todo en la hoja.
