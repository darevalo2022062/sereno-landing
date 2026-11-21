# Sereno · landing

Página de presentación de **Sereno**, la alerta de ventana de infección de roya
del café por parcela.

- **La landing:** se despliega desde este repo.
- **La aplicación:** https://sereno-tan.vercel.app
- **El código de la app:** https://github.com/fpaiz-2022134/SERENO

## Qué hay aquí

HTML y CSS planos, sin framework ni paso de compilación. Vercel lo sirve como
sitio estático tal cual.

```
index.html      la página entera
estilo.css      los tokens son los mismos que usa la app en producción
medios/         fotos, icono y el video
```

La paleta y las tipografías (Fraunces y Figtree) se copiaron de
`src/app/globales.css` de la aplicación, para que la landing y el producto se
vean de la misma familia. Si la app cambia de paleta, aquí se ajusta el bloque
`:root` de `estilo.css` y nada más.

## El video

Hay dos montajes del mismo demo y la página elige según el ancho de pantalla:

| Archivo | Medidas | Cuándo se sirve |
|---|---|---|
| `medios/sereno-30s-horizontal.mp4` | 1920×1080 | 768 px o más |
| `medios/sereno-30s-vertical.mp4` | 1080×1920 | menos de 768 px |

Los dos los grabó el equipo contra la aplicación en producción.

El `<video>` arranca con el horizontal para que funcione **sin JavaScript**; un
script corto cambia la fuente y el póster si la pantalla es angosta, y vuelve a
cambiarlos si se gira el teléfono, conservando el punto en que iba.

Cada montaje tiene su propio póster (`medios/poster-horizontal.jpg` y
`medios/poster-vertical.jpg`), sacados con ffmpeg del segundo 4 y del 2.5 de
cada video. Es a propósito: un póster apaisado dentro del marco vertical dejaba
dos franjas negras enormes.

Para reemplazar un montaje, basta sobrescribir el archivo con el mismo nombre y
regenerar su póster:

```bash
ffmpeg -ss 4 -i medios/sereno-30s-horizontal.mp4 -frames:v 1 -q:v 3 medios/poster-horizontal.jpg
```

## Verlo en local

```bash
python3 -m http.server 4310
```

Y abrir http://localhost:4310
