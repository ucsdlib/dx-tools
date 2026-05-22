# DX Tools Design System

A design system for UC San Diego DX team internal tools. Built on campus brand guidelines with a tool-first perspective: accent colors serve as primaries, Navy provides structural depth, and every interface element is sized for serious work.

## Design principles

- **Inverted brand** — UC San Diego accent colors (Turquoise, Citron) as primary interactive colors; Navy as structural surface
- **Tool-first typography** — Atkinson Hyperlegible in tool chrome, Roboto in preview/brand areas, JetBrains Mono for code
- **Dark-first** — Navy-based dark mode by default; system `prefers-color-scheme` + `data-theme` manual toggle
- **WCAG 2.1 AAA** — 7:1 minimum contrast for primary text, 44px+ touch targets, full keyboard/screen reader support
- **No AI design tells** — No left-border-only cards, no gradient mesh backgrounds, no glassmorphism

## Two layers, one token foundation

```
css/tokens.css     ← all design tokens (import first)
css/frame.css      ← tool chrome: layout, header, sidebar, status bar
css/components.css ← component library: buttons, forms, cards, tables, etc.
css/preview.css    ← preview area: brand-faithful UC San Diego palette, scoped
css/code.css       ← code blocks, inline code, diff, terminal
```

## Quick start

```html
<link rel="preconnect" href="https://fonts.googleapis.com">
<link rel="preconnect" href="https://fonts.gstatic.com" crossorigin>
<link href="https://fonts.googleapis.com/css2?family=Atkinson+Hyperlegible:ital,wght@0,400;0,700;1,400;1,700&family=JetBrains+Mono:ital,wght@0,400;0,500;0,700;1,400&family=Roboto:ital,wght@0,300;0,400;0,500;0,700;1,400&display=swap" rel="stylesheet">

<link rel="stylesheet" href="css/tokens.css">
<link rel="stylesheet" href="css/frame.css">
<link rel="stylesheet" href="css/components.css">
<link rel="stylesheet" href="css/preview.css">
<link rel="stylesheet" href="css/code.css">
```

## Documentation

View the full design system documentation site at the GitHub Pages URL once deployed.

## Color strategy

| Context | Background | Primary CTA | Text |
|---|---|---|---|
| Frame (dark) | Navy `#182B49` | Turquoise `#00C6D7` | White |
| Frame (light) | Sand `#F5F0E6` | UC San Diego Blue `#00629B` | Navy |
| Preview | White | UC San Diego Blue `#00629B` | Navy |

All primary text meets WCAG AAA (7:1 minimum contrast ratio).
