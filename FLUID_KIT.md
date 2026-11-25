# FLUID KIT — Spec, Code Locations & How It Works (v1, 2026-11-25)

Owner: Sir Amon (Shivam Tyagi). The Fluid Lab: 120 general-use UI components
(30 types × 4 variants) built around one signature idea — **liquid behaviour**.
Inspired by the Sakuga Kit's black & white goo toggle: press it and it *flows*
like liquid. This kit takes that one idea across every common component.

File: **`fluid-components.html`** — single file, zero dependencies, vanilla
HTML/CSS/JS. Open in any browser.

## The board rule (non-negotiable)

- Every type has **exactly ONE fluid variant**: the component melts, pours,
  drips, waves, splashes or merges like real liquid (gooey SVG filters, canvas
  waves, spring + damping physics — never linear tweens).
- The other **3 variants are different motion inventions** (burst, smear,
  scramble-decode, stamp, spotlight, pulse, peel, flip…). A trick is never
  repeated across types — the funnel pass rejected and replaced 8 repeats.
- Fluid variants re-colour live through **6 liquid themes**:
  **Ink** (black & white — the original), **Honey Amber**, **Ocean Blue**,
  **Grape Jelly**, **Mint Syrup**, **Rose Syrup**.

## How the code is organised

- All components are data-driven: the inline `<script>` holds a **`TYPES`
  array** — one object per type, each with its 4 variant definitions
  (name, markup, style hooks). Labs and the Self-Review table are rendered
  from this array, so to copy ONE component: find its type object in `TYPES`,
  take the variant's markup + the CSS block with the matching class names +
  any handler referencing its `data-*` hook.
- Batch hooks: Batch 1 uses `data-act`, Batch 2 `data-z`, Batch 3 `data-q`,
  funnel-pass additions `data-scramble / data-pulse / data-lift /
  data-sealsucc / data-planspot / data-stamp`.
- Init safety: every batch's init sweep is wrapped in per-stage try/catch —
  one lab failing can never kill another batch's click handlers. (This was a
  real bug, fixed 2026-11-25: Batch 2/3 sections stopped opening because one
  init error aborted the shared script.)
- Off-screen pause: looping animations pause when their lab is off-screen;
  fade-ins are never paused.

## The 30 types

Batch 1 — Buttons · Toggles · Tabs · Sliders · Progress Rings · Loaders ·
Like · Menus · Cards · Checkboxes.
Batch 2 — Inputs & Forms · Search Bars · Dropdowns & Selects · Modals &
Bottom Sheets · Accordions · Carousels · Pricing · Stats & Charts ·
Avatars & Badges · Toasts & Alerts.
Batch 3 — Hero Sections · Footers & CTAs · Timelines & Steppers · Tables &
Kanban · Media Players · Maps & Delivery · E-commerce · Social &
Engagement · Calendars & Booking · Empty / Error / Success.

Signature fluid variants: drip button, pour toggle, gooey tab bar, sloshing
slider, wave ring, metaball loader, splash like, blob menu, wave card,
liquid check, liquid-rise input, blob-open search, pour-down dropdown,
splash modal, flow-open accordion, liquid columns chart, goo avatar stack,
drip toast, rising-tide hero, wave footer, pour stepper, splash kanban,
liquid-progress player, flowing delivery route, filling cart, pour poll,
ink-bleed calendar, liquid-check success.

Full index with variant names: see `COMPONENTS.md`, section D.
Self-review scores (DesignBot funnel, strict scale): board average **72.3/100** —
the per-type table lives at the bottom of `fluid-components.html`.

## Recreate with a low-tier / free AI model

Same process as the rest of this repo — see `RECREATE_WITH_AI.md`, with one
Fluid-specific rule: work **one TYPE at a time** (4 variants), paste that
type's full `TYPES` object + its CSS block, and add this line to the master
prompt: *"Exactly one variant must behave like liquid (goo/wave/pour/drip
with spring physics); the other three must each use a different motion idea.
Do not simplify the liquid into a plain fade or slide."*

## Modify without breaking it

See `MODIFY_GUIDE.md` for the general rules. Fluid-specific knobs:
- Liquid colours: the 6 theme definitions (search the script for the theme
  names — Ink/Honey/Ocean/Grape/Mint/Rose).
- Goo strength: the SVG goo filter's blur/contrast values in the shared
  `<svg>` filter block — higher contrast = thicker liquid.
- Wave speed/height: the canvas wave loops in the slider/ring/player blocks.
- Never swap spring easings for linear ones; the flow *is* the easing.
