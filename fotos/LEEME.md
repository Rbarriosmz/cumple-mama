# Fotos de la invitación

Esta carpeta guarda dos cosas distintas: las fotos de la **galería** y los recortes del **photocall**.

---

# 1. Los abuelos del photocall

Para que aparezcan a los lados y los invitados se hagan fotos con ellos:

| Archivo | Dónde aparece |
|---|---|
| `abuelo.png` | Lado izquierdo |
| `abuela.png` | Lado derecho |

**Tienen que ser PNG con el fondo borrado** (transparente). Un `.jpg` normal saldría con su fondo rectangular encima de la cámara y quedaría fatal.

## Cómo borrar el fondo

- **remove.bg** — subes la foto y te la devuelve recortada. Gratis y sin instalar nada. Descárgala en **PNG**, no en JPG, o pierdes la transparencia.
- **iPhone**: abre la foto, mantén pulsado sobre la persona hasta que brille, «Copiar» y pégala en una app que guarde PNG.
- **Google Fotos / Samsung**: buscar «recortar sujeto» o «borrar fondo».

## Qué foto elegir

- **De cuerpo entero, mejor que un retrato.** El tamaño se calcula con la altura, así que una figura alta y estrecha se ve a tamaño natural junto a los invitados. Una foto de medio cuerpo choca contra el límite de anchura y sale más pequeña.
- **Recorta lo que sobre** antes de subirla. Si el PNG lleva mucho margen transparente alrededor, la persona aparece más pequeña y despegada del borde, porque el margen cuenta como parte de la imagen.
- Que la persona esté **de pie y mirando a cámara** si puede ser.
- Peso: por debajo de ~800 KB.

Si solo subes uno de los dos, ese lado se ocupa y el otro se queda vacío. Si no subes ninguno, el photocall funciona igual, solo con el marco.

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
