# 🌟 Gestor de Temas en la Nube • Ivan OS (webOS TV)

Repositorio de catálogo dinámico de temas para la Smart TV de Ivan.

---

## 🚀 ¿Cómo Funciona el Sistema Dinámico?

1. **La TV consulta este repositorio directamente:**
   Al abrir el **Gestor de Temas** (pulsando el botón de **Ajustes** en la esquina superior derecha, la píldora de **Música** o el **botón Azul** del mando), la TV hace una petición web a:
   `https://raw.githubusercontent.com/ivanmr97/tv-themes/main/themes.json`
2. **Sin caché retardada:**
   La TV añade una marca de tiempo (`?t=timestamp`), lo que hace que cualquier cambio o nuevo tema que subas a GitHub aparezca **en tiempo real** en la pantalla del televisor sin esperas.
3. **Optimización de memoria en la TV:**
   Al pulsar **OK** sobre un tema:
   - Se descarga el nuevo vídeo `.mp4` en memoria temporal RAM (`/tmp`).
   - Se elimina/reemplaza el tema anterior de forma que **solo existe 1 vídeo en la memoria interna de la tele**, garantizando que el almacenamiento nunca se llene.
   - Se actualizan los títulos y créditos en `current_theme.json`.
   - La pantalla de inicio se reinicia automáticamente aplicando el nuevo fondo y banda sonora en vivo.

---

## 🛠️ Cómo Publicar Este Repositorio en GitHub (Paso a Paso en 1 Minuto)

1. En tu navegador, entra en **[GitHub](https://github.com/new)** y crea un repositorio público llamado:
   `tv-themes`
2. Sube los archivos de esta carpeta (`themes.json` y `README.md`) al repositorio.
3. ¡Listo! La TV ya está preconfigurada para leer de `ivanmr97/tv-themes`.

---

## 🎨 Cómo Añadir un Nuevo Tema (Vídeo + Música)

### Paso 1: Subir el archivo de vídeo (`.mp4`)
Los vídeos combinados (con su música integrada) suelen pesar entre 15MB y 100MB. En GitHub, el mejor sitio para alojar archivos grandes sin límites y con CDN ultra-rápida son los **Releases**:
1. En tu repositorio `tv-themes`, ve a la pestaña **Releases** -> **Draft a new release**.
2. Pon una etiqueta (por ejemplo `v1.0`).
3. Arrastra tu archivo `.mp4` (por ejemplo `cyberpunk-combined.mp4`) a la zona de adjuntos.
4. Pulsa **Publish release**.
5. Haz clic derecho sobre el archivo subido y copia su enlace directo de descarga.

### Paso 2: Añadir la tarjeta a `themes.json`
Abre `themes.json` y añade un bloque con los datos de tu nuevo tema:

```json
{
  "id": "mi-nuevo-tema",
  "name": "Nombre del Tema",
  "author": "Ivan OS",
  "bgm_title": "♫  Nombre de la Canción",
  "header_sub": "⚔  SUBTÍTULO PERSONALIZADO • IVAN OS",
  "accent_color": "#00e5ff",
  "preview": "file:///home/root/custom-home/icons/sports.png",
  "video_url": "https://github.com/ivanmr97/tv-themes/releases/download/v1.0/mi-nuevo-tema.mp4",
  "description": "Descripción de lo que se ve en el tema animado a 60 FPS."
}
```

¡Guarda los cambios y haz commit! La próxima vez que abras el Gestor en la tele, el nuevo tema aparecerá automáticamente con su botón para descargar y aplicar con un solo clic.

