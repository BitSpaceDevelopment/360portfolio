# BSD XR Brand Guide

**Company:** Bit Space Development Ltd. (BSD XR)
**Tagline:** Immersive Technology Experts
**Founded:** 2015
**Location:** Winnipeg, Manitoba, Canada
**Website:** [bsdxr.com](https://bsdxr.com)
**Contact:** [bsdxr.com/contact](https://bsdxr.com/contact)

---

## Who We Are

BSD XR is a leading extended reality development company specialising in immersive XR, AR, and AI solutions for industries that demand precision, innovation, and results. Since 2015, we have partnered with organisations across aerospace, construction, education, mining, railways, and manufacturing to deliver transformative technology experiences that improve safety, training, and engagement.

Our approach is design-led and research-driven. We do not just build software — we build the future of how humans interact with information and with each other.

---

## Brand Voice

- **Direct.** No filler words. Every sentence earns its place.
- **Technical but accessible.** We speak to engineers and executives in the same breath.
- **Confident, not arrogant.** We let our work speak.
- **Uppercase, tracked-out.** Even our tone feels like the typography — precise, measured, deliberate.

---

## Logo

The BSD XR logo consists of two parts:

1. **BSD wordmark** — Bold, condensed letterforms. Black in light mode, white in dark mode.
2. **XR mark** — A geometric, angular XR constructed from diagonal strokes with a blue gradient fill (dark blue `#1b3d9e` → cyan `#00a8e8`, left to right).

### Logo Files

| File | Use |
|---|---|
| [`logo-dark.png`](./logo-dark.png) | White wordmark + gradient XR. Use on dark backgrounds. |
| [`logo-light.png`](./logo-light.png) | Black wordmark + gradient XR. Use on light backgrounds. |

The web app references these files from `vr-compare/public/` (copies of the same files):

| App path | Source |
|---|---|
| `vr-compare/public/logo-dark.png` | Copy of `branding/logo-dark.png` |
| `vr-compare/public/logo-light.png` | Copy of `branding/logo-light.png` |

### Logo Rules

- Never change the XR gradient to a flat colour.
- Never place the dark logo on a light background or vice versa.
- Maintain clear space equal to the cap-height of the "B" on all sides.
- Never stretch, rotate, or add effects to the logo.
- The tagline "IMMERSIVE TECHNOLOGY EXPERTS" may appear below the logo or be omitted — never rearranged.

---

## Colour System

Colours are defined as CSS custom properties on `:root` and toggled by adding the class `light` to the `<html>` element. All values use space-separated RGB channels to support Tailwind CSS opacity modifiers.

### Dark Mode (default)

| Token | Hex | Usage |
|---|---|---|
| `background` | `#0a0a0a` | Page background |
| `surface` | `#111111` | Cards, panels, dropdowns |
| `surface-2` | `#181818` | Elevated surfaces, category headers |
| `border` | `#222222` | Default borders and dividers |
| `border-light` | `#333333` | Hover-state borders |
| `text` | `#e5e5e5` | Primary body and heading text |
| `muted` | `#666666` | Labels, captions, placeholders |
| `accent` | `#ffffff` | CTAs, active states, links, winner highlights |

### Light Mode

| Token | Hex | Usage |
|---|---|---|
| `background` | `#eeeeee` | Page background |
| `surface` | `#e4e4e4` | Cards, panels, dropdowns |
| `surface-2` | `#dadada` | Elevated surfaces, category headers |
| `border` | `#cccccc` | Default borders and dividers |
| `border-light` | `#bbbbbb` | Hover-state borders |
| `text` | `#111111` | Primary body and heading text |
| `muted` | `#777777` | Labels, captions, placeholders |
| `accent` | `#1b4fd8` | CTAs, active states, links, winner highlights |

### Brand Blue (XR gradient only)

| Stop | Hex | Position |
|---|---|---|
| Dark blue | `#1b3d9e` | 0% (left) |
| Cyan | `#00a8e8` | 100% (right) |

This gradient is reserved exclusively for the XR mark in the logo. It does not appear in UI elements.

### Status Colours

These are fixed and do not change between themes.

| State | Usage | Tailwind |
|---|---|---|
| Discontinued | Device no longer in production | `border-yellow-700 text-yellow-600` |
| Filtered | Device excluded by active filter | `border-orange-800 text-orange-500` |
| Winner | Best value in a spec row | `text-green-400` |
| Active / In production | Status indicator in admin | `text-green-500` |
| Error | Form validation, mutation errors | `text-red-500` |

---

## Typography

**Font:** Space Mono (Google Fonts)
**Weights used:** 400 (regular), 700 (bold)
**Import:** `https://fonts.googleapis.com/css2?family=Space+Mono:ital,wght@0,400;0,700;1,400&display=swap`

### Usage Rules

- **All UI text is uppercase.** No sentence case in labels, buttons, headings, or nav items.
- **Letter-spacing is always wide** (`tracking-widest` or `tracking-wider` in Tailwind).
- **Font size is small by default** — `text-xs` (12px) for labels, `text-sm` (14px) for body, with headings scaled via `text-xl` to `text-3xl`.
- **Bold is used sparingly** — only for device names, category headers, and primary CTAs.

### Hierarchy Example

```
COMPARE                          ← text-xs uppercase tracking-widest text-muted
VR SYSTEMS                       ← text-3xl uppercase tracking-widest font-bold text-text
Select up to 4 devices...        ← text-xs tracking-wider text-muted
```

---

## UI Principles

These rules are non-negotiable and define the BSD XR digital aesthetic.

1. **No rounded corners.** Every element uses sharp 90° edges (`rounded-none` is implied everywhere).
2. **1px borders only.** Never use 2px or thicker borders.
3. **No shadows.** No `box-shadow` or `drop-shadow` anywhere in the UI.
4. **No gradients in UI elements.** Flat surfaces only. The XR gradient is the sole exception.
5. **Monospace everywhere.** Space Mono is used at all sizes — body, labels, code, inputs.
6. **Minimal colour.** The accent colour appears only on interactive elements (buttons, active states, links). Never as decoration.
7. **Uppercase always.** All user-facing text in the interface is uppercase.
8. **Sparse layouts.** Generous whitespace. Content does not fight for attention.

---

## Component Patterns

### Buttons

```
Primary:  border border-accent text-accent px-4 py-1.5 hover:bg-accent hover:text-background
Ghost:    border border-border text-muted hover:border-border-light hover:text-text
Danger:   border border-red-900 text-red-500 hover:bg-red-950
```

All buttons: uppercase, tracking-widest, text-xs, no border-radius.

### Inputs

```
bg-surface border border-border text-text font-mono text-sm px-3 py-2
outline-none focus:border-border-light
```

### Toggle / Filter Buttons

```
Active:   border-accent text-accent bg-accent/10
Inactive: border-border text-muted hover:border-border-light hover:text-text
```

### Status Badges

```
Discontinued: border border-yellow-700 text-yellow-600 px-1.5 py-0.5 text-[10px] uppercase tracking-widest
Filtered:     border border-orange-800 text-orange-500 px-1.5 py-0.5 text-[10px] uppercase tracking-widest
```

---

## Theme Implementation

```css
/* index.css */
:root {
  --color-background: 10 10 10;
  --color-accent: 255 255 255;
  /* ... */
}

:root.light {
  --color-background: 238 238 238;
  --color-accent: 27 79 216;
  /* ... */
}
```

```ts
// Toggle by adding/removing the 'light' class on <html>
document.documentElement.classList.toggle('light')

// Persist preference
localStorage.setItem('bsdxr-theme', 'light' | 'dark')
```

Theme is initialised before React boots via an inline script in `index.html` to prevent flash-of-dark on light mode preference:

```html
<script>
  try {
    if (localStorage.getItem('bsdxr-theme') === 'light')
      document.documentElement.classList.add('light')
  } catch(e) {}
</script>
```

---

## Contact

| | |
|---|---|
| Website | [bsdxr.com](https://bsdxr.com) |
| Contact | [bsdxr.com/contact](https://bsdxr.com/contact) |
| Email | info@bsdxr.com |
| Location | Winnipeg, Manitoba, Canada |
| Founded | 2015 |
