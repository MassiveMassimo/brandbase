# Contributing to Brandbase

Thanks for adding a brand! Follow these steps to submit a logo.

## Quick Start

1. Fork this repository
2. Create a folder: `brands/{brand-slug}/`
3. Add the required 24px SVG: `{brand-slug}-24.svg`
4. Add `guidelines.md` (copy from `template/guidelines-template.md`)
5. Open a pull request

## Naming Conventions

### Folder Name
- Lowercase, hyphenated: `spotify`, `visual-studio-code`, `stack-overflow`
- Must be the commonly recognized brand name

### File Names
Pattern: `{brand}-{size}[-{variant}].svg`

| Part | Description | Examples |
|------|-------------|----------|
| `{brand}` | Matches folder name exactly | `spotify`, `github` |
| `{size}` | Pixel dimension (square) | `24`, `48`, `96` |
| `{variant}` | Optional modifier | `dark`, `light`, `wordmark`, `monochrome` |

Examples:
```
brands/spotify/
  spotify-24.svg          ← required
  spotify-48.svg
  spotify-24-dark.svg
  spotify-wordmark.svg
  guidelines.md           ← required
```

## Requirements

- **`{brand}-24.svg`** — Required. Must be exactly 24x24px square.
- **`guidelines.md`** — Required. Copy from `template/guidelines-template.md` and fill in what applies. Remove sections that don't apply.
- **Clean SVGs** — No embedded raster images, no unnecessary metadata, reasonable file size.

## SVG-Only Policy

All logos must be in SVG format. This is a deliberate choice:

- **Scalable** — Renders crisply at any size
- **Lightweight** — Smaller than equivalent bitmaps
- **Theme-adaptable** — Colors can be modified via CSS/code
- **Consistent** — One format across the entire repository

### Bitmap Exception

PNG images are allowed only for logos that are heavily illustrated or textured and genuinely cannot be represented as vectors — for example, a WWDC event logo with complex artwork.

Rules:
- Justify in your PR description why SVG is not feasible
- PNG only (for transparency and lossless quality)
- If the brand also has a standard vector logo, `{brand}-24.svg` is still required
- PRs with bitmaps that could reasonably be SVGs will be rejected
