# SAKUGA KIT — Agent Instructions & Spec (v1, 2026-11-24)

Owner: Sir Amon (Shivam Tyagi). Purpose: anime-impact ("sakuga") UI components for
his websites/apps (UniDash, Inqui, Hermes web, portfolio). Any AI agent (Claude,
Antigravity, BuildBot) given this file + `showcase.html` must build in THIS style.

## Files
- `showcase.html` — single-file live demo of every component (open in any browser,
  share as-is). All component code lives inside it; copy a component's CSS+JS block
  (marked with comments like `/* ============ IMPACT BUTTON ============ */`).

## Design tokens
- Background: near-black #0B0B0D · Panel: rgba(250,250,247,.05) on black
- Primary: crimson #FF3355 · Deep: #E62E4D · Dark red: #B01E38 · Soft: #FF5C77 / #FF8FA3
- Text: white #FAFAF7 · Muted: rgba(250,250,247,.55)
- Element colours (lanterns): fire #FF7A29/#FFB347, water #39A8E8/#7CCBFF, wind #A9E8C0
- Headings: elegant serif (Georgia / 'Cormorant Garamond'). Japanese: 'Yuji Syuku',
  'Hiragino Mincho ProN', 'Yu Mincho', serif.

## The 5 rules (non-negotiable)
1. **Matched Japanese word per component** — button 爆発/ドン, toggle 起動 or 液体,
   slider 流れ, tabs タブ, seal 判子, input 入力, pond 波紋, lanterns 火/水/風.
   Kanji reveals must be CLEARLY readable: bold ~130px, white outline
   (-webkit-text-stroke), dark radial disc behind, romaji + meaning caption,
   ~1.2s clean hold before fading. Never let blur/flash wash the kanji out.
2. **Fluid, never linear** — spring/overshoot easings (cubic-bezier(.22,.9,.26,1),
   (.34,1.4,.44,1)), velocity damping ~0.96 in particle physics, swirl/vortex
   forces, squash-and-stretch on press. If it moves like a robot, it's wrong.
3. **Many layers at once** — ambient motion never stops (ink blobs, sine ribbons,
   breathing glow, dust motes, swimming koi). An interaction fires a CHOREOGRAPHED
   combo (flash + burst + rings + shake + letter/kanji), not a single effect.
4. **Handcrafted feel** — scenes over boxes: grain, vignette, light pools on the
   ground, tassels with lagged secondary physics, slight imperfections. It must
   not look like generic AI output.
5. **Invent per component** — do NOT copy-paste the burst everywhere. Each
   component gets its own motion idea (goo melts, pond lives, lanterns swing
   with pendulum physics, slider has a liquid wave edge).

## Components in v1
Impact Button · Liquid Goo Toggle · Living Slider · Pond (ambient koi) · Folding Fan Deck · Zipper Reveal · Shodo Brush Loader ·
Element Lanterns （火/水/風） · Lantern Festival （祭） · Constellation （星） · Origami Map （図） ·
Elastic Pull （弾） · Ink Tabs （タブ） — all 13 live in `showcase.html`.
(Also seen in chat demos: Hanko Seal · Ink Input · Toast.)

## Copy-paste prompt for any AI agent
"Build this component in the Sakuga Kit style (see SAKUGA_KIT.md): near-black +
crimson + white palette, a matched Japanese impact word shown clearly (bold,
white outline, dark disc, romaji caption), fluid spring physics with damping —
never linear easing — multiple animation layers running simultaneously plus an
ambient always-on layer, and a handcrafted, non-generic finish. Invent a motion
idea that fits THIS component; do not reuse a generic particle burst."

---

## Code & Explanation — every component (added in the full-code upgrade)

Earlier this file was spec + text only. Each component below now points at its exact
code block in `showcase.html`, explains how the effect is built, and lists the knobs.
The code itself lives in `showcase.html` — copy the named block (HTML + CSS + JS).

### 1. Impact Button — `/* ============ IMPACT BUTTON ============ */`
Canvas particle system. On click: 46 particles spawn with swirl force (tangential
acceleration, damping 0.965, swirl decay 0.94), two shockwave rings (second delayed
150ms), a white flash, squash-and-stretch on the button (scale 1.2/0.78 → 0.95/1.09 → 1
over 520ms, cubic-bezier(.34,1.4,.44,1)), and a kanji reveal: disc fades in, kanji lands
from scale 1.7 + blur 9px to 0.97, holds ~1.2s with romaji + meaning caption, exits up.
Background runs forever: 3 drifting crimson ink blobs + 3 sine ribbons on the canvas.
Knobs: `words[]` (kanji/word/romaji/meaning cycle), particle count 46, colour array.

### 2. Liquid Goo Toggle — `/* ============ GOO TOGGLE ============ */`
SVG filter `#goof`: feGaussianBlur (stdDeviation 7) + feColorMatrix alpha contrast
(22, -10) makes nearby shapes melt together. Three pieces animate over 620ms: the knob
travels 6px ↔ 92px on cubic-bezier(.3,1.25,.35,1), a bridge blob stretches through the
middle (scale 1.15/0.8 at 45%), and the knob squashes 1.35/0.72 → 0.92/1.1 → 1.
Knobs: travel distance, filter deviation (higher = meltier), blob colours via `.goo.on .blob`.

### 3. Living Slider — `/* ============ LIVING SLIDER ============ */`
Pointer events set the value (0–100); the displayed number eases toward it (×0.22/frame).
The fill's leading edge is an SVG wave path rebuilt each frame — phase speed rises while
dragging, so the liquid sloshes faster the faster you drag. Dragging spawns canvas spark
particles against the velocity and smear-ghost thumbs at velocity > 2.2. 21 ticks light
progressively. On release: kanji moment — 流 NAGARE normally, 満 MAN at 100%, 空 KŪ at 0%.
Knobs: tick count 21, wave phase increments (0.55 drag / 0.16 idle), ghost threshold.

### 4. The Pond — `/* ============ POND ============ */`
Canvas scene, 5 koi. Each koi steers: gentle sine wander, occasional random target
heading, wall bounce; tail wag is a sine on the tail triangle. Tap: two elliptical
ripples (second delayed 110ms, inner ring crimson), 12 droplets with gravity, and any
koi within 110px gets a flee heading + 3.2× speed for ~1.1s, then drifts back.
Knobs: koi count, flee radius 110, ripple growth 1.5/frame.

### 5. Folding Fan Deck — `/* ============ FAN DECK ============ */`
Five blades (`fanData[]`: 炎 Flame #FF7A29, 氷 Ice #7CCBFF, 雷 Thunder #F2DFAC,
風 Wind #A9E8C0, 月 Moon #E9E4F5) share one pivot; opening rotates them to (i−2)×27°
with per-blade transition delay (55ms stagger open, reverse stagger close) on
cubic-bezier(.3,1.35,.35,1). Tapping a blade lifts it −13px, brightens it, and writes
its name into the caption. Knobs: fanData entries, spread angle 27°, stagger.

### 6. The Zipper — `/* ============ ZIPPER ============ */`
Drag the golden pull (pointer capture, vertical). Progress zp (4–96%) drives two
clip-path polygons: each cover half keeps a wedge that narrows toward the pull point
(factor 0.42), revealing the 秘 secret layer beneath. Release fires a small
squash animation on the pull. Knobs: wedge factor 0.42, zp clamp range.

### 7. Shodo Brush Loader — `/* ============ SHODO LOADER ============ */`
The stroke is an SVG path; its length (getTotalLength) drives a dash-offset draw over
2300ms with easeInOut easing. A feTurbulence + feDisplacementMap filter (scale 5)
roughens the stroke so it reads as ink, not vector. A brush-tip circle rides
getPointAtLength and thins mid-stroke; the % counter follows eased progress; at 100%
the 完 stamp slams (scale 2.1 → 0.94 → 1, 360ms). Knobs: duration, path `d`, filter scale.

### 8. Element Lanterns — `/* ============ ELEMENT LANTERNS ============ */`
Three lanterns （火 fire #FF7A29/#FFB347, 水 water #39A8E8/#7CCBFF, 風 wind #A9E8C0) hang from
strings. Each is a true pendulum: velocity += (−0.052·angle + gust), damped ×0.985; the
tassel runs its own softer spring chasing the lantern angle ×1.7, so it lags and overshoots.
Random gusts shove all three. Selecting a lantern swaps the canvas particle system —
embers rising (fire), drips falling into expanding ripples (water), leaves streaming
sideways (wind) — recolours the panel scene, and fires that element's kanji moment.
Knobs: pendulum stiffness 0.052, tassel chase 0.075 / damping 0.92, gust interval.

### 9. Lantern Festival — `/* ============ LANTERN FESTIVAL ============ */`
One canvas paints the whole night: 110 twinkling stars, a glowing cratered moon, six
lanterns swaying on a sagging wire, rooftop silhouettes with lit windows, and a CSS
film-grain overlay jittering on steps(4) above a vignette. Tap anywhere: a sky lantern
releases from the rooftops — flickering flame, sine sway, slow shrink — and drifts up
until it fades; one also auto-releases every ~400 frames. First taps fire 祭 MATSURI
(1.7s cooldown so the kanji never spams). Knobs: star count, wire sag, release rate.

### 10. Constellation — `/* ============ CONSTELLATION ============ */`
A 90-star twinkling field with occasional shooting stars. Tap: the point snaps to the
nearest field star within 26px (or plants a new one), pulses a ring, and the line to the
previous star draws itself at 0.028/frame with a glowing travelling head. 3+ stars close
a faint crimson polygon; **Complete** flashes the lines and fires 星 HOSHI, naming the
constellation （鯉座， 扇座， 弓座… by star count). **Clear** resets the sky.
Knobs: snap radius 26, line draw speed, names list.

### 11. Origami Map — `/* ============ ORIGAMI MAP ============ */`
A 2×2 paper map (street-grid texture, river band, crease shading) folded in quarters.
Stage classes s0→s3 resize the sheet and un-rotate the panels on their real fold edges
(right panel rotateY −178°→0 around its left edge, bottom rotateX, corner panel both),
all on cubic-bezier(.3,1.18,.35,1). At full unfold the route path draws itself
(dash-offset, 1.7s), the two pins pop in with spring scale, a compass fades in spinning,
and 図 ZU fires. Knobs: stage captions, route path `d`, fold durations.

### 12. Elastic Pull — `/* ============ ELASTIC PULL ============ */`
A crimson medallion （弾） on a spring. Dragging chases the pointer with a stiff spring
(×0.2 pull, ×0.7 damping) so it lags and stretches: the disc rotates to the pull angle,
scales up to +50% along it and thins −24% across it, then counter-rotates so the kanji
stays upright. Release switches to a soft spring (×0.05, damping 0.90) — a long wobbling
overshoot home — plus two ripple rings and 16 droplets; past 105px of stretch it also
fires 弾 DAN. Idle, it breathes a faint ring every 2.6s. Knobs: spring constants,
stretch threshold 105, medallion size.

### 13. Ink Tabs — `/* ============ INK TABS ============ */`
Four tabs （家 Home, 探 Explore, 庫 Library, 定 Settings). Selecting one rebuilds an SVG
brush path from the old tab's centre to the new one — a fat soft under-stroke (blurred,
32% crimson) plus the main stroke through a feTurbulence displacement filter (#inktab,
scale 4) so the edge bleeds like ink. Both draw on over 620ms while a brush-tip dot
rides getPointAtLength; landing fires 6 splatter droplets and the タブ TABU kanji moment.
The panel below swaps content with a blur-fade rise. Knobs: tab data `TD[]`, draw
duration, displacement scale.

## Also in this repo now
- `ui-components.html` — the Creative UI/UX Kit: 169 components (Waves 1–2 + 30 types × 5 variants).
- `COMPONENTS.md` — index of everything in both kits. `RECREATE_WITH_AI.md` — low-tier
  model process. `MODIFY_GUIDE.md` — colours/text/motion knobs for small changes.

## The 150 — everyday components in Sakuga style (sakuga-components.html)

Added 2026-11-25. `sakuga-components.html` holds **150 general website components** —
the everyday parts of real websites (search bars, buttons, forms, login, cards, tables,
toasts, sliders, quizzes, settings, chat…) — built to the same 5 rules above, at the
quality bar of the approved "Sakuga Search" sample. Sakuga Kit total: **13 + 150 = 163**.

- 15 categories × 10: Search · Buttons & CTAs · Navigation & Menus · Inputs & Forms ·
  Login & Signup · Cards & Lists · Tables & Data Lists · Toasts & Notifications ·
  Sliders & Progress · Quiz, Polls & Surveys · Loading & Empty States ·
  Timelines & Activity · Settings & Preferences · Heroes, Banners & Footers · Chat & Social.
- Every component is **fully functional** with real content and all states
  (idle/focus/typing/loading/empty/success/error) — not a static mockup.
- Every component has exactly **one matched kanji moment, earned** by completing its
  real flow (110px glyph, white outline, dark disc, romaji + meaning, ~1.35s hold).
- Each batch of 10 closes with a **Rate → Correct → Rate review panel** inside the file;
  corrected batch averages rise 84.8 → 89.8 across the board; **collection average 88.1**.
- Structure: one section + one isolated script per batch (off-screen pause via
  IntersectionObserver, per-piece try/catch isolation, user input escaped via `esc()`).
- A shared in-page demo account system links the Login batch (signup → login → reset).
- Full per-piece index: `COMPONENTS.md`, section F. To lift one component, copy its
  card block + its batch script, or recreate it via `RECREATE_WITH_AI.md`.
