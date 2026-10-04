# Quilt — Generative Art

> A seed-based generative system for rotated block compositions.  
> A reproducible catalogue of computational textile compositions.

---

## What is this?

**Quilt** is a generative design system that lays a twelve- to twenty-one-cell grid across the canvas and places a rotated square inside each cell. The rotation snaps to one of four quarter-turns, so every block sits on-axis or at right angles — never at an angle in between. Colours are drawn from a single background hue, shifted by a fixed arc and jittered in saturation and brightness.

Every artwork in this catalogue is defined by a single numeric seed. The same seed always produces the identical composition — making each piece **traceable, reproducible, and licensable** across textile, print, and apparel applications.

Named for the patched textile that has carried pattern and colour across cultures for centuries — a grid of small blocks, some doubled, held in a single family — **Quilt** translates that structure into code.

---

## Live

🌐 **[View the catalogue →](https://reyrove.github.io/Quilt-Generative-Art/)**

---

## The System

The generator combines three layers:

| Layer | Description |
|-------|-------------|
| **Grid** | Twelve to twenty-one cells per side, with a 5% margin around the canvas. |
| **Blocks** | A square inside each cell, sized at 30–80% of the cell and rotated to one of four quarter-turns. |
| **Doubles** | Some cells carry a second, smaller square nested inside — opposite hue, at ~30% probability. |

All three layers are driven by the same seed, ensuring deterministic output.

### Parameters

- **Grid** — 12 to 21 cells per side
- **Margin** — 5% of canvas width, on all four sides
- **Block size** — 30% to 80% of cell
- **Rotation** — flat, 90°, 180°, or 270° — snapped, never intermediate
- **Colour shift** — 30° to 150° around the background hue
- **Nested block** — 30% chance, at 20–60% of the parent block's size

---

## Structure

```
Quilt-Generative-Art/
├── index.html          ← Full catalogue (single-file)
├── images/
│   ├── fav.svg
│   ├── tote.png
│   ├── tee.png
│   └── cushion.png
└── README.md
```

The entire project is contained in a single `index.html` — no build step, no framework. Open it in any modern browser.

---

## Features

- **Seed-based generation** — every composition is deterministic and reproducible
- **Snapped rotation** — four quarter-turns only, so the grid reads as on-axis
- **Nested blocks** — occasional doubled squares break the regularity without leaving the grid
- **Live catalogue** — cover, plate, surfaces, process, archive, commission sections
- **Multiple surfaces** — print, scarf, textile, wallpaper — all rendered from the same seed
- **Archive of 8 seeds** — click any plate to load it into the main view
- **PNG export** — download any composition directly from the browser
- **Keyboard shortcuts** — `R` for new seed, `S` to save
- **Legal modal** — licensing, terms, and credits built in
- **Responsive** — works on desktop, tablet, and mobile
- **Mobile-first navbar** — horizontally scrollable with fade hint

---

## Usage

### Generate a new composition

Click **New Seed** or press `R`.

### Download the current composition

Click **Download** or press `S`.

### Load a seed from the archive

Click any plate in the **Archive** section.

---

## Colour System

Each composition is drawn in HSB, with all colours derived from a single background hue:

| Element | Range |
|---------|-------|
| **Background** | Full-spectrum hue, 10–40% saturation, 95–100% brightness |
| **Blocks** | Background hue + 30° to 150°, 40–80% saturation, 40–80% brightness |
| **Nested blocks** | Block hue + 90° to 270°, 40–80% saturation, 40–80% brightness |
| **Rotation** | Not a colour, but a fourth "channel" — snapped per block |

The result reads as a soft chromatic field: a pale ground, mid-tone blocks, and occasional deeper or lighter inset squares. Every hue in the piece traces back to the background, so the palette feels unified even at grid size twenty-one.

---

## Technical Notes

- p5.js 1.9.0 (CDN) for canvas rendering
- Custom seeded random generator for deterministic output
- HSB colour mode, per-instance
- Rotation snapped with `p.HALF_PI * n` — never arbitrary angles
- Nested blocks drawn inside the same `push()/pop()` as their parent
- Rectangular surfaces tile the square composition to fill aspect ratio

---

## About

**Quilt** is a project by [Reyhaneh Daneshdoost](https://reyrove.github.io/) — an Iranian-born artist working at the intersection of classical textile logic and generative systems.

The work begins with a simple observation: the woven surface — repetitive, mathematically structured, infinitely variable — has always been a form of computation, long before computers.

**Quilt** is an attempt to render that logic visible.

> *A square turned by a quarter becomes a rhythm.*

---

## Licensing

All compositions are seed-documented and available for licensing across textile, surface, and apparel applications.

For commercial use, custom editions, or exclusive rights:

📧 **reyhanehdaneshdoost@gmail.com**

See the **Licensing** section in the live catalogue for details.

---

## Links

- 🌐 [Website](https://reyrove.github.io/)
- 📷 [Instagram](https://www.instagram.com/rey._.rove/)
- 💼 [LinkedIn](https://www.linkedin.com/in/reyhaneh-daneshdoost-730481160/)
- 🐦 [X](https://x.com/reyrove)

---

## Credits

**Design & Generative System**  
Reyhaneh Daneshdoost

**Typefaces**  
Cormorant Garamond · DM Mono

**Edition**  
Quilt — Autumn 2026

---

<p align="center">
  <em>Computational Textile Design</em><br />
  <sub>© Reyrove Studio · All compositions reproducible by seed</sub>
</p>