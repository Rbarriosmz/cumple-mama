# Vídeo de la invitación

Coloca aquí el vídeo con **este nombre exacto**:

```
video.mp4
```

## Cómo funciona

El marco enseña un dibujo decorativo mientras no exista el archivo. **En cuanto subas `video.mp4`, el reproductor aparece solo** con sus controles de play, volumen y pantalla completa. No hay que tocar el `index.html`.

Nunca se reproduce en automático: hace falta que la persona le dé al play.

## Consejos importantes

- **Peso: máximo ~50 MB, y cuanto menos mejor.** GitHub rechaza archivos de más de 100 MB, y además la gente abrirá esto desde el móvil con datos. Un vídeo de 1-2 minutos bien comprimido cabe de sobra.
- **Formato:** `.mp4` con códec H.264. Es el que reproducen todos los móviles. Si lo grabaste con el iPhone puede salir en `.mov` o HEVC — conviértelo a `.mp4`/H.264 o mucha gente no lo verá.
- **Forma:** horizontal (16:9) queda mejor en el marco. Si es vertical se recortará por los lados.

## Cómo subirlo

Copia el archivo en esta carpeta y luego, desde la carpeta del proyecto:

```powershell
git add video/
git commit -m "Añadir vídeo"
git push
```

## Si el vídeo pesa demasiado

Súbelo a YouTube como **"no listado"** y dímelo: cambio el marco por un reproductor de YouTube incrustado. Así la web carga rápido y el vídeo sigue siendo privado (solo quien tenga el enlace lo ve).
