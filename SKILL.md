---
name: arcan-glass
description: >
  BroomVA trademark web styling system with glass/frosted effects, dark-first themes,
  and AI Blue tokens for Next.js + Tailwind v4 + shadcn/ui. Provides a drop-in globals.css,
  glass component patterns (card, nav, button, modal, sidebar, badge), OKLCh color system
  with P3 gamut enhancement, and composable animation presets. Use when creating or styling
  BroomVA web interfaces, implementing frosted glass UI effects, setting up brand-consistent
  dark-first themes, or integrating ArcanBG brand tokens (AI Blue #0066FF, Web3 Green #00CC66).
---

# Arcan Glass

**Arcan Glass** is BroomVA's trademark web design language -- ArcanBG's brand DNA (AI Blue `#0066FF` + Web3 Green `#00CC66` + dark surfaces) fused with liquid glass web effects (backdrop-filter blur, layered highlights, adaptive tinting, morphing transitions). Dark-first, glass-elevated.

## Quick Start

1. **Copy** `arcan-glass/assets/globals.css` into your Next.js project as `app/globals.css`
2. **Import** in your layout: `import "./globals.css"`
3. **Use** glass classes: `<div class="glass-card">`, `<button class="glass-button glass-button-primary">`

All shadcn/ui components automatically pick up the Arcan Glass theme.

## Design Principles

1. **Dark-first** -- dark mode is the default; light mode is supported but secondary
2. **Glass is earned** -- only key surfaces get `backdrop-filter`; limit to 3-5 per viewport
3. **Brand through surface** -- surface hue 275 (blue-purple) connects all surfaces to AI Blue
4. **OKLCh primary** -- perceptually uniform lightness for clean depth scales and natural color mixing
5. **Additive on shadcn** -- glass effects layer on top of shadcn/ui, never replacing base accessibility
6. **Motion with purpose** -- every animation communicates state; reduced motion is always respected
7. **Token-prefixed** -- all custom properties use `--ag-` prefix to avoid collisions

## Glass Effect System

Every glass component is built from 4 composable layers:

| Layer | Technique | Purpose |
|-------|-----------|---------|
| 1. Backdrop blur | `backdrop-filter: blur() saturate()` | Frosted glass foundation |
| 2. Highlight | `::before` with top-edge gradient | Light reflection / depth cue |
| 3. Shadow | Multi-level `box-shadow` | Elevation / grounding |
| 4. Adaptive tint | `color-mix(in oklab)` | Contextual color pickup |

Three intensity presets: `glass-subtle` (40% / 8px), `glass` (60% / 16px), `glass-heavy` (80% / 24px).

## Brand Colors

| Token | Color | Usage |
|-------|-------|-------|
| `--ag-ai-blue` | `oklch(0.55 0.25 260)` / `#0066FF` | Primary, interactive, links |
| `--ag-web3-green` | `oklch(0.72 0.19 155)` / `#00CC66` | Accent, success, web3 |

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

| Animation | Tailwind | Duration | Usage |
|-----------|----------|----------|-------|
| Glow pulse | `animate-glow-pulse` | 2s loop | Active/loading states |
| Glass reveal | `animate-glass-reveal` | 0.5s once | Entry animations |
| Gradient flow | `animate-gradient-flow` | 8s loop | Hero backgrounds |

## Resources

### references/
- `color-system.md` -- Full OKLCh palette, hex fallbacks, surface scale, text hierarchy
- `design-tokens.md` -- Shadows, blur, radius, spacing, typography, transitions
- `glass-components.md` -- 4-layer glass system, component CSS patterns + Tailwind composition
- `animation-patterns.md` -- Glow pulse, hover lift, morph, scroll reveal, gradient flow
- `tailwind-integration.md` -- @theme inline wiring, @utility blocks, shadcn mapping, cva extensions

### assets/
- `globals.css` -- Drop-in CSS file with all tokens, glass utilities, components, and animations
