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
