# SlideStudio

Editor web de presentaciones en español, inspirado en imágenes de referencia. Funciona sin servidor, API de pago ni conexión una vez descargados los archivos.

## Uso local

Extrae el ZIP completo y abre `index.html` en Chrome, Edge o Firefox moderno. Conserva las carpetas y los archivos juntos. No requiere Node.js.

1. Carga una imagen PNG, JPG o WebP. El programa calcula una paleta dominante, estima fondo, contraste y distribución visual, y propone un estilo y diseño.
2. Escribe el tema, elige el número de diapositivas y pulsa **Crear presentación**. Se genera una estructura inicial editable con textos guía.
3. Ajusta fuentes, tamaños, colores y estilo en el panel izquierdo. Selecciona el diseño por diapositiva y edita textos en el panel derecho. Añade imágenes propias.
4. Agrega, duplica, elimina y reordena diapositivas. Pulsa **Presentar** para revisar a pantalla completa; usa las flechas del teclado.
5. Pulsa **PowerPoint editable** para obtener un `.pptx` con texto, formas e imágenes como objetos separados. Pulsa **Guardar proyecto** para conservar un JSON que puedes volver a abrir en la aplicación.

## Publicación en GitHub Pages

1. Entra en https://github.com/new y crea un repositorio público llamado `slidestudio`.
2. En el repositorio, usa **Add file → Upload files**. Sube el contenido de la carpeta SlideStudio (no el ZIP) al directorio raíz, manteniendo la carpeta `vendor`. Confirma con **Commit changes**. Alternativamente, desde el directorio extraído:

```bash
git init
git add .
git commit -m "Publicar SlideStudio"
git branch -M main
git remote add origin https://github.com/TU-USUARIO/slidestudio.git
git push -u origin main
```

3. En **Settings → Pages**, selecciona **Deploy from a branch**, rama `main`, carpeta `/ (root)`, y guarda.
4. Cuando GitHub indique que finalizó la publicación, la dirección tendrá la forma `https://TU-USUARIO.github.io/slidestudio/`.

## Alcance y limitaciones

- El análisis de la imagen es local y heurístico, no un modelo generativo: no reconoce con exactitud tipografías ni reconstruye objetos o textos de una captura. La composición y paleta son aproximadas y editables.
- Los textos iniciales son una plantilla temática para completar manualmente, sin generación de contenido factual ni conexión con IA.
- Las tipografías dependen de las instaladas en el equipo y PowerPoint; no se incrustan fuentes.
- La vista previa HTML y PowerPoint pueden diferir en saltos de línea y ajuste de texto. Evita textos demasiado extensos.
- No se guarda automáticamente: descarga el proyecto JSON antes de cerrar la pestaña.
- Formato 16:9. Generador inicial de 1 a 30 diapositivas, editor hasta 100.
- PptxGenJS se incluye localmente en `vendor/` con su licencia. No hay dependencias de CDN.
