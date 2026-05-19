# Chronelia Linktree Clone

Static linktree-style profile page for **Chronelia**. Hosted on GitHub Pages.

## Structure

No build step, no dependencies.

```
index.html          — main page
CLAUDE.md           — this file
.gitignore          — excludes _archive/
assets/
  ├── bg-mobile.mp4     — mobile background video (9:16 portrait)
  ├── bg-pc.mp4         — PC background video (landscape)
  ├── avatar.png        — profile avatar
  └── donate-icon.gif   — EasyDonate button icon
_archive/               — gitignored, unused Linktree JS/CSS + original saved HTML
```

## Background Video Behavior

- **Mobile (≤768px):** 2-layer — blur fill (Layer 1) + portrait clear centered (Layer 2, 9:16)
- **PC (≥769px):** `bg-pc.mp4` full cover single layer

## Layout

- Container `max-width` on mobile: `min(100%, calc(100svh * 9/16 - 40px))` — stays within portrait video bounds with 20px buffer per side
- Container `max-width` on PC: `580px`
- Background color fallback: `#7979be`
- Buttons: frosted glass (`rgba(255,255,255,0.15)`), `border-radius: 28px`
- Font: Inter (Google Fonts)

## Links

| Label | URL |
|---|---|
| Support Chronelia now | https://easydonate.app/chronelia |

## Social Icons

YouTube, Instagram (`CHRONELIA_CH`), TikTok (`@chronelia00`), Discord (`BUeCUhu9`), Facebook (`61575378848836`)

## Deploy

```
git init
git add .
git commit -m "init"
git remote add origin <repo-url>
git push -u origin main
```
GitHub → Settings → Pages → Deploy from branch: `main` / `root`
