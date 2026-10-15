# SoberanIA · landing (copia exacta del prototipo)

Es el mismo archivo de la landing diseñada en el proyecto, no una reconstrucción. React, el motor que lee la plantilla y las fuentes se sirven desde esta carpeta: no se descarga nada de unpkg ni de Google Fonts.

## Estructura
```
index.html          la landing: plantilla (entre <x-dc> y </x-dc>) y su lógica (<script data-dc-script>)
support.js          motor que lee la plantilla; carga React desde vendor/
vendor/             React 18.3.1, ReactDOM 18.3.1 y Babel 7.29.0 (copias locales)
css/fonts.css       @font-face apuntando a fonts/
css/responsive.css  puntos de quiebre para tablet y teléfono (960, 640 y 380 px)
fonts/              ponga aquí los .woff2 (nombres en fonts/LEEME.txt)
favicon.svg · favicon-32.png · apple-touch-icon.png · og-image.png
vercel.json         cabeceras de seguridad y caché de fuentes y vendor
```

## Publicar en Vercel
1. Copie sus .woff2 a `fonts/`.
2. Suba la carpeta al repositorio. En Vercel: Framework Preset **Other**, sin comando de build, Output Directory la raíz.
3. Necesita un servidor (no abre con doble clic): pruebe localmente con `python3 -m http.server 8080`.

## Antes de publicar
- **Dominio:** `index.html` usa `https://soberania.cl/` en canonical, og:url, og:image y twitter:image. Si publica en otro dominio, cámbielo en esas cuatro líneas: las redes exigen una URL absoluta para la imagen.

## Contacto
No hay formulario: la sección de contacto invita a escribir por LinkedIn (https://www.linkedin.com/in/soberan-ia-529a96443/).

## Cómo se edita
Textos y estilos están en la plantilla de `index.html`, con estilos en línea. Los valores que cambian (la demostración, las preguntas, las órbitas) están en la lógica del final, en `renderVals()`. No hay compilación: se edita y se recarga.
