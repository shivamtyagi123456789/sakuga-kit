# FLAGSHIP KIT — 100 Bespoke Scene Pieces (flagship-pieces.html)

The flagship collection: **100 scene-level pieces in 10 genre batches of 10**, all in one
self-contained HTML file — zero dependencies, vanilla canvas + JS. Open
`flagship-pieces.html` in any browser; no build step, no server.

## What makes a piece "flagship"

- **Bespoke, not a variant.** Every piece is its own little world with invented physics —
  no shared templates, no reskins. A piece named Flame burns, Wave moves like water,
  a volcano builds an island grain by grain.
- **One matched kanji moment per piece**, earned by a real event inside the scene
  (totality reached, the 100th spark tapped, the hatch threshold crossed) — shown bold
  (~130px) with a white outline, dark disc behind, romaji + meaning caption, ~1.2s hold.
- **Layered, simultaneous effects + ambient motion that never fully stops**, with
  spring/damping physics — never linear tweens.
- **Sakuga palette**: near-black `#0B0B0D`, crimson `#FF3355` / `#E62E4D`, white —
  element colours (sea blue, aurora green, lava orange) appear only where the scene earns them.
- **Performance**: each batch runs in its own isolated script with its own
  IntersectionObserver — off-screen pieces pause, particle counts are capped
  (~40–130 per stage), and one batch's fault can never stop another batch.

## How the file is organised

- One `<section>` per batch (`batch1` … `batch10`), one isolated `<script>` engine per batch.
- Each piece is an `<article class="piece">` with a `data-canvas` name; find a piece by
  searching the file for its canvas name (e.g. `nighttrain`, `gravity`, `crow`).
- After every batch sits its **Review Panel** (Rate → Correct → Rate): honest first
  scores, the weakness found per piece, the fix applied, and the corrected score.
  The board ends with a **Collection Finale** panel: all batch averages, the
  collection average (83.5), the Top 10 pieces, and the polish report.

## The 10 batches

| Batch | Genre | Corrected avg |
|---|---|---|
| 01 | Night & Festival | 80.6 |
| 02 | Ocean & Water | 82.5 |
| 03 | Sky & Cosmos | 83.4 |
| 04 | Seasons & Forest | 83.2 |
| 05 | City Night & Streets | 83.1 |
| 06 | Music & Rhythm | 84.0 |
| 07 | Creatures & Companions | 84.1 |
| 08 | Machines & Invention | 84.2 |
| 09 | Journeys & Travel | 84.6 |
| 10 | Grand Finale — Elements & Wonder | 85.3 |

**Collection average: 83.5/100.** Highest-rated piece: **Night Train Window (87)**.

Full piece-by-piece index: see `COMPONENTS.md`, section E.

## Using a piece in your own project

1. **Exact same** — copy the piece's `<article>` block plus its batch engine script;
   keep the batch's shared helpers (the engine is written to run its 10 pieces together).
   For a single piece, ask an AI to extract it using `RECREATE_WITH_AI.md`'s method.
2. **Recreate with an AI model** — follow `RECREATE_WITH_AI.md`: one piece at a time,
   strict prompt, never paste the whole file.
3. **Small changes** — colours live in CSS variables / canvas palette constants at the
   top of each engine; text is plain HTML. See `MODIFY_GUIDE.md`.

## Rating honesty note

Scores in the review panels are self-reviews on the owner's strict scale
(40/100 = "good, more upgrades required"). They are kept in the file on purpose:
they show what was weak, what was fixed, and what the next batch's Improvement Lens changed.
