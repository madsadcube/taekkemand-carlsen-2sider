# Tækkemand Carlsen — to sider (handoff til Peter)

Dette er et **selvstændigt, trimmet Astro-projekt** med præcis de to sider du skal arbejde videre på:

| URL | Fil |
|-----|-----|
| `/b/` | `src/pages/b.astro` |
| `/helsinge/` | `src/pages/helsinge/index.astro` |

Alt andet i projektet er kun det, de to sider afhænger af (komponenter, layout, data, config og billeder). Resten af det rigtige website er bevidst skåret væk.

## Sådan kører du det lokalt

Kræver Node.js 22.12 eller nyere.

```bash
npm install
npm run dev
```

Åbn så:
- http://localhost:4321/b/
- http://localhost:4321/helsinge/

Hot-reload er slået til — gem en fil, og browseren opdaterer.

## Byg til statiske filer

```bash
npm run build      # output i dist/
npm run preview    # se den byggede version
```

## Struktur

```
src/
  pages/
    b.astro                 ← side 1  (/b/)
    helsinge/index.astro    ← side 2  (/helsinge/)
  components/
    b/                      ← komponenter brugt af /b/
    v5/                     ← komponenter brugt af /helsinge/
    Nav.astro, Garanti.astro, Gallery.astro   ← delte
  layouts/Layout.astro      ← fælles HTML-skelet / <head>
  data/cities.ts            ← bydata
  styles/global.css         ← global styling (Tailwind v4)
public/img/                 ← billeder
astro.config.mjs            ← Astro + Tailwind + sitemap config
tailwind.config.mjs
```

## Noter

- **Styling:** Tailwind CSS v4 (via `@tailwindcss/vite`). Utility-klasser i markup; global CSS i `src/styles/global.css`.
- Interne links til sider der ikke er med her (fx `/kontakt/`, `/galleri/`) giver 404 lokalt — det er forventet, de findes på det fulde site.
- `astro.config.mjs` indeholder `.php`-redirects fra det gamle site; lad dem bare være.

Spørgsmål: skriv til Mads.
