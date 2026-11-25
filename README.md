# Sakuga Kit — Anime-Impact + Creative UI Components

Five collections in one repo — **752 components total**, all single-file, zero dependencies, vanilla HTML/CSS/JS:

1. **Sakuga Kit** (`showcase.html` + `sakuga-components.html`) — 163 anime-impact components: the original 13 scene-grade pieces in `showcase.html`, plus **150 everyday website components** in `sakuga-components.html` (search, buttons, forms, login, cards, tables, toasts, sliders, quizzes, settings, chat — 15 categories × 10, all fully functional with real states, each earning one matched kanji moment; built batch-by-batch with Rate → Correct → Rate review panels, collection average 88.1/100).
2. **Creative UI/UX Kit** (`ui-components.html`) — 169 general-use components: Waves 1–2 (19 flagship pieces) + a Variant Lab of 30 types × 5 variants (150), each variant a different design + colour pattern (amber, teal, crimson Sakuga, violet, sky, emerald, rose, mono).
3. **Fluid Kit** (`fluid-components.html`) — 120 components (30 types × 4 variants) built on liquid behaviour: every type has exactly one fluid/goo variant (pours, drips, waves, merges — re-colourable through 6 liquid themes: Ink, Honey Amber, Ocean Blue, Grape Jelly, Mint Syrup, Rose Syrup) plus three different motion inventions. Self-reviewed average 72.3/100.
4. **Flagship Kit** (`flagship-pieces.html`) — 100 bespoke scene-level pieces in 10 genre batches of 10 (Night & Festival, Ocean & Water, Sky & Cosmos, Seasons & Forest, City Night, Music & Rhythm, Creatures, Machines, Journeys, Grand Finale). Each piece invents its own physics and earns one matched kanji moment; every batch was built with a Rate → Correct → Rate review loop (panels included in the file). Collection average 83.5/100; top piece: Night Train Window (87).
5. **Sakuga Live 200** (`live-components.html`) — 200 live components in 20 categories × 10 (Buttons, Toggles & Switches, Sliders & Steppers, Checkboxes & Radios, Text Inputs, Loaders & Progress, Reactions, Toasts & Alerts, Cards, Tabs & Accordions, Menus & Nav, Badges & Avatars, Media & Players, Counters & Stats, Modals & Popovers, Drag & Sort, Scroll & Reveal, Text Effects, Nature Scenes, Celebration & Rewards). Every piece is live — interactive and animated in the Sakuga language of springs, layered simultaneous effects and matched kanji moments.

Open any file in any browser — no build step, no server.

## Files

| File | What it is |
|---|---|
| `showcase.html` | Sakuga collection — full working code, 13 components, blocks marked with comments |
| `sakuga-components.html` | Sakuga everyday components — 150 working website components in 15 categories, with per-batch review panels |
| `ui-components.html` | Creative Kit board — full working code, 169 components |
| `fluid-components.html` | Fluid Kit board — full working code, 120 components (30 types × 4 variants) |
| `flagship-pieces.html` | Flagship Kit board — 100 bespoke scene pieces in 10 genre batches, with per-batch review panels |
| `live-components.html` | Sakuga Live 200 board — 200 live components in 20 categories × 10 |
| `SAKUGA_KIT.md` | Sakuga spec + per-component code locations, how each effect works, and its change knobs |
| `FLUID_KIT.md` | Fluid spec + code organisation, the board rule, liquid themes, and its change knobs |
| `FLAGSHIP_KIT.md` | Flagship spec + file organisation, the 10 batches, ratings, and how to lift a piece |
| `COMPONENTS.md` | Index of every component in all five kits: type, variant, pattern, code location |
| `RECREATE_WITH_AI.md` | Step-by-step process to recreate any component with a low-tier / free AI model |
| `MODIFY_GUIDE.md` | How to make small changes (colours, text, names) without breaking motion |
| `README.md` | This file |

## Three ways to use a component

1. **Exact same** — copy its code block from the HTML file. No AI needed.
2. **Small modification** — follow `MODIFY_GUIDE.md` (colours are CSS variables; text is plain HTML).
3. **Recreate with an AI model** — follow `RECREATE_WITH_AI.md`: small batches, strict prompts, one component at a time.

## Design rules (all kits)

- Motion is fluid: spring/overshoot easings and damping physics, never linear tweens.
- Many layers fire at once (burst + ring + smear + kanji), and ambient motion never fully stops — but off-screen components pause to save CPU.
- Sakuga kit: near-black `#0B0B0D`, crimson `#FF3355` / `#E62E4D`, white `#FAFAF7`; every component owns ONE matched kanji, shown bold with a white outline, dark disc behind, romaji + meaning caption, ~1.2s clean hold.
- Creative kit: bright amber lead `#F59E0B` / `#D97706`, warm cream `#F7EFD4`, white, warm grey, espresso `#18120C`; elegant serif headings (Playfair Display) + DM Sans; dark mode is the espresso theme.

## License

Free to use, modify and share (MIT spirit). Credit appreciated, not required.

---
*Built by Shivam Tyagi — designed with Muse (Junior Amon).*
