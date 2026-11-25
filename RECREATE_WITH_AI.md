# RECREATE_WITH_AI — Build these components with a low-tier / free model

The golden rule: **a small model cannot hold 169 components at once — and it does not
need to.** The finished code already exists in this repo. Use the model only when you
want a component rebuilt in a new project, and feed it ONE component at a time.

## Route 0 — No model at all (fastest, exact)

Open `ui-components.html` or `showcase.html`, find the component's block
(see `COMPONENTS.md` for locations), copy its HTML + CSS + JS into your page. Done.
Same-to-same, zero risk of the model "improving" it into something basic.

## Route 1 — Model rebuild, one component per prompt

Repeat these steps per component (a batch = up to 5 prompts in one sitting, one at a time):

1. Open the source file and copy the component's full block (markup + its CSS + its JS).
2. Paste the MASTER PROMPT below, then paste the copied block after it.
3. The model returns the component placed in your target page. Check it against the
   checklist at the bottom. If it simplified anything, reply with the FIX prompt.
4. Only then move to the next component. Never paste two components in one prompt.

### MASTER PROMPT — copy exactly

You are recreating ONE UI component from my design kit. Rules, no exceptions:
1. Do NOT redesign anything. Keep the same layout, colours, text and animation idea.
2. Keep the motion fluid: spring/overshoot easings only — cubic-bezier(.22,1,.36,1),
   cubic-bezier(.34,1.56,.44,1), cubic-bezier(.22,1.4,.36,1). Never linear tweens.
3. Keep ALL layers of the effect (if the original fires a burst + ring + smear, yours
   fires all three). Do not replace an effect with a simpler one.
4. Vanilla HTML/CSS/JS only, single file, no libraries, no build step.
5. Animate transform and opacity; pause animations when the component is off-screen
   if the original does.
6. Output ONLY the code, no explanation.
Here is the exact component code to recreate in my page:

### FIX prompt — if the output came back basic

Your version is simpler than the original. Compare it with the code I pasted:
restore every missing layer, the exact easing curves, and the exact colours.
Change nothing else. Output only the corrected code.

## Route 2 — Sakuga-style NEW component (no original exists)

Use the prompt in `SAKUGA_KIT.md` ("Copy-paste prompt for any AI agent"), and give the
model ONE finished Sakuga component from `showcase.html` as a reference example in the
same message. One component per prompt, same checklist.

## Checklist (tick before accepting any output)

- [ ] Same colours and layout as the original (compare side by side)
- [ ] Motion is springy, never straight/linear
- [ ] Every effect layer from the original is present
- [ ] It actually works: click / drag / type — the state changes for real
- [ ] No library or framework was added
- [ ] Works at phone width without sideways scroll

## Batch plan (if recreating the whole Creative Kit)

30 types. Order: Buttons, Toggles, Cards, Navigation, Search, Chips, Sliders,
Progress, Toasts, Tabs (Batch 1) → Inputs, Dropdowns, Modals, Accordions, Carousels,
Pricing, Stats, Lists, Avatars, Loaders (Batch 2) → Heroes, Footers, Timelines,
Tables, Media, Maps, E-commerce, Social, Calendars, States (Batch 3).
Per type: 5 prompts (one per variant). Per prompt: MASTER PROMPT + that variant's block.
