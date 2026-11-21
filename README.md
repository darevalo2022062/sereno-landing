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

`medios/sereno-30s-horizontal.mp4` — 1920×1080, 30 s.

Se generó a partir de `sereno-30s-vertical.mp4` (1080×1920), que es el que
grabó el equipo contra la aplicación en producción. **No había una versión
horizontal**: esta se armó con ffmpeg poniendo el vertical centrado sobre un
fondo desenfocado del propio video.

Si alguien vuelve a grabar en horizontal de verdad, basta reemplazar el archivo
con el mismo nombre.

## Verlo en local

```bash
python3 -m http.server 4310
```

Y abrir http://localhost:4310
