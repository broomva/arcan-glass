# Arcan Glass — Color System

## Color Space

Arcan Glass uses **OKLCh** as the primary color space for perceptually uniform lightness across the surface depth scale. Hex fallbacks are provided via `@supports not (color: oklch(0 0 0))`.

All surface colors share **hue 275°** (blue-purple), connecting them subtly to the AI Blue brand without competing with it.

---

## Brand Colors

| Token | OKLCh | Hex | Usage |
|-------|-------|-----|-------|
| `--ag-ai-blue` | `oklch(0.55 0.25 260)` | `#0066FF` | Primary, interactive, focus, links |
| `--ag-web3-green` | `oklch(0.72 0.19 155)` | `#00CC66` | Accent, success, web3 branding |

On P3 displays, chroma is boosted: AI Blue → `0.28`, Web3 Green → `0.22`.

---

## Surface Scale

Surfaces form a lightness ramp at hue 275° (blue-purple). Each step is ~0.03-0.05 L apart in OKLCh for perceptual consistency.

### Dark Mode (Default)

| Token | OKLCh | Hex | Usage |
|-------|-------|-----|-------|
| `--ag-bg-deep` | `oklch(0.12 0.02 275)` | `#12121A` | Body background |
| `--ag-bg-dark` | `oklch(0.15 0.04 245)` | `#001F3F` | Secondary bg, sidebar |
| `--ag-bg-surface` | `oklch(0.17 0.03 275)` | `#1A1A2E` | Cards, panels |
| `--ag-bg-elevated` | `oklch(0.22 0.03 275)` | `#232340` | Popovers, dialogs |
| `--ag-bg-hover` | `oklch(0.26 0.03 275)` | `#2A2A4A` | Hover states |

### Light Mode

| Token | OKLCh | Hex | Usage |
|-------|-------|-----|-------|
| `--ag-bg-deep` | `oklch(0.98 0.005 275)` | — | Body background |
| `--ag-bg-dark` | `oklch(0.96 0.008 275)` | — | Secondary bg |
| `--ag-bg-surface` | `oklch(0.99 0.003 275)` | — | Cards |
| `--ag-bg-elevated` | `oklch(1 0 0)` | `#FFFFFF` | Popovers |
| `--ag-bg-hover` | `oklch(0.95 0.01 275)` | — | Hover states |

---

## Text Hierarchy

### Dark Mode

| Token | OKLCh | Hex | Usage |
|-------|-------|-----|-------|
| `--ag-text-primary` | `oklch(0.98 0 0)` | `#FFFFFF` | Headings, body |
| `--ag-text-secondary` | `oklch(0.70 0.02 275)` | `#A0A0B8` | Labels, descriptions |
| `--ag-text-muted` | `oklch(0.50 0.02 275)` | `#6B6B80` | Placeholders, captions |
| `--ag-text-disabled` | `oklch(0.38 0.02 275)` | `#4A4A5C` | Disabled text |

### Light Mode

| Token | OKLCh | Hex | Usage |
|-------|-------|-----|-------|
| `--ag-text-primary` | `oklch(0.15 0.02 275)` | — | Headings, body |
| `--ag-text-secondary` | `oklch(0.40 0.02 275)` | — | Labels |
| `--ag-text-muted` | `oklch(0.55 0.02 275)` | — | Placeholders |
| `--ag-text-disabled` | `oklch(0.70 0.01 275)` | — | Disabled |

---

## Semantic Colors

| Token | OKLCh | Hex | Usage |
|-------|-------|-----|-------|
| `--ag-success` | `oklch(0.72 0.19 155)` | `#00CC66` | Success, confirmed |
| `--ag-warning` | `oklch(0.87 0.18 85)` | `#FFD60A` | Caution, pending |
| `--ag-error` | `oklch(0.58 0.24 27)` | `#FF3B30` | Error, destructive |
| `--ag-info` | `oklch(0.55 0.25 260)` | `#0066FF` | Informational |

---

## Border Scale

| Token | Value (Dark) | Usage |
|-------|-------------|-------|
| `--ag-border-subtle` | `oklch(0.30 0.02 275 / 0.40)` | Glass edges, dividers |
| `--ag-border-default` | `oklch(0.40 0.02 275 / 0.50)` | Input borders, cards |
| `--ag-border-strong` | `oklch(0.50 0.02 275 / 0.60)` | Active borders |
| `--ag-border-focus` | `oklch(0.55 0.25 260)` | Focus rings (= AI Blue) |

---

## Glass Opacity Scale

| Token | Dark | Light | Usage |
|-------|------|-------|-------|
| `--ag-glass-light` | 40% | 60% | Subtle backgrounds, inputs |
| `--ag-glass-medium` | 60% | 75% | Cards, panels (default) |
| `--ag-glass-heavy` | 80% | 90% | Nav bars, modals, sidebars |

These values control the `color-mix()` ratio in glass surfaces — higher opacity = less transparency, more grounding.

---

## Chart Colors

| Token | Value | Usage |
|-------|-------|-------|
| `--chart-1` | AI Blue | Primary series |
| `--chart-2` | Web3 Green | Secondary series |
| `--chart-3` | `oklch(0.65 0.22 330)` | Tertiary (pink-purple) |
| `--chart-4` | Warning yellow | Fourth series |
| `--chart-5` | `oklch(0.60 0.20 30)` | Fifth series (warm red) |

---

## Usage in Tailwind

All color tokens are mapped to Tailwind via `@theme inline`:

```html
<div class="bg-ai-blue text-text-primary">AI Blue</div>
<div class="bg-bg-surface border-border">Surface card</div>
<div class="text-web3-green">Accent text</div>
```

shadcn/ui semantic classes work as expected:
```html
<div class="bg-primary text-primary-foreground">Button</div>
<div class="bg-card text-card-foreground">Card</div>
```
