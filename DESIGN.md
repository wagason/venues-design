# Design System

## Theme

Light. Bright, airy, outdoor feel — optimized for daylight and mobile use. Users are often outside or in well-lit spaces.

## Color Strategy

Restrained: tinted neutrals + one committed accent. The accent carries brand identity; neutrals stay warm and intentional.

### Palette (OKLCH)

| Role | Token | OKLCH | Usage |
|---|---|---|---|
| Accent | `--color-accent` | `oklch(0.65 0.15 200)` | CTAs, active states, booking buttons, key highlights |
| Accent hover | `--color-accent-hover` | `oklch(0.58 0.17 200)` | Hover/press states on accent elements |
| Accent subtle | `--color-accent-subtle` | `oklch(0.95 0.03 200)` | Tinted backgrounds, badges, subtle highlights |
| Neutral 900 | `--color-text` | `oklch(0.18 0.008 200)` | Primary text — tinted toward accent, never pure black |
| Neutral 600 | `--color-text-secondary` | `oklch(0.45 0.008 200)` | Secondary text, labels |
| Neutral 200 | `--color-border` | `oklch(0.88 0.006 200)` | Borders, dividers |
| Neutral 50 | `--color-surface` | `oklch(0.975 0.004 200)` | Page background — barely tinted |
| White | `--color-surface-raised` | `oklch(0.99 0.003 200)` | Cards, elevated surfaces — never pure white |

### Color Rules

- Never use `#000` or `#fff`. All neutrals tinted toward accent hue (200).
- Accent used on primary CTAs, active nav, booking flows, and key data points. Not decorative.
- Status colors: success `oklch(0.7 0.15 145)`, warning `oklch(0.75 0.15 85)`, error `oklch(0.6 0.18 25)`.

## Typography

### Font Stack

- **Display / Headings**: Inter, system-ui, sans-serif — bold weights (700–800). Geometric, sharp, athletic.
- **Body**: Inter, system-ui, sans-serif — regular (400) and medium (500). Clean, highly legible.

Load via `@fontsource/inter` or Google Fonts. Fallback to system-ui.

### Scale

| Level | Size | Weight | Line height | Usage |
|---|---|---|---|---|
| Display | 2.25rem (36px) | 800 | 1.1 | Hero headlines, key numbers |
| H1 | 1.75rem (28px) | 700 | 1.2 | Page titles |
| H2 | 1.375rem (22px) | 700 | 1.25 | Section headings |
| H3 | 1.125rem (18px) | 600 | 1.3 | Card titles, subheadings |
| Body | 1rem (16px) | 400 | 1.5 | Default text |
| Body small | 0.875rem (14px) | 400 | 1.5 | Labels, metadata |
| Caption | 0.75rem (12px) | 500 | 1.4 | Timestamps, badges |

Scale ratio: ~1.25 between steps.

### Rules

- Body line length: max 70ch.
- Hierarchy through scale + weight contrast, never color alone.
- Uppercase only for badges and micro-labels, tracked at 0.05em.

## Spacing

Base unit: 4px. Scale: 4, 8, 12, 16, 20, 24, 32, 40, 48, 64, 80.

- Section padding: 48–64px vertical, 24px horizontal (mobile: 32px vertical, 16px horizontal).
- Card padding: 20–24px.
- Inline spacing: 8px between related items, 16px between groups.
- Vary rhythm — avoid uniform padding everywhere. Tighter near content, looser between sections.

## Elevation

Minimal. Light theme doesn't need heavy shadows.

- Level 0: flat (page background)
- Level 1: `0 1px 3px oklch(0.18 0.008 200 / 0.08)` — cards, dropdowns
- Level 2: `0 4px 12px oklch(0.18 0.008 200 / 0.12)` — modals, popovers
- Level 3: `0 8px 24px oklch(0.18 0.008 200 / 0.16)` — floating elements

No glassmorphism. No heavy drop shadows.

## Border Radius

- Small (badges, chips): 6px
- Medium (cards, inputs): 12px
- Large (modals, panels): 16px
- Pill (tags, avatars): 999px

Consistent, not excessive. Rounded enough to feel friendly, not so much it feels卡通.

## Motion

Snappy & physical. Ease-out with exponential curves.

- Default easing: `cubic-bezier(0.16, 1, 0.3, 1)` (ease-out-expo)
- Duration: 150ms micro (hover, focus), 250ms small (expand, toggle), 400ms large (page transitions)
- No bounce, no elastic, no spring physics.
- Animate transform and opacity only — never animate layout properties.
- Subtle parallax on scroll for venue images. Elements should feel like they have physical mass.

## Components

### Buttons

- **Primary**: accent background, white text, 12px radius, bold weight. Hover: darken accent.
- **Secondary**: accent outline, accent text, transparent background. Hover: accent subtle fill.
- **Ghost**: no border, neutral text, subtle hover background.
- Min height: 44px (touch target). Padding: 12px 24px.

### Cards

- Surface-raised background, 12px radius, level 1 shadow.
- No side-stripe borders. No nested cards.
- Image on top, content below. Padding: 20px.
- Hover: subtle lift (translateY -2px, shadow increase).

### Inputs

- Neutral-200 border, 12px radius, 44px min height.
- Focus: accent border + subtle accent ring.
- Labels above, not floating.

### Navigation

- Top nav for mobile, optional sidebar for desktop.
- Active state: accent text + accent-subtle background.
- No hamburger menus for primary nav — show key items directly.
