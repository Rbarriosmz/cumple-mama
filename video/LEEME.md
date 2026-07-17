# Vídeo de la invitación

Coloca aquí el vídeo con **este nombre exacto**:

```
video.mp4
```

## Cómo funciona

El marco enseña un dibujo decorativo mientras no exista el archivo. **En cuanto subas `video.mp4`, el reproductor aparece solo** con sus controles de play, volumen y pantalla completa. No hay que tocar el `index.html`.

Nunca se reproduce en automático: hace falta que la persona le dé al play.

## Consejos importantes

- **Peso: cuanto menos, mejor.** La gente lo abrirá desde el móvil con datos. El vídeo actual se comprimió de 90 MB a ~3,7 MB (720p, H.264) sin pérdida visible.
- **Formato:** `.mp4` con códec H.264 y `-pix_fmt yuv420p`. Es el que reproducen todos los móviles, iPhone incluido.
- **Nombre:** el archivo que se publica es **`video.mp4`** (sin acentos ni ñ, que dan problemas en las URLs de GitHub Pages). Si dejas otro `.mp4` con otro nombre, git lo ignora (ver `.gitignore`) y no se sube.
- **Forma:** horizontal (16:9) queda mejor en el marco.

## Cómo se comprimió (por si hay que repetirlo)

Con [ffmpeg](https://ffmpeg.org) instalado:

```powershell
ffmpeg -i TU_VIDEO.mp4 -vf "scale=-2:720" -c:v libx264 -crf 25 -preset medium -c:a aac -b:a 128k -movflags +faststart -pix_fmt yuv420p video.mp4
```

`-movflags +faststart` es importante: coloca el índice al principio para que el vídeo empiece a verse sin descargarse entero.

## Cómo subirlo

Copia el archivo en esta carpeta y luego, desde la carpeta del proyecto:

```powershell
git add video/
git commit -m "Añadir vídeo"
git push
```

## Si el vídeo pesa demasiado

Súbelo a YouTube como **"no listado"** y dímelo: cambio el marco por un reproductor de YouTube incrustado. Así la web carga rápido y el vídeo sigue siendo privado (solo quien tenga el enlace lo ve).
