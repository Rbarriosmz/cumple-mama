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

## Photocall

Un botón abre la cámara del móvil y dibuja encima un marco con «60 años · María Esther · 2 · Agosto · 2026». El invitado hace la foto y la guarda en su carrete.

Recrea la foto familiar de los 50 años: **los abuelos en el centro** y la familia colocándose a los lados. Se dibuja en tres capas, y la diferencia entre ellas importa:

| Capa | ¿Sale en la foto guardada? |
|---|---|
| **Los abuelos** (`fotos/abuelos.png`), los dos juntos, en el centro | Sí |
| **La guía**: dos siluetas de cuerpo entero marcando dónde colocarse | **No** — solo se ve al encuadrar |
| **El marco** y los textos | Sí |

La guía existe para que la gente se sitúe junto a ellos, no para salir en la imagen. Ese `withGuide` de `paint()` es justo lo que separa una cosa de la otra: si alguna vez lo pones a `true` en la captura, las siluetas acabarán en las fotos de todo el mundo.

**Las guías se dimensionan desde `centerBox()`**, o sea, desde la altura real a la que se dibujan los abuelos. No es un capricho: cuando cada uno calculaba su tamaño por separado, las siluetas salían un 50% más altas que la pareja y la escena dejaba de leerse como gente de pie junta. Si tocas el tamaño de los abuelos, las guías siguen solas.

Cómo preparar el recorte: [`fotos/LEEME.md`](fotos/LEEME.md). Necesita el fondo borrado; un `.jpg` normal saldría con su rectángulo encima de la cámara.

**La foto no sale del dispositivo.** No se sube a ninguna parte, y esto no es una limitación temporal: para que la web escribiera en este repositorio habría que incrustar un token de escritura de GitHub en el `index.html`, que es público. Cualquiera podría cogerlo y borrar el repo. Si algún día quieres recibir las fotos automáticamente, hace falta un servidor intermedio que guarde el token — no se puede hacer desde una página estática.

Detalles de implementación:

- El marco se dibuja **con código en un `<canvas>`**, no es un PNG, así que sale nítido a cualquier resolución de cámara. Está verificado en 3:4, 4:3 y 9:16.
- Las medidas del marco van en unidades de `u = min(ancho, alto) / 100`. **La última línea de texto no puede bajar de `7u` desde el borde inferior** o choca con la regla dorada interior, que está a `4.7u`.
- La cámara frontal se muestra y se captura **en espejo**, como en cualquier app de selfies, pero el marco se dibuja sin espejar para que el texto no salga del revés.
- Si la cámara falla o se deniega el permiso, hay **plan B automático**: se abre el selector de fotos del móvil y se le aplica el mismo marco.
- El navegador interno de WhatsApp suele bloquear la cámara. En ese caso se muestra un aviso explicando cómo abrir la página en Chrome o Safari.
- La cámara se apaga al cerrar (`track.stop()`), para no dejar el piloto encendido.

## Privacidad

GitHub Pages gratuito obliga a que el repositorio sea público, así que **cualquiera con el enlace puede abrir la invitación**, y aquí hay un nombre completo, una dirección, la fecha en que la familia estará allí y un número de WhatsApp.

Por eso la página pide **no ser indexada** por los buscadores, desde dos sitios:

- `<meta name="robots" content="noindex, ...">` en el `index.html`
- `robots.txt` con `Disallow: /`

Los buscadores serios lo respetan; los rastreadores maliciosos no hacen caso de ninguna de las dos cosas, así que esto reduce la exposición pero no la elimina. **Si quitas esas dos protecciones, la invitación puede acabar en Google** con el teléfono incluido.

Las previsualizaciones de enlaces de WhatsApp y Twitter ignoran `robots`, así que la tarjeta con la imagen sigue funcionando.

Los commits usan el email `noreply` de GitHub a propósito, para no publicar el correo personal.

## Publicado con

GitHub Pages, sobre la rama `main` (raíz).
