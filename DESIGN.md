---
name: Rate & Pricing Calculator
description: A pricing workbench on the Pumice design system, where the margin verdict, not the price, is the loudest element.
system: Pumice
reference: https://granqvistsanna-web.github.io/pumice/
tokens: https://granqvistsanna-web.github.io/pumice/tokens.css
font: Inter (Google Fonts), weights 400 and 500
---

# Design System: Rate & Pricing Calculator

## Overview

The calculator is built on **Pumice**. All colour, radius, spacing, shadow and motion values come
from Pumice's `tokens.css`, linked in the page head together with Inter from Google Fonts. The page
adds rules only. It defines no page-level custom properties, so nothing collides with Pumice's
`:root[data-theme="dark"]` block.

The live reference and component recipes are at https://granqvistsanna-web.github.io/pumice/.

**Thesis.** A consultant at a desk composes a defensible price, reads one verdict and copies text
into a proposal. The verdict leads the Breakdown panel, and on one column the Breakdown panel
leads the page.

## Theme

- Light first. With no stored choice the page follows the system through the tokens'
  `prefers-color-scheme` block.
- A small inline script in the head reads `localStorage.theme` (`"light"` or `"dark"`) and stamps
  `data-theme` on `<html>` before first paint. The app has no theme toggle; the script is there so
  a stored choice is honoured.
- `theme-color` has a light value (#ffffff) and a dark value (#000000), split by media query.

## Colour

Only Pumice tokens are used:

- **Ink ladder:** `--ink` for headings, values and totals; `--ink-2` for body and labels; `--ink-3`
  for field labels and resting icons; `--ink-4` for hints, effects (`→ +2 400 kr`), the footer and
  muted table rows.
- **Surfaces:** `--bg` for the page, `--surface` for the two panels, `--elev` for the dialog, the
  selected segment and the one-off line's editable cells.
- **Fills are washes, not borders:** `--wash` for control rows, quote lines, rate rows, quiet
  buttons, segmented tracks and the passing verdict; `--wash-2` on hover. Hairlines (`--hairline`)
  only divide: switch rows, table total rules and the save bar.
- **Ink fill** (`--ink` with `--on-ink`) is the loudest voice. It is used for the primary button,
  danger confirms, the toast, a checked switch, and the warn and fail verdicts.
- **Focus** is a 2px `--signal` outline with a 2px offset.
- No other hue is used. Danger is wording plus the ink fill, never red; verdicts differ by icon,
  wording and fill, never by colour.

## Typography

Inter only, weights 400 and 500 only, with no monospace anywhere. `font-variant-numeric:
tabular-nums` is set on `body` and on tables, so money, rates and hours never shift width.

| Role | Spec | Used for |
| --- | --- | --- |
| Display | 40 / 1.1 / 500 / -2% | Quote total (30px title size below 600px) |
| Heading | 26 / 1.2 / 500 / -1% | Panel titles; retainer key figures |
| Panel title | 17 / 1.25 / 500 / -2% | Dialog title |
| Body | 15 / 1.5 / 400, `--ink-2` | Labels, table left cells |
| Brand | 15 / 1.4 / 500, `--ink` | App name in the bar |
| UI | 14–15 / 500 | Buttons, values, toast |
| Section | 13 / 1.5 / 500, `--ink` | `h3` section labels |
| Small | 13 / 1.5, `--ink-4` | Hints, effects, footer, sub and muted rows, segmented labels |
| Micro | 12 / 1.6 / 500, `--ink-3` | Field labels above segmented controls, column heads |

There are no uppercase tracked labels.

## Layout

- One centred column, max 1060px. Gutters are 24px, and 16px at 600px wide and below.
- **Bar:** a sticky frosted header (`--frost`, saturate 1.4, blur 12px), at least `--h-bar` tall,
  running full bleed.
- **Panels:** `--surface`, 28px radius (`--r-card`), 24px padding (20/16px below 600px),
  `--panel-gap` between them.
- **At 860px and wider:** two columns (inputs, then Breakdown). When the window is also at least
  780px tall, Breakdown is sticky under the bar.
- **Below 860px:** the columns stack with Breakdown first.
- **At 600px and below:** the table re-grids to label and amount, sub-lines go full width, and the
  segmented pickers stack.
- **At 520px and below:** control rows wrap their money effect onto a second line, and rate rows
  re-grid into named areas.
- At 375px there is no horizontal page scroll.

## Shape

- **Controls are pills** (`--r-pill`): buttons, inputs, selects, segmented tracks and segments,
  switches, the icon button and the toast.
- **Cards and panels:** 28px (`--r-card`).
- **Inner panels:** 12px (`--r-inner`). These are the control rows, quote lines, rate rows and the
  verdict. Inputs nested inside them use 10px (`--r-bar`).
- **Outline buttons** (the add buttons "One-off line" and "Add rate") use a 1px `--line-ctl` inset
  ring, which goes to .28 ink on hover.
- **Shadows only on what floats:** `--shadow-1` for the selected segment, `--float` for the dialog
  and toast. Panels are flat.

## Icons

Inline SVG symbols with Lucide geometry: 24 grid, stroke-width 2, round caps and joins, no fill.
The icons are sliders-horizontal, chevron-left, x, check, plus, trash-2, circle-check,
triangle-alert and circle-x.

- Sizes: 18px by default (`--icon`), 15px inside buttons (`--icon-sm`).
- Icon buttons rest at `--ink-3` and go to `--ink` on hover.
- `pointer-events: none` on `.ic` is load-bearing, because the delegated click handler reads
  `e.target.dataset`.
- The select caret is a Lucide chevron-down data URI in a mid grey that works on both themes.

## Components

- **Segmented control (`.seg`):** a pill track on a wash with 2px padding. Segments are 36px pills
  in 13px/500 `--ink-4`. The selected segment is `--elev` + `--ink` + `--shadow-1`, and segments
  press to scale .95. Every enum uses one: mode, currency, start from, and ex/ink moms.
- **Control row (`.crow`):** label left, tabular value right, on a 44px wash bar. The input is
  transparent, right-aligned and 108px wide. A percentage row shows its money effect in `.eff`.
- **Quote line and rate row:** the same shell. A one-off line lifts its three cells onto `--elev`.
  Each row ends in an icon button (`.del`): a 36px circle at `--ink-3` that gains a wash on hover
  and presses to scale .92.
- **Switch (`.check input`):** a Pumice switch drawn on the native checkbox, 50×30. The track is
  ink .16 and turns `--ink` when on. The knob is a radial gradient that slides with
  `--morph-ease`. The whole row is the hit area (52px), with the switch on the right and the
  money effect just before it.
- **Buttons:** 40px pills, 15px/500. Quiet is the default (`--wash`, then `--wash-2` on hover).
  Primary and danger use the ink fill and drop to .86 opacity on hover. Outline is used for the
  add buttons. Buttons press to scale .96. Disabled is .4 opacity.
- **Verdict (`.margin-line`):**
  - Pass: a wash panel with circle-check.
  - Warn: an ink panel with triangle-alert.
  - Fail: an ink panel with circle-x.
  - The culprit clause is 400 at .72 opacity.
  - Without hours or without an internal cost set, a hint replaces the verdict.
- **Breakdown table:** borderless with tabular numerals. Right cells are 500 `--ink`, and sub and
  muted rows are 13px `--ink-4`. Total and rule rows carry a hairline.
- **Toast:** an ink pill with `--float`. It fades and rises with `--spring`.
- **Dialog:** `--elev`, 28px radius, `--float`. The backdrop is `--veil` with blur(12px)
  saturate(1.3). It has two equal pill actions: quiet Cancel and an ink confirm.

## Motion

- Pumice tokens throughout: `--t-color` and `--t-fade` for colour and opacity, `--t-press` with
  `--spring-soft` for the press `scale`, and `--t-move` with `--rise` for the view slide (14px).
- Press scales: .96 for buttons, .95 for segments, .92 for icon buttons.
- `prefers-reduced-motion` zeroes the tokens and clamps every transition and animation.

## Touch and accessibility

- On `pointer: coarse`, every input, select, button and segment is at least 44px tall
  (`--h-touch`), and icon buttons are 44×44.
- `prefers-contrast: more` adds a `--ring` to controls.
- Recomputed totals and verdicts are announced through a debounced polite live region, and toasts
  and status lines have `role="status"`.
