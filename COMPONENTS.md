# COMPONENTS — Full Index (both kits)

How to use this index: find the component, note its file + location, copy that block.
Locations in `ui-components.html` are the section comments (e.g. `<!-- VL-7 SLIDERS -->`)
and the matching CSS/JS blocks with the same name. Locations in `showcase.html` are
the script comments (e.g. `/* ============ IMPACT BUTTON ============ */`).

## A. Sakuga Kit — showcase.html (7)

| # | Component | Kanji | Signature effect | Location |
|---|---|---|---|---|
| 1 | Impact Button | 爆 BAKU | Vortex particle burst, rings, squash-stretch, kanji reveal | IMPACT BUTTON |
| 2 | Liquid Goo Toggle | 液 EKITAI | SVG goo filter melt, spring knob + bridge | GOO TOGGLE |
| 3 | Living Slider | 流 NAGARE | Liquid wave edge, ghost trail, ticks, release kanji | LIVING SLIDER |
| 4 | The Pond | 池 / 波紋 HAMON | 5 koi, tap ripples + droplets, flee steering | POND |
| 5 | Folding Fan Deck | 扇 | 5 element blades fan from one pivot | FAN DECK |
| 6 | The Zipper | 秘 HIMITSU | Drag pull, polygon-clip wedge reveal | ZIPPER |
| 7 | Shodo Brush Loader | 書 / 完 | Self-drawing ink stroke, turbulence edge, stamp slam | SHODO LOADER |

Full per-component explanation + knobs: see `SAKUGA_KIT.md`.

## B. Creative Kit — ui-components.html, Waves 1–2 (19)

Wave 1: Buttons + Gradient Mesh · Liquid Progress Ring · Search + Filter Chips ·
Deadline Countdown · Live Activity Stream · Swipe Card Deck · Living Slider + Tabs ·
Muse Suggests + Add Card · Colour System.
Wave 2: Living Calendar · Exam Countdown Hero (fuse + DONE seal) · Ink Slider ·
Hanko Seal Button · Orbit Quick-Actions · Notification Island · Subject Vault ·
Bunk Calculator (odometer + spring needle) · Vinyl Mini-Player · Achievement Burst.

## C. Creative Kit — Variant Lab, 30 types × 5 variants (150)

Variants are lettered A–E on each card's switcher. Patterns rotate through:
Amber Burst, Teal, Crimson Sakuga, Violet, Sky, Emerald, Rose, Mono (per type below).

| Lab | Type | Variant patterns (A–E) |
|---|---|---|
| 01 | Buttons | Amber Burst · Teal Ripple · Crimson Slash · Violet Glow · Mono Fill |
| 02 | Toggles & Switches | Sakuga Gold · Teal Goo · Crimson Block · Violet Orb · Mono Flip |
| 03 | Cards | Pricing Amber · Profile Teal · Product Crimson · Usage Violet · Travel Sky |
| 04 | Navigation | Pill Amber · Sidebar Teal · Bottom Mono · Underline Crimson · Dock Violet |
| 05 | Search Bars | Pill Amber · Underline Teal · Command Dark · Voice Violet · Expanding Mono |
| 06 | Chips, Tags & Filters | Amber · Teal · Violet check · Mono · Removable crimson tags |
| 07 | Sliders & Range | Amber · Teal segments · Violet glow · Price range · Brightness |
| 08 | Progress Rings & Bars | Amber ring · Teal bar · Violet donut · Download · Battery |
| 09 | Toasts & Alerts | Success · Info · Error shake-retry · Stack · Banner |
| 10 | Tabs & Segmented | Pill · Underline · Segmented · Badge tabs · Vertical |
| 11 | Inputs & Forms | Floating label · OTP · Slug builder · Password meter · Textarea counter |
| 12 | Dropdowns & Selects | Single · Multi-select total · Colour picker · Searchable · Country |
| 13 | Modals & Drawers | Confirm · Delete + Undo · Sheet · Drawer · Form modal |
| 14 | Accordions & FAQs | Standard · Gradient accent · Card · Plus/minus · Nested |
| 15 | Carousels & Galleries | Auto-play · Testimonial fade · Logo loop · Snap row · Before/After drag |
| 16 | Pricing & Plans | Monthly/Yearly flip · Paywall blur · Donation tiers · Compare table · Toggle |
| 17 | Stats & Charts | KPI count-up · Draw-on line · Gauges · Sparklines · Bars |
| 18 | Lists & Feeds | Todo draw-on ticks · Playlist player · File saves · Chat auto-reply · Activity |
| 19 | Avatars & Badges | Stack fan · Presence list · Bell ring · XP level-up · Verified |
| 20 | Loaders & Skeletons | Orbit ring + % · Dots halo · Skeleton shimmer · Bar · Spinner set |
| 21 | Hero Sections | Mesh · Split card-swap · App · Video play pulse · Minimal |
| 22 | Footers & CTAs | CTA sheen banner · Footer links · QR scanline · Sticky bar · Signup burst |
| 23 | Timelines & Steppers | Vertical · Onboarding cycler · Activity prepend · Steps · Order |
| 24 | Tables & Data Grids | Sortable · Detail rows · Compare · Kanban fly · Leaderboard |
| 25 | Media Players | Audio timed · Video chapters · Voice note · Story edge-tap · Mini |
| 26 | Maps & Location | Pin bounce · Route flow · Rider tracker · Weather sun · Journey steps |
| 27 | E-commerce | Product tiles · Bag counter · Cart re-price · Order tracker · Wishlist |
| 28 | Social & Engagement | Poll animated · Like burst · Share sheet · Follow · Reactions |
| 29 | Calendars & Booking | Month range pricing · Slots · Event RSVP · Reminders · Date card |
| 30 | Empty / Error / Success | Empty inbox · 404 glitch · Success draw-on check · Error retry · Offline queue |

## Shared systems (ui-components.html)

- Motion tokens: `--sp-glide`, `--sp-pop`, `--sp-snap`, `--sp-soft` (see MODIFY_GUIDE).
- Off-screen pause: IntersectionObserver tags cards `data-off`; heavy loops check `__isVis()`.
- FX layer: `#fxLayer` (pointer-events:none) hosts all burst particles.
- Theme: `data-theme="dark"` on `<html>` switches to the espresso palette.
