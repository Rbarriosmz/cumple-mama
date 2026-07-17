# Fotos de la invitación

Esta carpeta guarda dos cosas distintas: las fotos de la **galería** y los recortes del **photocall**.

---

# 1. Los abuelos del photocall

> ## ⚠️ Si cambias la foto, hay que cambiar DOS archivos
>
> Existen `abuelos.webp` **y** `abuelos.png`, con la misma imagen. La web usa el **`.webp`** (194 KB) y solo recurre al `.png` (1,7 MB) en navegadores muy antiguos.
>
> **Si sustituyes solo el `.png`, la web seguirá enseñando la foto vieja del `.webp`** y parecerá que el cambio no funcionó. Pásame la foto nueva y yo genero el `.webp`, o conviértelo tú en cualquier conversor a WebP con calidad 90.

**Archivos:**

```
abuelos.webp   <- el que se usa (194 KB)
abuelos.png    <- respaldo para navegadores viejos (1,7 MB)
```

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

Las siluetas guía se calculan **a partir de la altura de esta imagen**, para que todos salgan a la misma escala. Si al poner la foto real se ven grandes o pequeños, se toca `centerBox()` en el `index.html`: los números `0.56` (anchura máxima) y `0.66` (altura máxima), en fracción del tamaño de la foto.

---

# 2. Fotos de la galería

Coloca aquí las fotos con **estos nombres exactos** (en minúsculas, extensión `.jpg`):

| Archivo | Dónde aparece | Forma recomendada |
|---|---|---|
| `foto-1.jpg` | Marco grande, arriba del todo | Horizontal (apaisada), 3:2 |
| `foto-2.jpg` | Marco pequeño | Vertical, 4:5 |
| `foto-3.jpg` | Marco pequeño | Vertical, 4:5 |
| `foto-4.jpg` | Marco pequeño | Vertical, 4:5 |
| `foto-5.jpg` | Marco pequeño | Vertical, 4:5 |

## Cómo funciona

Cada marco enseña un dibujo decorativo mientras no exista la foto. **En cuanto subas el archivo con el nombre correcto, la foto aparece sola** — no hay que tocar el `index.html`.

Al revés también vale: si solo pones tres fotos, los otros dos marcos se quedan con el dibujo y la página sigue viéndose bien.

## Consejos

- **Peso:** que cada foto no pase de ~500 KB. La invitación se abre desde el móvil, muchas veces con datos, y fotos de 5 MB tardarían una eternidad en cargar.
- **Tamaño:** con 1200 px de ancho sobra. Más grande no se nota y solo pesa.
- **Recorte:** las fotos se recortan para llenar el marco (centradas). Si la cara queda muy al borde, recorta tú antes de subirla.
- **Nombres:** ojo con las mayúsculas. `Foto-1.JPG` **no** funciona en GitHub Pages, tiene que ser `foto-1.jpg`.

## Cómo subirlas

Copia las fotos en esta carpeta y luego, desde la carpeta del proyecto:

```powershell
git add fotos/
git commit -m "Añadir fotos de la galería"
git push
```

En un par de minutos aparecen en la web.
