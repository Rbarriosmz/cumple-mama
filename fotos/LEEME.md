# Fotos de la invitación

Esta carpeta guarda dos cosas distintas: las fotos de la **galería** y los recortes del **photocall**.

---

# 1. Los abuelos del photocall

> ## ⚠️ Si cambias una foto, hay que cambiar DOS archivos
>
> Cada foto existe en `.webp` **y** `.png`. La web usa el **`.webp`** y solo recurre al `.png` en navegadores muy antiguos.
>
> **Si sustituyes solo el `.png`, la web seguirá enseñando la foto vieja del `.webp`** y parecerá que el cambio no funcionó. Pásame la foto nueva y yo genero el `.webp`, o conviértelo tú en cualquier conversor a WebP con calidad 90.

**Archivos:**

```
abuelos.webp    <- foto 1, la que se usa (194 KB)
abuelos.png     <- foto 1, respaldo (1,7 MB)
abuelos2.webp   <- foto 2, la que se usa (292 KB)
abuelos2.png    <- foto 2, respaldo (2,6 MB)
```

El invitado elige entre las dos con las miniaturas que salen sobre el botón de disparo. **El selector solo aparece si cargan dos o más**; con una sola, se usa esa y no hay nada que elegir.

## Añadir una tercera foto

En el `index.html`, en la lista `PHOTOS`:

```js
{ webp:'fotos/abuelos3.webp', png:'fotos/abuelos3.png', label:'...', maxW:0.64, maxH:0.70, guide:'sides' }
```

| Campo | Para qué sirve |
|---|---|
| `maxW`, `maxH` | Tamaño de partida, en fracción de la pantalla. `maxW` **puede pasar de 1** si quieres que la foto se salga por los lados a propósito. |
| `guide` | `'sides'` pone las siluetas a los lados (para cuando están juntos); `'center'` pone una en medio (para cuando hay hueco entre ellos). |

Cada foto lleva su propio encaje porque una vertical de cuerpo entero y una apaisada de medio cuerpo piden cosas distintas. Con una regla única, la que no estuviera afinada salía diminuta.

Son **los dos juntos, en una misma imagen**, y aparecen en el centro. A los lados, dos siluetas discontinuas marcan dónde colocarse la familia. Así se recrea la foto de los 50 años: ellos en medio, los hijos alrededor.

**Tiene que ser PNG con el fondo borrado** (transparente). Un `.jpg` normal saldría con su fondo rectangular encima de la cámara y quedaría fatal.

## Cómo prepararlo

1. **Elige una foto donde estén los dos de pie y juntos.** La de los 50 años sirve muy bien.
2. **Recorta primero** para quedarte solo con ellos dos. Si en la foto hay más gente, quítala en este paso.
3. **Borra el fondo** y guarda en PNG:
   - **remove.bg** — subes la foto y te la devuelve recortada. Gratis, sin instalar nada. Descarga en **PNG**, no en JPG, o pierdes la transparencia.
   - **iPhone**: mantén pulsado sobre ellos hasta que brillen, «Copiar», y pega en una app que guarde PNG.
   - **Google Fotos / Samsung**: busca «recortar sujeto» o «borrar fondo».

## Qué foto funciona mejor

- **Cuanto más cuerpo entero, mejor.** El tamaño se calcula con la altura. Una foto de medio cuerpo choca contra el límite de anchura y sale más pequeña de lo que debería.
- **Recorta el margen sobrante.** Si el PNG lleva mucho espacio transparente alrededor, ellos salen más pequeños, porque el margen cuenta como parte de la imagen.
- Peso: por debajo de ~800 KB.

Si el archivo no existe, el photocall funciona igual: solo el marco y las guías.

## Ajustar el tamaño

Las siluetas guía se calculan **a partir de la altura de esta imagen**, para que todos salgan a la misma escala. Si al poner la foto real se ven grandes o pequeños, se tocan los valores `maxW` (anchura) y `maxH` (altura) de esa foto en la lista `PHOTOS` del `index.html`, en fracción de la pantalla.

---

# 2. El álbum de recuerdos

La sección «Álbum de recuerdos» es un carrusel: enseña una foto grande cada vez, pasa sola cada pocos segundos y se puede deslizar con el dedo o con las flechas. Al tocar una foto se abre a pantalla completa.

Las fotos del álbum se llaman **`foto-01.webp`, `foto-02.webp`, `foto-03.webp`…** (numeradas con dos cifras). El álbum las busca en orden y se detiene tras dos huecos seguidos, así que **para añadir más basta con dejar la siguiente** (`foto-09.webp`, `foto-10.webp`…) y aparece sola, sin tocar el `index.html`.

## ⚠️ Importante: tienen que ir en `.webp` y optimizadas

Las fotos del móvil son enormes (3–7 MB, 6000 px). Servirlas tal cual tardaría una eternidad en el móvil de los invitados. Por eso el álbum usa **`.webp` reducido a 1600 px** — cada foto baja a ~100–300 KB.

**Si dejas aquí un `.jpg` o `.jpeg` normal, el álbum NO lo mostrará** (solo busca `.webp`). Los originales `.jpg`/`.jpeg` que dejaste están ignorados por git a propósito (ver `.gitignore`): se quedan en tu equipo, no se suben.

Para añadir fotos nuevas, lo más fácil: **pásamelas y yo las optimizo y las numero**. O tú mismo, con cualquier conversor a WebP (calidad ~82) y el nombre `foto-NN.webp`.

## Cómo se ven las fotos de distinta forma

El álbum admite verticales y apaisadas mezcladas: cada una se muestra entera y centrada, con una copia difuminada de sí misma al fondo para rellenar el marco. No se recorta nada.
