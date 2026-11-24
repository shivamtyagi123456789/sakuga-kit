# Sakuga Kit — Anime-Impact UI Components

Handcrafted, anime-style animated UI components inspired by **Sakuga VFX** (the
animation technique behind impact frames in anime). Every component pairs a
physical, spring-driven motion system with a matched Japanese kanji moment —
built to feel *developer-made*, not generated.

Single-file, **zero dependencies**, vanilla HTML/CSS/JS. Open it in any
browser and everything runs.

## Live demo

Open **`showcase.html`** in a browser — no build step, no server needed.

## What's inside

| # | Component | Signature effect |
|---|-----------|------------------|
| 1 | **Impact Button** | Sakuga burst — smears, speed lines, splash, kanji pop （爆 BAKU) |
| 2 | **Liquid Goo Toggle** | SVG goo filter — two blobs stretch, snap and merge |
| 3 | **Living Slider** | Liquid wave fill that sloshes; release kanji 流 / 満 / 空 |
| 4 | **The Pond** | Five koi drifting in a dark pond, ripples on tap |
| 5 | **Folding Fan Deck** | Cards fan open like a sensu, spring physics |
| 6 | **Zipper** | Drag the pull — teeth part with a metallic run |
| 7 | **Shodo Brush Loader** | A brush stroke draws itself, ink texture and all |

## Design system

- **Palette:** near-black `#0A0A0C`, crimson `#FF3355` / `#E62E4D`, white.
  (This kit deliberately does *not* use the author's usual amber — crimson is
  the Sakuga colour.)
- **Kanji rule:** every component owns ONE matched kanji, shown bold (~138px)
  with a white outline, a dark radial disc behind it, a romaji + meaning
  caption, and a clean ~1.2s hold. The word must *mean* what the component
  does.
- **Motion rule:** fluid spring/damping physics, never linear tweens. Many
  layers fire simultaneously (burst + smear + lines + splash), and ambient
  motion never fully stops.
- **Invention rule:** each component gets its own effect system invented from
  its meaning — no copy-paste bursts from one component to the next.

## Use it in your project

1. Open `showcase.html`, find the component you like.
2. Copy its block (each section is self-contained: markup + styles + script).
3. Paste into your page and restyle the palette tokens to your brand.

## Build your own with an AI agent

`SAKUGA_KIT.md` contains the full spec plus a copy-paste prompt. Hand both
files to your coding agent (ChatGPT, Claude, Antigravity, Cursor…) with the
prompt from that file, and it can generate new components in the same system —
a toggle, a loader, a slider, anything — at the same standard.

## License

Free to use, modify and share (MIT spirit). Credit appreciated, not required.

---

*Built by Shivam Tyagi — designed with Muse (Junior Amon). Part of a larger
quest: interfaces that feel alive.*
