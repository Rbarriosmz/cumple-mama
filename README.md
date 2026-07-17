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
| `musica.mp3` | Música de fondo *(opcional, no incluida — ver abajo)*. |

## Añadir música de fondo

El reproductor ya está programado, pero el archivo de audio no está en el repo.

1. Copia un `.mp3` en la raíz del proyecto con el nombre exacto `musica.mp3`.
2. Haz commit y push.

El botón de play/pausa aparece solo si el archivo carga correctamente; si no existe, se oculta y la página funciona igual. Nunca suena en automático: hace falta que la persona lo pulse.

## Notas técnicas

- La cuenta regresiva está anclada a `2026-08-02T14:00:00-05:00`, así que marca bien el tiempo restante tanto para quien la abra desde Perú como desde España.
- Las etiquetas `og:image` y `og:url` usan URLs absolutas apuntando a `rbarriosmz.github.io`. **Si renombras el repositorio o cambias de usuario, hay que actualizarlas a mano** o WhatsApp dejará de mostrar la imagen.
- WhatsApp cachea la tarjeta de previsualización. Si cambias `og-image.png` después de haber compartido el enlace, la tarjeta antigua puede seguir apareciendo un tiempo.
- El diseño respeta `prefers-reduced-motion` para quien tenga las animaciones desactivadas.

## Publicado con

GitHub Pages, sobre la rama `main` (raíz).
