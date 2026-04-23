# BSD XR Brand Guide

**Live:** [bitspacedevelopment.github.io/bsd-branding-repo](https://bitspacedevelopment.github.io/bsd-branding-repo/)

Interactive brand reference for Bit Space Development Ltd. (BSD XR). Single-page, zero-dependency — deploys directly to GitHub Pages or Vercel.

---

## What's Inside

| Section | Contents |
|---|---|
| Overview | Company summary, founding info, specialisations |
| Colours | Interactive swatches for both dark and light themes — click any swatch to copy the hex value |
| Typography | Space Mono type scale, letter-spacing reference, font import snippet |
| Logo | Both logo variants on correct backgrounds, usage do/don't rules |
| Components | Live interactive buttons, inputs, filter toggles, data rows, status badges |
| Principles | All 8 non-negotiable design rules |
| Voice & Tone | Brand voice attributes with writing examples |

---

## Files

```
bsd-branding-repo/
├── index.html        # Self-contained SPA (HTML + CSS + JS, no build step)
├── logo-dark.png     # White BSD wordmark + gradient XR — use on dark backgrounds
├── logo-light.png    # Black BSD wordmark + gradient XR — use on light backgrounds
├── dark.png          # Reference screenshot — dark mode
├── light.png         # Reference screenshot — light mode
├── branding.md       # Source-of-truth brand spec in Markdown
├── theme.json        # Brand tokens in JSON (colours, typography, logos)
├── vercel.json       # Vercel routing config for SPA
└── README.md
```

---

## Brand Tokens

### Dark Mode (default)

| Token | Hex | Usage |
|---|---|---|
| `background` | `#0a0a0a` | Page background |
| `surface` | `#111111` | Cards, panels |
| `surface-2` | `#181818` | Elevated surfaces |
| `border` | `#222222` | Default borders |
| `border-light` | `#333333` | Hover borders |
| `text` | `#e5e5e5` | Primary text |
| `muted` | `#666666` | Labels, captions |
| `accent` | `#ffffff` | CTAs, active states |

### Light Mode

| Token | Hex | Usage |
|---|---|---|
| `background` | `#eeeeee` | Page background |
| `surface` | `#e4e4e4` | Cards, panels |
| `surface-2` | `#dadada` | Elevated surfaces |
| `border` | `#cccccc` | Default borders |
| `border-light` | `#bbbbbb` | Hover borders |
| `text` | `#111111` | Primary text |
| `muted` | `#777777` | Labels, captions |
| `accent` | `#1b4fd8` | CTAs, active states |

### Brand Gradient (XR mark only)

```
linear-gradient(90deg, #1b3d9e 0%, #00a8e8 100%)
```

This gradient is reserved exclusively for the XR mark in the logo. Never use it in UI elements.

---

## Typography

**Font:** Space Mono (Google Fonts)
**Weights:** 400, 700
**Rules:** Uppercase everywhere. Wide letter-spacing (`0.12em`–`0.25em`). Monospace at all sizes.

```html
<link href="https://fonts.googleapis.com/css2?family=Space+Mono:ital,wght@0,400;0,700;1,400&display=swap" rel="stylesheet" />
```

---

## Design Rules

1. **No rounded corners** — sharp 90° edges everywhere
2. **1px borders only** — never thicker
3. **No shadows** — no `box-shadow` or `drop-shadow`
4. **No UI gradients** — flat surfaces only; XR gradient is the sole exception
5. **Monospace everywhere** — Space Mono at all sizes
6. **Minimal colour** — accent on interactive elements only, never decorative
7. **Uppercase always** — all user-facing text
8. **Sparse layouts** — generous whitespace

---

## Theme Implementation

Themes are controlled via a `light` class on `<html>`. All colour values are CSS custom properties using space-separated RGB channels for Tailwind opacity support.

```css
:root {
  --color-background: 10 10 10;
  --color-accent:     255 255 255;
  /* ... */
}
:root.light {
  --color-background: 238 238 238;
  --color-accent:     27 79 216;
  /* ... */
}
```

```js
// Toggle
document.documentElement.classList.toggle('light');

// Persist
localStorage.setItem('bsdxr-theme', 'light' | 'dark');
```

To prevent flash-of-dark on light preference, add this inline before any scripts in `<head>`:

```html
<script>
  try {
    if (localStorage.getItem('bsdxr-theme') === 'light')
      document.documentElement.classList.add('light');
  } catch(e) {}
</script>
```

---

## Deploy

### GitHub Pages

Push to the `main` branch. Enable GitHub Pages in repo settings → source: `main` / root.

```bash
git add .
git commit -m "Update brand guide"
git push origin main
```

### Vercel

```bash
npx vercel
```

No build step. `vercel.json` handles SPA routing.

---

## Logo Rules

- Never flatten the XR gradient to a single colour
- Never place the dark logo on a light background (or vice versa)
- Maintain clear space equal to the cap-height of "B" on all sides
- Never stretch, rotate, skew, or add effects
- Tagline "IMMERSIVE TECHNOLOGY EXPERTS" may appear below or be omitted — never rearranged

---

## Contact

| | |
|---|---|
| Website | [bsdxr.com](https://bsdxr.com) |
| Contact | [bsdxr.com/contact](https://bsdxr.com/contact) |
| Email | info@bsdxr.com |
| Location | Winnipeg, Manitoba, Canada |
| Founded | 2015 |
