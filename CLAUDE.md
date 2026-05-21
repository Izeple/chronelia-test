# CLAUDE.md

This file provides guidance to Claude Code (claude.ai/code) when working with code in this repository.

# Chronelia Linktree Clone

Static linktree-style profile page for **Chronelia**. Hosted on GitHub Pages.

## Structure

No build step, no dependencies. Everything in one `index.html` with inline CSS and SVG icons.

```
index.html          — main page (all CSS + SVG inline)
CLAUDE.md           — this file
.gitignore          — excludes _archive/
assets/
  ├── bg-mobile.mp4       — mobile background video (9:16 portrait)
  ├── bg-pc.mp4           — PC background video (landscape)
  ├── avatar.png          — profile avatar
  ├── donate-icon.gif     — shared button icon (both link buttons)
  ├── cursor.png          — default cursor (48x48)
  └── cursor_click.png    — hover/click cursor (32x32)
_archive/                 — gitignored, unused Linktree JS/CSS + original saved HTML
```

## Background Video Behavior

- **Mobile (≤768px):** 2-layer — blur fill (Layer 1, `z-index:0`) + portrait clear centered (Layer 2, `z-index:1`, 9:16). Blur video uses `transform: scale(1.15)` to hide blur edges.
- **PC (≥769px):** `bg-pc.mp4` full cover single layer (`z-index:0`). Mobile layers hidden via `display:none`.
- Content `.page` sits at `z-index:2` above all video layers.

## Layout

- Container `max-width` on mobile: `min(100%, calc(100svh * 9/16 - 40px))` — stays within portrait video bounds with 20px buffer per side
- Container `max-width` on PC: `580px`
- Background color fallback: `#7979be`
- Buttons: frosted glass (`rgba(255,255,255,0.15)`), `border-radius: 28px`
- Font: Inter (Google Fonts)

## CSS Custom Properties

Defined on `:root`:

| Variable | Value | Use |
|---|---|---|
| `--bg` | `#7979be` | Fallback background |
| `--btn-bg` | `rgba(255,255,255,0.15)` | Button fill |
| `--btn-border` | `rgba(255,255,255,0.25)` | Button border |
| `--btn-text` | `#ffffff` | Button text |
| `--radius` | `28px` | Button border-radius |
| `--gap` | `14px` | Links gap + container padding |

## Cursors

- Default: `cursor.png` (48×48) on `html, body`
- Interactive: `cursor_click.png` (32×32) on `a, button, [role="link"], [role="button"], input, label, select`

## Link Buttons

| Label | URL |
|---|---|
| Pray Chronelia now | https://easydonate.app/chronelia |
| Wallpaper free | https://drive.google.com/drive/folders/1T66fc6LVt3-MW6-_pm0aypj8bbtQfs76 |

Both buttons share `donate-icon.gif` as the left icon (48×48, positioned absolute within `.link-icon`).

## Social Icons

All SVG icons are inline (no external icon library). Platforms and handles:

| Platform | Handle/ID |
|---|---|
| YouTube | `@Chronelia` |
| Instagram | `CHRONELIA_CH` |
| TikTok | `@chronelia00` |
| Discord | invite `BUeCUhu9` |
| Facebook | profile ID `61575378848836` |

## Deploy

```
git add .
git commit -m "message"
git push
```
Repo: `https://github.com/Izeple/chronelia-test.git`
Site: `https://izeple.github.io/chronelia-test/`
