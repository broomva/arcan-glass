# arcan-glass

BroomVA's trademark web styling system -- the Arcan Glass design language for Next.js + Tailwind v4 + shadcn/ui projects. Glass/frosted UI effects, dark-first themes, and AI Blue brand tokens delivered as a drop-in `globals.css` and composable component patterns.

This is a [skills.sh](https://skills.sh) agent skill -- it can be installed by any AI agent that supports the skills protocol.

## Features

- **Drop-in globals.css** with all tokens, glass utilities, components, and animations
- **Dark-first design** with automatic light mode support via CSS custom properties
- **Glass effect system** built from 4 composable layers (backdrop blur, highlight, shadow, adaptive tint)
- **OKLCh color system** with P3 gamut enhancement on capable displays
- **Full shadcn/ui compatibility** -- all shadcn CSS variables resolve to Arcan Glass tokens
- **Tailwind v4 integration** via `@theme inline` with brand color utilities
- **Reduced motion** respected globally across all animations and transforms

## Quick Start

1. **Copy** `arcan-glass/assets/globals.css` into your Next.js project as `app/globals.css`
2. **Import** in your layout: `import "./globals.css"`
3. **Use** glass classes:

```html
<div class="glass-card">Standard glass card</div>
<button class="glass-button glass-button-primary">Primary action</button>
<nav class="glass-heavy sticky top-0">Navigation</nav>
```

All shadcn/ui components automatically pick up the Arcan Glass theme.

## Brand Colors

| Token | Color | Usage |
|-------|-------|-------|
| `--ag-ai-blue` | `#0066FF` | Primary, interactive, links |
| `--ag-web3-green` | `#00CC66` | Accent, success, web3 |

## Glass Intensity Presets

| Preset | Opacity / Blur | Use for |
|--------|---------------|---------|
| `glass-subtle` | 40% / 8px | Repeated items (list items, table rows) |
| `glass` | 60% / 16px | Key surfaces (cards, buttons) |
| `glass-heavy` | 80% / 24px | Landmark surfaces (nav, sidebar, modal) |

## Component Index

| Component | Class | Glass Level |
|-----------|-------|-------------|
| Card | `.glass-card` | Medium |
| Nav | `.glass-nav` | Heavy |
| Button | `.glass-button` | Medium |
| Input | `.glass-input` | Subtle |
| Modal | `.glass-modal` | Heavy |
| Sidebar | `.glass-sidebar` | Heavy |
| Badge | `.glass-badge` | Subtle |

## Animation Index

| Animation | Tailwind Class | Duration |
|-----------|---------------|----------|
| Glow pulse | `animate-glow-pulse` | 2s loop |
| Glass reveal | `animate-glass-reveal` | 0.5s once |
| Gradient flow | `animate-gradient-flow` | 8s loop |

## Design Principles

1. **Dark-first** -- dark mode is the default; light mode is supported but secondary
2. **Glass is earned** -- limit `backdrop-filter` to 3-5 elements per viewport
3. **Brand through surface** -- surface hue 275 connects all surfaces to AI Blue
4. **OKLCh primary** -- perceptually uniform lightness for clean depth scales
5. **Additive on shadcn** -- glass layers on top of shadcn/ui, never replacing base accessibility
6. **Motion with purpose** -- every animation communicates state; reduced motion is respected
7. **Token-prefixed** -- all custom properties use `--ag-` to avoid collisions

## References

- `arcan-glass/references/color-system.md` -- Full OKLCh palette, hex fallbacks, surface scale
- `arcan-glass/references/design-tokens.md` -- Shadows, blur, radius, spacing, typography
- `arcan-glass/references/glass-components.md` -- 4-layer glass system, component CSS patterns
- `arcan-glass/references/animation-patterns.md` -- Glow, hover, morph, scroll reveal patterns
- `arcan-glass/references/tailwind-integration.md` -- @theme wiring, shadcn mapping, cva extensions

## License

[MIT](LICENSE)
