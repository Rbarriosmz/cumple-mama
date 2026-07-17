# Los 60 de María Esther

Invitación digital al cumpleaños número 60 de **María Esther Muñoz Medina**.

**Ver la invitación:** https://rbarriosmz.github.io/cumple-mama/

## El evento

| | |
|---|---|
| **Fecha** | Domingo 2 de agosto de 2026 |
| **Hora** | 2:00 PM (hora de Perú, UTC−5) |
| **Lugar** | Caserío Aguada de Palos, s/n · Distrito de Santiago · Ica, Perú |

## Qué hay aquí

| Archivo | Para qué sirve |
|---|---|
| `index.html` | La invitación entera: HTML, CSS y JS en un solo archivo, sin dependencias más allá de Google Fonts. |
| `og-image.png` | Imagen 1200×630 de la tarjeta que aparece al pegar el enlace en WhatsApp. |
| `fotos/` | Las fotos de la galería — ver [`fotos/LEEME.md`](fotos/LEEME.md). |
| `video/` | El vídeo — ver [`video/LEEME.md`](video/LEEME.md). |
| `musica.mp3` | Música de fondo *(opcional, no incluida — ver abajo)*. |

## Añadir fotos y vídeo

**No hay que tocar el `index.html`.** Cada marco enseña un dibujo decorativo mientras no exista el archivo, y en cuanto subas uno con el nombre correcto, aparece solo. Si subes tres fotos en vez de cinco, los otros marcos se quedan con el dibujo y la página sigue viéndose bien.

- **Fotos:** `fotos/foto-1.jpg` … `fotos/foto-5.jpg`. La primera es el marco grande. Instrucciones completas en [`fotos/LEEME.md`](fotos/LEEME.md).
- **Vídeo:** `video/video.mp4`. Instrucciones completas en [`video/LEEME.md`](video/LEEME.md).

Las fotos se pueden ampliar tocándolas.

## Añadir música de fondo

El reproductor ya está programado, pero el archivo de audio no está en el repo.

1. Copia un `.mp3` en la raíz del proyecto con el nombre exacto `musica.mp3`.
2. Haz commit y push.

El botón de play/pausa aparece solo si el archivo carga correctamente; si no existe, se oculta y la página funciona igual. Nunca suena en automático: hace falta que la persona lo pulse.

## Notas técnicas

- La cuenta regresiva está anclada a `2026-08-02T14:00:00-05:00`, así que marca bien el tiempo restante tanto para quien la abra desde Perú como desde España.
- Las animaciones de entrada esconden el contenido hasta que el JavaScript lo revela. Para que eso no deje la página en blanco si el scripting falla (pasa en el navegador interno de WhatsApp y en móviles viejos), **esas reglas CSS están limitadas a `.js`**, una clase que solo se añade si el script corre. Además hay una red de seguridad que muestra todo a los 3 segundos si el `IntersectionObserver` no llega a dispararse. Si tocas las animaciones, conserva las dos protecciones.
- Las etiquetas `og:image` y `og:url` usan URLs absolutas apuntando a `rbarriosmz.github.io`. **Si renombras el repositorio o cambias de usuario, hay que actualizarlas a mano** o WhatsApp dejará de mostrar la imagen.
- WhatsApp cachea la tarjeta de previsualización. Si cambias `og-image.png` después de haber compartido el enlace, la tarjeta antigua puede seguir apareciendo un tiempo.
- El diseño respeta `prefers-reduced-motion` para quien tenga las animaciones desactivadas.

## Publicado con

GitHub Pages, sobre la rama `main` (raíz).
