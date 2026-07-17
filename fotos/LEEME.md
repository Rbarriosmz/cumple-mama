# Fotos de la invitación

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
