Hunt HUD • OCR → KD / KDA

Un HUD estilo Hunt: Showdown que toma una imagen pegada desde el portapapeles (Ctrl+V), extrae kills / deaths / assists con OCR y calcula:

KD = kills / deaths

KDA = (kills + assists) / deaths

Progreso real para subir +0.01 (con redondeo half-up: 1.965 → 1.97)

Safe por X: cuántas muertes podés sumar sin que baje el valor mostrado (a 2 decimales)

Todo corre 100% en el navegador. No hay backend. No hay datos que salgan de tu PC.

✨ Demo (Ctrl+V)

Abrí la página

Hacé click en el panel

Pegá un screenshot con Ctrl+V

Mirá el HUD actualizarse

🧠 Cómo funciona el cálculo (lo importante)

El valor mostrado usa redondeo a 2 decimales half-up.

Para que el número mostrado suba +0.01:

ratio >= (nextShown - 0.005)


Para que no baje aunque sumes muertes (“Safe”):

ratio >= (shown - 0.005)


Esto hace que los cálculos coincidan exactamente con lo que ves en pantalla.

🗂 Estructura

Este repo es un único HTML estático:

average_hunt_lore_components.html


Incluye:

Estilos inspirados en Hunt (tiles, tagbar, brass/rust, grano, humo)

OCR con tesseract.js

Lógica de KD/KDA y progreso

Filtros tipo “Lore” (All / KD / KDA / Debug)

🚀 Hostearlo gratis (recomendado)
Cloudflare Pages

https://pages.cloudflare.com

Create project → Upload assets

Subí el HTML

Listo: tunombre.pages.dev

Podés conectar tu propio dominio gratis.

Vercel / Netlify

Drag & drop del archivo y ya queda online.

🔒 Privacidad

No hay servidor

No se suben imágenes

Todo el OCR ocurre en tu navegador

🧩 Personalización

Podés modificar fácilmente:

Colores en :root

Textos del HUD

Estilo de tiles

Cálculo en la función hundredthStats

🎮 Inspiración visual

El layout replica componentes visuales de la sección Lore de Hunt Showdown:

Tagbar tipo filtros

Tiles con kicker + título grande + CTA

Estética brass / rust / parchment

🛠 Requisitos

Cualquier navegador moderno con:

Soporte para Clipboard API

Soporte para WebAssembly (Tesseract)

📝 Licencia

Uso personal / educativo.
El estilo está inspirado en Hunt Showdown, pero no usa assets oficiales.

🇬🇧 English Version
Hunt HUD • OCR → KD / KDA

A Hunt: Showdown-styled HUD that takes an image pasted from your clipboard (Ctrl+V), extracts kills / deaths / assists via OCR and calculates:

KD = kills / deaths

KDA = (kills + assists) / deaths

True progress to the next +0.01 (using half-up rounding: 1.965 → 1.97)

Safe by X: how many deaths you can add without lowering the displayed value (2 decimals)

Everything runs 100% in the browser. No backend. No data leaves your machine.

✨ Demo (Ctrl+V)

Open the page

Click inside the panel

Paste a screenshot with Ctrl+V

Watch the HUD update

🧠 How the math works

Displayed values use 2-decimal half-up rounding.

To increase the shown value by +0.01:

ratio >= (nextShown - 0.005)


To avoid decreasing the shown value (“Safe”):

ratio >= (shown - 0.005)


This makes the math match exactly what you see on screen.

🗂 Structure

This repo is a single static HTML file:

average_hunt_lore_components.html


It includes:

Hunt-inspired styling (tiles, tagbar, brass/rust, grain, smoke)

OCR with tesseract.js

KD/KDA logic and progress bars

Lore-style filters (All / KD / KDA / Debug)

🚀 Free hosting (recommended)
Cloudflare Pages

https://pages.cloudflare.com

Create project → Upload assets

Upload the HTML

Done: yourname.pages.dev

You can attach your own domain for free.

Vercel / Netlify

Drag & drop the file and you’re live.

🔒 Privacy

No server

No image uploads

OCR runs locally in your browser

🧩 Customization

You can easily tweak:

Colors in :root

HUD texts

Tile styles

The hundredthStats function

📝 License

Personal / educational use.
Visual style is inspired by Hunt Showdown, no official assets used.

Made for KD-obsessed hunters who need to know exactly how many kills are left for the next +0.01.
