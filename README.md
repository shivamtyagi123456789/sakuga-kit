# Sakuga Kit — Anime-Impact + Creative UI Components

Two collections in one repo, both single-file, zero dependencies, vanilla HTML/CSS/JS:

1. **Sakuga Kit** (`showcase.html`) — anime-impact components: every component pairs spring/damping physics with a matched Japanese kanji moment.
2. **Creative UI/UX Kit** (`ui-components.html`) — 169 general-use components: Waves 1–2 (19 flagship pieces) + a Variant Lab of 30 types × 5 variants (150), each variant a different design + colour pattern (amber, teal, crimson Sakuga, violet, sky, emerald, rose, mono).

Open either file in any browser — no build step, no server.

## Files

| File | What it is |
|---|---|
| `showcase.html` | Sakuga collection — full working code, 7 components, blocks marked with comments |
| `ui-components.html` | Creative Kit board — full working code, 169 components |
| `SAKUGA_KIT.md` | Sakuga spec + per-component code locations, how each effect works, and its change knobs |
| `COMPONENTS.md` | Index of every component in both kits: type, variant, pattern, code location |
| `RECREATE_WITH_AI.md` | Step-by-step process to recreate any component with a low-tier / free AI model |
| `MODIFY_GUIDE.md` | How to make small changes (colours, text, names) without breaking motion |
| `README.md` | This file |

## Three ways to use a component

1. **Exact same** — copy its code block from the HTML file. No AI needed.
2. **Small modification** — follow `MODIFY_GUIDE.md` (colours are CSS variables; text is plain HTML).
3. **Recreate with an AI model** — follow `RECREATE_WITH_AI.md`: small batches, strict prompts, one component at a time.

## Design rules (both kits)

- Motion is fluid: spring/overshoot easings and damping physics, never linear tweens.
- Many layers fire at once (burst + ring + smear + kanji), and ambient motion never fully stops — but off-screen components pause to save CPU.
- Sakuga kit: near-black `#0B0B0D`, crimson `#FF3355` / `#E62E4D`, white `#FAFAF7`; every component owns ONE matched kanji, shown bold with a white outline, dark disc behind, romaji + meaning caption, ~1.2s clean hold.
- Creative kit: bright amber lead `#F59E0B` / `#D97706`, warm cream `#F7EFD4`, white, warm grey, espresso `#18120C`; elegant serif headings (Playfair Display) + DM Sans; dark mode is the espresso theme.

## License

Free to use, modify and share (MIT spirit). Credit appreciated, not required.

---
*Built by Shivam Tyagi — designed with Muse (Junior Amon).*
