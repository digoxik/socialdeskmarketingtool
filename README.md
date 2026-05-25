# SocialDesk — Digital Marketing Tool

Herramienta de gestión de contenido y SEO para digital marketers. Un único archivo HTML que funciona en cualquier navegador, sin instalación ni servidor.

---

## 📦 Contenido del repositorio

```
socialdesk/
└── index.html     ← Toda la aplicación en un solo archivo
└── README.md      ← Este manual
```

---

## 🚀 Cómo subir la herramienta a GitHub y publicarla online

### Paso 1 — Crea una cuenta en GitHub
Si no tienes cuenta, regístrate gratis en [github.com](https://github.com).

### Paso 2 — Crea un repositorio nuevo
1. Haz clic en el botón verde **"New"** o en el **"+"** de la esquina superior derecha.
2. Ponle un nombre, por ejemplo: `socialdesk`
3. Déjalo en **Public** (necesario para GitHub Pages gratuito).
4. Marca la casilla **"Add a README file"** (o no, da igual porque ya tienes uno).
5. Haz clic en **"Create repository"**.

### Paso 3 — Sube los archivos
Una vez dentro del repositorio:
1. Haz clic en **"Add file" → "Upload files"**.
2. Arrastra el archivo `index.html` y el `README.md` a la zona de subida.
3. Escribe un mensaje en "Commit changes", por ejemplo: `Primera versión de SocialDesk`.
4. Haz clic en **"Commit changes"**.

### Paso 4 — Activa GitHub Pages
1. Ve a **Settings** (pestaña de configuración del repositorio).
2. En el menú lateral izquierdo, haz clic en **"Pages"**.
3. En la sección **"Branch"**, selecciona `main` y la carpeta `/ (root)`.
4. Haz clic en **"Save"**.
5. Espera 1-2 minutos. GitHub te mostrará una URL del tipo:
   ```
   https://tuusuario.github.io/socialdesk
   ```
6. Abre esa URL en cualquier navegador. ¡Ya está publicada!

> 💡 **Importante:** Los datos se guardan en el navegador donde uses la herramienta (localStorage). Si abres la URL en otro navegador o dispositivo, los datos no se sincronizan automáticamente. Puedes usar la función **Exportar / Importar datos** en Configuración para hacer copias de seguridad.

---

## 🤖 Configurar la IA

Al abrir la herramienta por primera vez, ve a **Configuración** en el menú lateral.

Verás 4 opciones de proveedor de IA:

| Proveedor | Coste | Velocidad | Calidad |
|-----------|-------|-----------|---------|
| **Google Gemini Flash** | ✅ Gratis | ⚡ Rápido | ⭐⭐⭐⭐ |
| **Groq (LLaMA 3)** | ✅ Gratis | ⚡⚡ Muy rápido | ⭐⭐⭐ |
| **OpenRouter** | ✅ Modelos gratuitos | ⚡ Rápido | ⭐⭐⭐ |
| **Anthropic Claude** | 💳 De pago | ⚡ Rápido | ⭐⭐⭐⭐⭐ |

### Cómo obtener tu API key gratuita (Gemini — recomendado)
1. Ve a [aistudio.google.com](https://aistudio.google.com).
2. Inicia sesión con tu cuenta de Google.
3. Haz clic en **"Get API key"** → **"Create API key"**.
4. Copia la key generada.
5. En SocialDesk → Configuración, selecciona **Google Gemini Flash**, pega la key y guarda.

### Cómo obtener tu API key gratuita (Groq)
1. Ve a [console.groq.com](https://console.groq.com).
2. Crea una cuenta gratuita.
3. Ve a **API Keys** → **"Create API Key"**.
4. Copia la key y pégala en SocialDesk → Configuración → Groq.

### Cambiar de proveedor de IA
En cualquier momento puedes ir a **Configuración**, seleccionar otro proveedor, pegar la nueva API key y guardar. El cambio es inmediato.

---

## ✏️ Cómo modificar la herramienta

Toda la aplicación vive en el archivo `index.html`. Para modificarla:

### Herramienta recomendada: Visual Studio Code (gratis)
Descárgalo en [code.visualstudio.com](https://code.visualstudio.com).

### Estructura del archivo

El `index.html` está organizado en estas secciones claramente marcadas con comentarios:

```
<style>          → Todos los estilos visuales (colores, tipografía, layout)
</style>

<!-- HTML -->     → La interfaz: sidebar, páginas, modales

<script>
  // AI ENGINE   → Adaptador multi-proveedor de IA (callAI)
  // STATE       → Carga y guardado de datos (localStorage)
  // SETTINGS    → Configuración de la herramienta
  // DASHBOARD   → Estadísticas y resumen
  // CLIENTS     → Gestión de clientes y fichas
  // SEO TOOLS   → Todas las herramientas SEO (keywords, metas, contenido...)
  // CHECKLIST   → Checklist SEO con puntuación
  // COPY        → Generador de captions y hashtags
  // BRIEF       → Generador de brief visual
  // IDEAS       → Banco de ideas
  // CALENDAR    → Calendario editorial
  // UTILS       → Funciones auxiliares
</script>
```

### Cambios visuales frecuentes

**Cambiar colores:** Busca la sección `:root` al inicio del `<style>`. Ahí están todas las variables de color:
```css
:root {
  --accent: #c8a96e;    /* Color dorado principal */
  --accent3: #5fb89a;   /* Color verde (SEO) */
  --accent2: #8b6fd4;   /* Color morado */
  --danger: #e06060;    /* Color rojo */
  --bg: #0e0e0f;        /* Fondo oscuro principal */
}
```

**Cambiar el nombre de la herramienta:** Busca `SocialDesk` en el HTML y cámbialo por el nombre que quieras.

**Añadir un nuevo tono de voz:** En el modal de cliente, busca el `<select id="c-tone">` y añade un `<option>` nuevo.

**Añadir ítems al checklist SEO:** Busca `const CHECKLISTS` en el script y añade ítems a los arrays correspondientes.

### Subir cambios a GitHub
Después de modificar el archivo:
1. Ve a tu repositorio en GitHub.
2. Haz clic en el archivo `index.html`.
3. Haz clic en el lápiz ✏️ (editar) — o arrastra el archivo nuevo con **"Add file → Upload files"**.
4. Confirma los cambios con **"Commit changes"**.
5. En 1-2 minutos la URL de GitHub Pages se actualiza automáticamente.

---

## 💾 Copias de seguridad

Los datos se guardan en el navegador. Para no perderlos:

1. Ve a **Configuración → Exportar datos (JSON)**.
2. Guarda el archivo `socialdesk-backup.json` en un lugar seguro (Google Drive, etc.).
3. Para restaurar, usa **Importar datos** y selecciona el archivo.

> ⚠️ Si limpias el caché del navegador o usas el modo incógnito, los datos se borran. Haz exportaciones periódicas.

---

## ❓ Preguntas frecuentes

**¿Puedo usar la herramienta sin internet?**
La herramienta funciona sin internet excepto las llamadas a la IA, que siempre necesitan conexión.

**¿Mis datos son privados?**
Sí. Los datos de clientes, ideas y calendario se guardan solo en tu navegador. Solo se envía a internet el texto que introduces en las herramientas de IA, y únicamente al proveedor que hayas configurado.

**¿Puedo usarla en el móvil?**
Sí. Abre la URL de GitHub Pages desde el navegador de tu móvil. La interfaz se adapta, aunque está optimizada para escritorio.

**¿Puedo compartirla con mi equipo?**
La URL de GitHub Pages es pública y cualquiera puede abrirla. Sin embargo, cada persona tendrá sus propios datos locales. Para trabajo en equipo real necesitarías una solución con base de datos en servidor.

---

## 📬 Soporte

Esta herramienta fue desarrollada como proyecto personal. Para modificaciones o nuevas funciones, edita el `index.html` directamente o consulta con Claude en [claude.ai](https://claude.ai).
