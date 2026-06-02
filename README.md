# Eye-Box Alignment Guide Generator

A lightweight, single-file web tool for generating corner alignment indicators used in **waveguide-based AR glasses** calibration interfaces.

Live demo → https://jing-yuan-huang.github.io/Eye-Box-alignment-Guide/

---

## What is this?

Waveguide AR glasses have an **Eye Box** — the spatial volume where your eye must be positioned to see a complete image. This tool generates the four-corner arrow indicators that guide users to physically adjust their glasses until all four corners are visible, confirming correct eye positioning.

![Preview](preview.png)

---

## Features

- **Input any resolution** — type W × H directly or pick from common presets
- **Live preview** — canvas updates instantly as you type
- **Export SVG** — full-resolution vector, perfect for design files and patent drawings
- **Export PNG** — full-resolution raster at exact pixel dimensions
- **Auto-computed layout** — S and M values calculated from `min(W, H)`

---

## Layout Formula

```
S (icon size) = min(W, H) × 0.12   (min 48px)
M (margin)    = min(W, H) × 0.03
```

| Preset | S | M |
|--------|---|---|
| 1920 × 1080 | 130 px | 32 px |
| 2560 × 1440 | 173 px | 43 px |
| 1024 × 1024 | 123 px | 31 px |
| 640 × 480   | 58 px  | 14 px |
| 380 × 500   | 46 px → 48 px (min) | 11 px |

---

## Corner Positions

| Corner | Anchor |
|--------|--------|
| Top-left | `(M, M)` |
| Top-right | `(W − M − S, M)` |
| Bottom-left | `(M, H − M − S)` |
| Bottom-right | `(W − M − S, H − M − S)` |

---

## Usage

### GitHub Pages
Just open the live URL above — no installation needed.

### Local
```bash
# Clone the repo
git clone https://github.com/jing-yuan-huang/Eye-Box-alignment-Guide.git

# Open in browser — no server needed
open index.html
```

---

## Files

```
index.html   ← entire tool, self-contained single file
README.md    ← this file
```

---

## Background

This tool was developed as part of a Taiwan patent application for a waveguide AR glasses eye-box calibration interface. The corner indicators provide intuitive visual feedback: when all four arrows are fully visible, the user's eye is correctly positioned within the Eye Box.

---

## License

MIT
