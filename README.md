# elcientificodo

Sitio oficial de **El Científico** — elcientificodo.com

Hospedado con GitHub Pages. Dominio personalizado en `CNAME`.

## Estructura

```
index.html      la página completa (HTML + CSS + JS en un solo archivo)
404.html        página de error con la misma identidad visual
img/            fotos optimizadas, posters de video, y og.jpg (imagen para compartir)
video/          clips verticales (MP4, H.264, 20-35 s)
CNAME           dominio personalizado
robots.txt      permite la indexación y apunta al sitemap
sitemap.xml     mapa del sitio para buscadores
.nojekyll       evita el procesamiento de Jekyll
```

## Secciones

`#vivo` · `#musica` · `#lab` · `#sobre` · `#contacto`

La galería de fotos vive **dentro** de `#sobre` (ancla `#fotos`), no es una sección aparte.

## Para actualizar fotos

Reemplaza el archivo en `img/` con el mismo nombre, o añade uno nuevo y
actualiza el `<figure>` correspondiente en la galería dentro de `#sobre`.
Exporta a ~1600 px del lado largo, calidad JPEG 80.

Cada `<img>` necesita sus atributos `width` y `height` con las medidas
reales del archivo — si no coinciden, la foto se deforma.

## Para actualizar videos

Los clips van en `video/` como MP4 (H.264 + AAC), verticales, de 20 a 35 s.
Cada uno necesita un poster en `img/poster-<nombre>.jpg`.

En el HTML el video usa `data-src` (no `src`): así el archivo sólo se
descarga cuando el clip se acerca a la pantalla. Mantén `data-src` al
añadir uno nuevo.

```html
<video data-src="video/NOMBRE.mp4" poster="img/poster-NOMBRE.jpg"
       muted loop playsinline preload="none" width="576" height="1024"></video>
```

## Imagen para compartir

`img/og.jpg` (1200x630) es lo que se ve al pegar el enlace en WhatsApp,
Instagram o X. Si cambias la foto principal, regenera también esta.
