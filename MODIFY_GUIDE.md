# MODIFY_GUIDE — Small changes, zero breakage

Everything visual is driven by variables and plain text. Change the variable, the
whole kit follows. Never edit animation physics to "fix" a colour.

## 1. Change colours (Creative Kit — ui-components.html)

Edit the `:root` block at the top of the `<style>`:

| Variable | Controls | Current |
|---|---|---|
| `--amber` / `--amber2` | Lead accent (buttons, rings, highlights) | #F59E0B / #D97706 |
| `--bg` | Page background (light) | #FFFBEB |
| `--surface` / `--surface2` | Card backgrounds | #FFFFFF / #FFFEF7 |
| `--ink` / `--ink2` | Text / headings | #18120C / #292018 |
| `--muted` | Secondary text | #78716C |
| `--line` | Borders | #E7DDC3 |
| `--cream` / `--cream2` | Warm fills | #F7EFD4 / #EFE6CC |

Dark mode is the `[data-theme="dark"]` block right below it — change values there too,
or the two modes will disagree.
Variant colours (teal #0F766E, crimson #DC2626, violet #7C3AED, sky #0284C7,
emerald #059669) live inside each variant's own CSS class (e.g. `.vb-teal`) — change
them per variant if you want one variant recolored only.

Sakuga Kit (`showcase.html`): crimson is `#FF3355` / deep `#E62E4D`, background
`#0B0B0D`, text `#FAFAF7` — they appear directly in the CSS; search-and-replace the hex.

## 2. Change text, names, numbers

All copy is plain HTML text — search the file for the sentence and edit it.
Data-driven pieces keep their data in one JS array near the component:
feed items `FEED`, deck cards `DECK`, search data `DATA`, fan blades `fanData`,
Sakuga kanji words `words[]`. Edit the array, not the rendering code.

## 3. Change motion speed / feel (carefully)

Creative Kit motion tokens (top of `<style>`):
`--sp-glide` reveals · `--sp-pop` pops · `--sp-snap` snaps · `--sp-soft` hovers;
durations `--dur-fast` .28s · `--dur-med` .5s · `--dur-slow` .95s.
Slow the whole board down by raising the three durations — do not swap the curves
for `ease` or `linear`; that is exactly what makes a kit feel basic.
Sakuga Kit: easings are written inside each component's JS `animate()` calls
(`cubic-bezier(.34,1.4,.44,1)` etc.) and physics constants (damping 0.965, swirl 0.94).

## 4. Take ONE component into another project

1. Find it in `COMPONENTS.md`, open the file at that location.
2. Copy three things: the HTML block, its CSS block (same comment name), its JS block.
3. If it uses bursts, also copy the `#fxLayer` div + `burstAt()` (Creative Kit) —
   several buttons depend on it.
4. If it uses the theme, copy the `:root` + `[data-theme="dark"]` variables it names.

## 5. Never touch (unless you mean it)

- `#fxLayer` must stay `pointer-events:none` and fixed — bursts render there.
- The `data-off` off-screen pause system: removing it makes a 169-component page lag.
- `prefers-reduced-motion` block at the end of the CSS.
- In Sakuga components, the kanji readability setup: bold size, white
  `-webkit-text-stroke`, dark disc behind, ~1.2s hold. Shrinking or blurring it
  breaks the kit's first rule.
