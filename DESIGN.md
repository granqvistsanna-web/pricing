---
name: Rate & Pricing Calculator
description: A monochrome pricing workbench where the margin verdict, not the price, is the loudest element.
colors:
  bg-0: "#0f0f0f"
  bg-1: "#171717"
  bg-2: "#222222"
  bg-3: "#2e2e2e"
  bg-4: "#3a3a3a"
  ink-hi: "#f2f2f2"
  ink-mid: "#b3b3b3"
  ink-low: "#8a8a8a"
  ink-faint: "#5f5f5f"
  hairline: "rgba(255,255,255,.08)"
  inverse-bg: "#ffffff"
  inverse-ink: "#101010"
typography:
  display:
    fontFamily: "Geist, -apple-system, BlinkMacSystemFont, Segoe UI, Roboto, sans-serif"
    fontSize: "31px"
    fontWeight: 700
    lineHeight: 1.05
    letterSpacing: "-0.02em"
    fontFeature: "tabular-nums"
  title:
    fontFamily: "Geist, -apple-system, BlinkMacSystemFont, Segoe UI, Roboto, sans-serif"
    fontSize: "19px"
    fontWeight: 650
    letterSpacing: "-0.005em"
  label:
    fontFamily: "Geist, -apple-system, BlinkMacSystemFont, Segoe UI, Roboto, sans-serif"
    fontSize: "11px"
    fontWeight: 600
    letterSpacing: "0.14em"
  body:
    fontFamily: "Geist, -apple-system, BlinkMacSystemFont, Segoe UI, Roboto, sans-serif"
    fontSize: "15px"
    fontWeight: 400
    lineHeight: 1.5
    fontFeature: "tabular-nums"
  value:
    fontFamily: "Geist, -apple-system, BlinkMacSystemFont, Segoe UI, Roboto, sans-serif"
    fontSize: "15px"
    fontWeight: 500
    fontFeature: "tabular-nums"
  hint:
    fontFamily: "Geist, -apple-system, BlinkMacSystemFont, Segoe UI, Roboto, sans-serif"
    fontSize: "13px"
    fontWeight: 400
    lineHeight: 1.55
rounded:
  xs: "6px"
  sm: "8px"
  md: "12px"
  lg: "16px"
  xl: "20px"
  control-inner: "9px"
  pill: "999px"
spacing:
  cell-gap: "8px"
  row-gap: "10px"
  control-pad: "16px"
  panel-pad: "20px"
  page-gutter: "24px"
components:
  panel:
    backgroundColor: "{colors.bg-1}"
    rounded: "{rounded.xl}"
    padding: "{spacing.panel-pad}"
  input:
    backgroundColor: "{colors.bg-2}"
    textColor: "{colors.ink-hi}"
    rounded: "{rounded.md}"
    padding: "0 16px"
    height: "48px"
  input-focus:
    backgroundColor: "{colors.bg-3}"
  control-row:
    backgroundColor: "{colors.bg-2}"
    rounded: "{rounded.md}"
    padding: "4px 6px 4px 16px"
    height: "48px"
  segmented:
    backgroundColor: "{colors.bg-2}"
    rounded: "{rounded.md}"
    padding: "3px"
    height: "48px"
  segmented-selected:
    backgroundColor: "{colors.bg-3}"
    textColor: "{colors.ink-hi}"
    rounded: "{rounded.control-inner}"
  button-ghost:
    backgroundColor: "{colors.bg-2}"
    textColor: "{colors.ink-mid}"
    rounded: "{rounded.md}"
    padding: "0 18px"
    height: "48px"
  button-ghost-hover:
    backgroundColor: "{colors.bg-3}"
    textColor: "{colors.ink-hi}"
  button-primary:
    backgroundColor: "{colors.inverse-bg}"
    textColor: "{colors.inverse-ink}"
    rounded: "{rounded.md}"
    padding: "0 18px"
    height: "48px"
  button-dashed:
    backgroundColor: "transparent"
    textColor: "{colors.ink-low}"
    rounded: "{rounded.md}"
    height: "48px"
  button-text:
    backgroundColor: "transparent"
    textColor: "{colors.ink-low}"
    padding: "0 10px"
    height: "48px"
  verdict-pass:
    backgroundColor: "{colors.bg-2}"
    textColor: "{colors.ink-hi}"
    rounded: "{rounded.md}"
    padding: "13px 16px"
  verdict-fail:
    backgroundColor: "{colors.inverse-bg}"
    textColor: "{colors.inverse-ink}"
    rounded: "{rounded.md}"
    padding: "13px 16px"
  toast:
    backgroundColor: "{colors.inverse-bg}"
    textColor: "{colors.inverse-ink}"
    rounded: "{rounded.pill}"
    padding: "11px 18px"
  dialog:
    backgroundColor: "{colors.bg-1}"
    textColor: "{colors.ink-mid}"
    rounded: "{rounded.xl}"
---

# Design System: Rate & Pricing Calculator

## Overview

**Creative North Star: "Graphite Console"**

A pricing workbench styled as a monochrome control console. Every surface is a step on one grey ladder, every word is a step on one ink ladder, and the only accent the system owns is the inverse pair — pure white carrying near-black ink. That accent is budgeted, not decorative: it is spent on the primary action, the toast, the dialog's confirm, and — above all — a failing margin verdict. The verdict, not the price, is the loudest element on screen; the system explicitly refuses the pastel SaaS-calculator card collage.

The console is dark-only by design (`color-scheme: dark`, theme-color #0f0f0f). There is no light theme and none is planned; the inverse pair only works as an alarm because the rest of the room stays dark. Density is deliberate but calm: 48px control rows, tracked-caps section labels over hairlines, tabular numerals everywhere money appears, and motion held to 120/180ms nudges.

This is an instrument for a consultant at a desk composing a defensible price — deliberation and legibility over spectacle. Elevation is lightness, not shadow. State is wording plus one ladder step, never a new color.

**Key Characteristics:**
- Dark-only monochrome; a single grey ramp from #0f0f0f to #ffffff supplies every surface and every ink.
- The white/near-black inverse pair is the sole accent, reserved for the primary action and for alarm.
- Verdicts speak through surface, icon, and wording — never through color.
- One control grammar: 48px rows on bg-2, recessed transparent inputs, segmented pickers for every enum.
- Geist variable font with tabular numerals set globally; the money total is the only display-scale type.
- Flat world: no box-shadows; depth is a lightness ladder plus hairlines.

## Colors

One achromatic ramp, split into a five-step surface ladder, a four-step ink ladder, a hairline, and the inverse accent pair.

### Primary
- **Inverse White** (#ffffff) with **Inverse Ink** (#101010): the system's only accent. Used on exactly four things: the primary button (`Copy for client`, dialog confirm — including the danger confirm), the warn/fail state of the margin verdict row, and the toast. Full inversion is the loudest voice the system has, which is why it is rationed.

### Neutral — surface ladder (elevation is lightness)
- **bg-0 Console Black** (#0f0f0f): the page itself and the sticky header.
- **bg-1 Panel Graphite** (#171717): panels (sections) and the dialog.
- **bg-2 Row Graphite** (#222222): every interactive resting surface — control rows, inputs, selects, buttons, segmented tracks, checkbox wells, the passing verdict row.
- **bg-3 Raised Graphite** (#2e2e2e): the state step — hover, focus fill, selected segment, checked checkbox.
- **bg-4 Top Graphite** (#3a3a3a): the top rung; reserved headroom above bg-3 (defined in the ladder, currently unused by any rule).

### Neutral — ink ladder
- **ink-hi Headline White** (#f2f2f2): titles, values, totals, verdict text, focused/hovered labels, links.
- **ink-mid Working Grey** (#b3b3b3): default body ink — labels, table left cells, resting button text.
- **ink-low Support Grey** (#8a8a8a): hints, section labels, effects (`→ +2 400 kr`), placeholders, footer, resting ghost/dashed/text buttons. **This is the floor for informational text.**
- **ink-faint Whisper Grey** (#5f5f5f): decoration only — the resting link-underline tint. Never used for words.
- **Hairline** (rgba(255,255,255,.08)): every structural line — header bottom, section-label underlines, checklist separators, table rules, the dialog border.

### Named Rules
**The One-Step Rule.** State is one ladder step up plus brighter ink: bg-2 at rest → bg-3 on hover/focus/selected/checked, ink-mid or ink-low → ink-hi. Nothing signals state with a hue.

**The Inverse Budget Rule.** The inverse pair appears only on the primary action, the failing/warning verdict, the toast, and the dialog confirm. Danger is not red — the danger confirm uses the same inverse styling; the words carry the danger.

**The Contrast-Floor Rule.** Informational text never drops below ink-low (#8a8a8a). Muted states are expressed by wording ("Unsaved quote") at ink-low, not by dimming further; ink-faint exists only for non-text decoration.

Dark-only is a commitment, not an omission: `color-scheme: dark` is declared, `prefers-color-scheme` is deliberately absent, and the only media-driven palette change is `prefers-contrast: more` (hairline → rgba(255,255,255,.3), ink-low → #a9a9a9, ink-faint → #8a8a8a, bg-2 → #262626, bg-3 → #343434, plus 1px inset rings on controls).

## Typography

**Display/Body Font:** Geist (variable, 100–900), self-hosted woff2, preloaded, `font-display: swap` (fallback: -apple-system, BlinkMacSystemFont, "Segoe UI", Roboto, sans-serif)
**Mono Font:** ui-monospace / SFMono-Regular / Menlo — only for the `?test` self-check output (12px)

**Character:** One quiet grotesk doing everything, differentiated by weight and tracking rather than family. `font-variant-numeric: tabular-nums` is set on `body`, so every number in the app — inputs, tables, effects, totals — is tabular by inheritance. Money never wobbles.

### Hierarchy
- **Display** (700, 31px, 1.05, −0.02em): the quote total — the one display-scale number, in the Breakdown table's total row. Drops to 26px below 600px. A secondary display step (650, 22px, −0.015em) carries the retainer's two key figures (20px below 600px).
- **Title** (650, 19px, −0.005em): panel titles ("Quote", "Breakdown"), in ink-hi. The app header title is a near-twin (650, 17px, −0.01em); the dialog title is a centered 700/20px.
- **Label** (600, 11px, +0.14em, UPPERCASE, ink-low): caps section labels — both the `h3` variant sitting on a hairline underline (10px padding-bottom) and the field-label variant above segmented controls. The system's structural wayfinding.
- **Body** (400, 15px, 1.5, ink-mid): labels, checklist rows, table left cells. Base for all controls (`font: inherit`).
- **Value** (500, 15px, ink-hi): the right half of every label/value pair — input text, table amounts, resting button labels. Values are one weight step heavier than their labels and always tabular.
- **Hint** (400, 13px, 1.55, ink-low): explanations, money effects (`.eff`), footer, save status. Smaller companions: 12.5px quote label/legend, 12px column headers, 14px segmented buttons / toast / dialog message.

### Named Rules
**The Tabular Rule.** Tabular numerals are global. Any new number — in a row, a table, or a button — inherits them; do not opt out.

**The Caps-Over-Hairline Rule.** Sections are introduced by 11px/600/+0.14em uppercase ink-low labels; the `h3` form always carries its hairline underline. No other element uses letterspaced caps.

## Layout

A single centered column, max-width 1060px with 24px gutters (14px below 600px), under a sticky bg-0 header closed by a hairline (13px vertical padding, z-index 20). Content lives in bg-1 panels with 20px radius and 20px padding (16px padding, 16px radius below 600px).

**Two-column split ≥860px:** the view is a grid of `minmax(0,1fr)` (inputs) and `minmax(0,.94fr)` (Breakdown), 20px gap, top-aligned. When the viewport is also ≥780px tall, the Breakdown panel is sticky at `top: 84px` so the verdict never scrolls away.

**Below 860px** the columns stack — and the Breakdown panel is ordered first (`order: -1`): the verdict is why the tool exists, so on one column it must not sit below a page of inputs.

**Rhythm:** base-4-flavored with a 2px grain. Named steps: 48px control-row height (`--row-h`), 16px control padding (`--pad-control`), 20px panel padding (`--pad-panel`), 10px row gap (`--gap-row`), 8px cell gap inside rows and bars. Section labels sit 28px below the previous block; panel titles carry 18px bottom margin.

**Compaction ladder:**
- **≤600px:** gutters 14px; panel padding 16px/radius 16px; touch targets rise to 44px (delete buttons, row inputs, selects); the breakdown table re-grids each row to `label | amount` columns and sub-lines to full width; display total 26px.
- **≤520px:** control rows wrap to two lines — label + value first, the money-effect line (`.eff`) on its own full-width right-aligned line below; rate-card rows re-grid into named areas (label spans the top, rate + currency below, delete at right); the rate-card column header row disappears; one-off line labels take the full width.

Mode/currency/direction visibility is gated by body classes (`mode-*`, `dir-*`, `cur-*`) toggling `display` — the layout never reflows for state it isn't showing.

## Elevation & Depth

**No shadows.** There is not a single decorative `box-shadow` in the system; elevation is lightness, exactly as the token comment states ("elevation is lightness, not shadow"). Higher on the surface ladder reads as closer: page (bg-0) → panel (bg-1) → row (bg-2) → state (bg-3). The two exceptions prove the rule: `prefers-contrast: more` adds 1px inset hairline rings to controls (a border in disguise, not depth), and the modal separates itself with a 1px hairline border plus a rgba(0,0,0,.62) backdrop dim — darkness behind, not shadow beneath.

Wells invert the ladder: the three editable cells of a one-off quote line recess to bg-1 against their bg-2 row, so their bounds read as *cut into* the row rather than raised off it. Inputs inside rows are fully transparent at rest and only fill (bg-3) when hovered or focused.

### Named Rules
**The Lightness-Is-Elevation Rule.** To raise something, move it one step up the bg ladder; to recess it, one step down. Never introduce a shadow to do either.

## Shapes

Nested rounded rectangles with a concentric radius ladder: 6 / 8 / 12 / 16 / 20px (`--r-xs` through `--r-xl`), plus two derived steps that live in rules rather than tokens — 9px for controls nested inside 12px rows and segmented tracks, and 999px for the toast pill. Small one-offs: 7px checkbox wells (24×24), 10px icon-only delete buttons.

Containers are 20px (panels, dialog), interactive rows and controls are 12px, hint-level buttons are 8px. The nesting is what keeps corners looking parallel: a 12px row with ~3–4px inset holds 9px inner controls.

Borders barely exist. The hairline is a divider, not a box: rows and panels are borderless fills. The only outlined shapes are the checkbox well (1px hairline, dropped once checked), the dialog (1px hairline), and the dashed add-buttons — 1px dashed rgba(255,255,255,.22) (rgba(255,255,255,.4) on hover), the system's "empty slot" affordance.

**Iconography is part of the form language:** one family (Phosphor, MIT, 256 viewBox), inlined as `<symbol>` sprites so the FX call stays the app's only network request. Fill weight where mass helps — verdict badges, back caret, trash, sliders; regular (stroke-drawn path) weight for bare marks — x, plus, check — so they read as glyphs, not chips. Standard size 16×16 (`.ic`), verdict icons 20×20. `pointer-events: none` on icons is load-bearing for event delegation.

## Components

### Segmented Control (`.seg`)
The system's one option picker — every enum (mode, currency, direction, ex/ink moms) uses it; there are no radio buttons or tab bars.
- **Track:** bg-2, 12px radius, 3px padding, 48px tall.
- **Segments:** transparent, 9px radius, 14px/500 ink-low, equal flex.
- **Selected:** `aria-pressed="true"` → bg-3 fill + ink-hi (the One-Step Rule verbatim).
- **Hover (unselected):** ink-mid, no fill. **Focus:** outline inset (−2px offset).
- Labelled by an 11px caps field label above the track.

### Control Row (`.crow`)
Label left, value right — the workhorse for every numeric setting.
- 48px min-height, bg-2, 12px radius, padding 4px 6px 4px 16px, 10px stacked gap.
- Label: 15px ink-mid, flexes; input: fixed 108px, right-aligned, transparent, 9px radius, 40px min-height.
- Percentage rows carry a money-effect span (`.eff`, 13px ink-low, e.g. `→ +2 400 kr`); below 520px the row wraps and the effect takes its own full-width right-aligned line.

### Quote-Line Row (`.lines > div`)
- Same shell as the control row (bg-2, 12px radius, 48px min-height); label holds the role name plus its rate (`× 1 000 kr` in 13px ink-low); hours input fixed 76px, right-aligned, transparent.
- **One-off variant:** three editable cells (label flex ≥90px, rate 92px, hours 76px) recessed to bg-1 so their bounds read on bg-2.
- **Orphan rate** (`span.bad`): flagged with ink-hi at 600 weight — emphasis, not color.
- Each row ends in a 40×40 icon-only remove button (regular-weight x).

### Rate-Card Row (`.rrow`)
- Grid `minmax(0,1fr) 104px 84px 40px`, 8px gaps, on the bg-2/12px shell; transparent full-width inputs and select inside.
- Headed once by `.cols-head` (same grid, 12px/500 ink-low, hidden below 520px, `aria-hidden`).
- Ends in a 40×40 delete button (filled trash). Below 520px it re-grids into label-spanning areas.

### Checklist Row (`.check`)
There are no switches in this system — boolean settings are checklist rows.
- 52px min-height, 15px ink-mid label, hairline separators between consecutive rows, whole row clickable.
- **Checkbox:** appearance-none 24×24 well, 7px radius, bg-2 + 1px hairline; checked → bg-3, border dropped, inlined 14px Phosphor check (data-URI, #f2f2f2). Hover (unchecked) → bg-3.
- Money effect (`.eff`) is pushed to the row's right edge.

### Buttons
All 48px min-height, 12px radius, 15px, centered inline-flex with 8px icon gap; active presses dim via `filter: brightness(.86)`; disabled is opacity .4.
- **Ghost (default):** bg-2, ink-mid, 500, padding 0 18px. Hover → bg-3 + ink-hi.
- **Primary inverse (`.primary`, and `.bad` for danger confirms):** inverse-bg/inverse-ink, 600. Hover keeps the inversion and dims (`brightness(.9)`). Danger is the same monochrome inversion — wording ("Delete rate"), not red.
- **Dashed (`.dashed`):** transparent, ink-low, 1px dashed rgba(255,255,255,.22), full-width (flexes ≥150px inside bars); the add-affordance ("One-off line", "Add rate"), always with a regular-weight plus. Hover brightens border (.4 alpha) and ink, never fills.
- **Text (`.text`):** transparent, ink-low, padding 0 10px; hover → ink-hi only.
- **Icon-only delete (`.del`):** 40×40 (44×44 ≤600px), 10px radius, transparent + ink-low → bg-3 + ink-hi on hover.
- Hint-level buttons shrink to 34px/13px with 8px radius.

### Inputs & Selects
- **Field at rest:** bg-2 fill, no border, 12px radius, 48px min-height, 0 16px padding, 15px/500 ink-hi text, ink-low/400 placeholder. Number spinners removed.
- **Hover and focus:** bg-3 (fill, not outline). Keyboard focus everywhere: 2px solid ink-low outline, 2px offset.
- **Nested in rows:** transparent at rest, 9px radius, 40px min-height, right-aligned when numeric.
- **Select:** appearance-none with an inlined Phosphor caret-down (data-URI, filled, #8a8a8a) at right 14px, 11px wide; 38px right padding; disabled at .45 opacity. In rate rows the caret tucks to 8px/28px.
- Numeric bounds clamp on commit (change), not mid-keystroke.

### Verdict Row (`.margin-line`) — the signature component
The reason the tool exists; it leads the Breakdown panel, above the arithmetic that supports it.
- **Shell:** 12px radius, padding 13px 16px, 15px/600/−0.005em, flex with a 20×20 filled icon (nudged 1px down), 16px bottom margin.
- **Pass (`good`):** quiet — bg-2 + ink-hi, filled circle-check. Speaks at control volume: "72,8 %: above your 30 % target".
- **Warn:** inverse-bg + inverse-ink, filled warning triangle: "24,1 %: below your 30 % target", plus a culprit clause when one lever alone would clear the target (`<small>` at inherit-size/500/72% opacity: "· Discount 55 % is what pushed you under").
- **Fail (`bad`):** same inversion, filled circle-x: "…: losing money", or "No revenue: this quote costs you money" when revenue ≤ 0.
- **Unearned states show no row:** without hours or without an internal cost set, a hint replaces the verdict — the inverse alarm is for real quotes gone wrong.
- State is icon + wording + surface. The `.good/.warn/.bad` text classes all resolve to ink-hi; color never differentiates verdicts.
- Every recompute is mirrored to a visually-hidden `aria-live="polite" aria-atomic` region, debounced 450ms: "18 400 kr ex moms. Margin verdict good: above 30 percent target." The margin detail block is itself `role="status"`.

### Breakdown Table
- Borderless; hairline top rules on `tr.rule` mark totals (14px top padding).
- Left cells 15px ink-mid; right cells right-aligned, nowrap, 15px/500 ink-hi.
- Sub-lines (`tr.sub`): 13px ink-low, indented 16px. Muted lines (`tr.muted`): 13px ink-low (moms, effective rate).
- Total row: 31px/700/−0.02em display figure. Retainer key rows: 22px/650.
- Below 600px each row becomes a two-column grid and the display sizes step down (26px/20px).

### Toast (`#toast`)
- Fixed, bottom-centered (24px), pill (999px), inverse pair, 14px/600, padding 11px 18px, max-width min(420px, 100vw−32px).
- Enters by fading and rising 10px over 180ms; auto-dismisses after 2.2s; `role="status" aria-live="polite"`; pointer-events none.

### Dialog (`#sysDialog`)
The system's only modal — prompts and confirms (no `window.confirm`).
- min(400px, 100vw−32px), bg-1, 1px hairline border, 20px radius, backdrop rgba(0,0,0,.62), 24px body padding.
- Centered 20px/700 title, 14px ink-low message, 13px ink-low input label, full-width input.
- Two equal-width actions: ghost Cancel + inverse confirm; destructive confirms swap `.primary` for `.bad` — identical inverse styling, the label does the warning.

### View Transition
Quote ↔ Settings views slide in 14px (from the direction they sit) while fading, 180ms `cubic-bezier(.25,.1,.25,1)`; control state changes use the 120ms step. Both collapse to ~0 under `prefers-reduced-motion`.

## Do's and Don'ts

### Do:
- **Do** express every state as one ladder step up plus brighter ink: bg-2 → bg-3 with ink-mid/ink-low → ink-hi. Hover, focus fill, selected, and checked are all the same move.
- **Do** keep verdicts monochrome and redundant: pass = quiet bg-2 row, warn/fail = inverse row, with a distinct filled Phosphor icon *and* distinct wording per state — any one channel alone must carry the meaning.
- **Do** keep informational text at or above ink-low (#8a8a8a); express de-emphasis through wording, size (13px), or weight, never a dimmer grey.
- **Do** keep all numerals tabular and money right-aligned; the 31px/700 total is the only display-scale number per panel.
- **Do** hold touch targets to ≥44px below 600px (delete buttons, row inputs, selects) and keep the 2px ink-low focus-visible outline on everything interactive.
- **Do** announce recomputed totals and verdicts through the debounced polite live region, and give toasts and status lines `role="status"`.
- **Do** use the segmented control for any new enum and a checklist row for any new boolean.
- **Do** stay on the radius ladder (6/8/12/16/20, 9px nested, 999px pill) and keep nested corners concentric.

### Don't:
- **Don't** introduce color. No red for danger, no green for pass, no brand hue anywhere — the danger confirm and the failing verdict already prove the inverse pair is enough.
- **Don't** add a light theme or `prefers-color-scheme` styles; the system is dark-only by design and the inverse alarm depends on it.
- **Don't** use box-shadows. Elevation is lightness; the only sanctioned rings are the `prefers-contrast: more` insets.
- **Don't** spend the inverse pair on anything beyond its four uses (primary action, warn/fail verdict, toast, dialog confirm) — its rarity is its volume.
- **Don't** add switches, radio groups, tab bars, or a second icon family or font. One grammar per job.
- **Don't** put words in ink-faint (#5f5f5f) — it is underline decoration only.
- **Don't** box content in borders; structure is hairlines and fills, with the 1px dashed outline reserved for add-affordances.
- **Don't** let the verdict scroll out of primacy: it leads the Breakdown panel, which itself leads the page below 860px.
