# Westfield · Hub de documentos — ADCOM

## Propósito
Mini sitio estático (GitHub Pages) que centraliza los documentos estratégicos del proyecto Westfield Summer 2026 para el cliente ADCOM.

## Estructura del proyecto
```
Westfield/
├── index.html              # Hub de navegación principal
├── assets/
│   └── css/
│       └── shared.css      # Tokens de diseño, reset y componente .hub-back
└── pages/                  # Documentos individuales
    ├── resumen.html         # Resumen ejecutivo (Syne / DM Sans)
    ├── resumen-stem.html    # Presentación interactiva STEM (Poppins, vars --y/--b)
    ├── flow.html            # Dashboard de inversión y ejecución (Poppins)
    ├── cuadro-materiales.html  # Herramienta paid media, exporta CSV (Poppins)
    ├── ruta.html            # Presentación estratégica completa (Poppins)
    └── informe-meta.html    # Informe de rendimiento Meta Ads + Chart.js (Poppins)
```

## Sistema de diseño
- **Fuente principal**: Poppins (Google Fonts) — usada por todos excepto `resumen.html`
- **`resumen.html`**: usa Syne + DM Sans + DM Mono
- **Tokens compartidos** (`shared.css`): `--amarillo: #FFC000`, `--negro: #000`, `--gris-*`, `--radius: 8px`
- Algunos archivos usan alias cortos (`--y`, `--b`, `--k`) — compatibles con `shared.css` porque no colisionan
- **`.hub-back`**: badge fijo (top-right) que vuelve a `index.html`, definido en `shared.css`

## Convenciones
- Archivos de página en `pages/` con kebab-case, sin espacios
- Rutas relativas: las páginas referencian `../assets/css/shared.css` y `../index.html`
- Sin framework de build — todo vanilla HTML/CSS/JS auto-contenido
- No hay dependencias externas excepto Google Fonts y Chart.js (CDN) en `informe-meta.html`

## Agregar una nueva página
1. Crear `pages/nombre-kebab.html`
2. En `<head>`: incluir la fuente + `<link rel="stylesheet" href="../assets/css/shared.css">`
3. Como primer hijo de `<body>`: `<a class="hub-back" href="../index.html">← Hub</a>`
4. Agregar la card correspondiente en `index.html`
