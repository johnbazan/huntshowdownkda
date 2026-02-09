# Hunt HUD • OCR → KD / KDA

Un HUD estilo **Hunt: Showdown** que toma una **imagen pegada desde el portapapeles (Ctrl+V)**, extrae **kills / deaths / assists** con OCR y calcula:

* **KD = kills / deaths**
* **KDA = (kills + assists) / deaths**
* **Progreso real** para subir **+0.01** (con **redondeo half-up**: `1.965 → 1.97`)
* **Safe por X**: cuántas muertes podés sumar sin que baje el valor mostrado (a 2 decimales)

Todo corre **100% en el navegador**. No hay backend. No hay datos que salgan de tu PC.

---

## ✨ Demo (Ctrl+V)

1. Abrí la página
2. Hacé click en el panel
3. Pegá un screenshot con **Ctrl+V**
4. Mirá el HUD actualizarse

---

## 🧠 Cómo funciona el cálculo (lo importante)

El valor mostrado usa **redondeo a 2 decimales half-up**.

Para que el número mostrado suba +0.01:

```
ratio >= (nextShown - 0.005)
```

Para que **no baje** aunque sumes muertes (“Safe”):

```
ratio >= (shown - 0.005)
```

Eso hace que los cálculos coincidan **exactamente** con lo que ves en pantalla.

---

## 🗂 Estructura

Este repo es un **único HTML estático**:

```
average_hunt_lore_components.html
```

Incluye:

* Estilos inspirados en Hunt (tiles, tagbar, brass/rust, grano, humo)
* OCR con `tesseract.js`
* Lógica de KD/KDA y progreso
* Filtros tipo “Lore” (All / KD / KDA / Debug)

---

## 🚀 Hostearlo gratis (recomendado)

La forma más simple:

### Opción 1 — Cloudflare Pages

1. Entrá a [https://pages.cloudflare.com](https://pages.cloudflare.com)
2. **Create project → Upload assets**
3. Subí el HTML
4. Listo: `tunombre.pages.dev`

Podés conectar tu propio dominio gratis.

### Opción 2 — Vercel / Netlify

Drag & drop del archivo y ya queda online.

---

## 🔒 Privacidad

* No hay servidor
* No se suben imágenes
* Todo el OCR ocurre en tu navegador

---

## 🧩 Personalización

Podés modificar fácilmente:

* Colores en `:root`
* Textos del HUD
* Estilo de tiles
* Cálculo en la función `hundredthStats`

---

## 🎮 Inspiración visual

El layout replica componentes visuales de la sección **Lore** de Hunt Showdown:

* Tagbar tipo filtros
* Tiles con kicker + título grande + CTA
* Estética brass / rust / parchment

---

## 🛠 Requisitos

Cualquier navegador moderno con:

* Soporte para Clipboard API
* Soporte para WebAssembly (Tesseract)

---

## 📝 Licencia

Uso personal / educativo.
El estilo está **inspirado** en Hunt Showdown, pero no usa assets oficiales.

---

## ❤️ Autor

Hecho para jugadores obsesivos del KD que necesitan saber **exactamente** cuántos kills faltan para subir 0.01 😄
