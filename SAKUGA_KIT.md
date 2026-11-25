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
Element Lanterns (festival scene, in chat demos) · Ink Tabs · Hanko Seal ·
Ink Input · Toast.

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

## Also in this repo now
- `ui-components.html` — the Creative UI/UX Kit: 169 components (Waves 1–2 + 30 types × 5 variants).
- `COMPONENTS.md` — index of everything in both kits. `RECREATE_WITH_AI.md` — low-tier
  model process. `MODIFY_GUIDE.md` — colours/text/motion knobs for small changes.
