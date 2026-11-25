# COMPONENTS — Full Index (all four kits)

How to use this index: find the component, note its file + location, copy that block.
Locations in `ui-components.html` are the section comments (e.g. `<!-- VL-7 SLIDERS -->`)
and the matching CSS/JS blocks with the same name. Locations in `showcase.html` are
the script comments (e.g. `/* ============ IMPACT BUTTON ============ */`).

## A. Sakuga Kit — showcase.html (13)

| # | Component | Kanji | Signature effect | Location |
|---|---|---|---|---|
| 1 | Impact Button | 爆 BAKU | Vortex particle burst, rings, squash-stretch, kanji reveal | IMPACT BUTTON |
| 2 | Liquid Goo Toggle | 液 EKITAI | SVG goo filter melt, spring knob + bridge | GOO TOGGLE |
| 3 | Living Slider | 流 NAGARE | Liquid wave edge, ghost trail, ticks, release kanji | LIVING SLIDER |
| 4 | The Pond | 池 / 波紋 HAMON | 5 koi, tap ripples + droplets, flee steering | POND |
| 5 | Folding Fan Deck | 扇 | 5 element blades fan from one pivot | FAN DECK |
| 6 | The Zipper | 秘 HIMITSU | Drag pull, polygon-clip wedge reveal | ZIPPER |
| 7 | Shodo Brush Loader | 書 / 完 | Self-drawing ink stroke, turbulence edge, stamp slam | SHODO LOADER |
| 8 | Element Lanterns | 火 HI · 水 SUI · 風 FŪ | Pendulum-swing lanterns, lagged tassel physics, element particle scenes (embers/drips/leaves), kanji per element | ELEMENT LANTERNS |
| 9 | Lantern Festival | 祭 MATSURI | Full night scene — moon, twinkling stars, rooftop silhouettes, wire lanterns, film grain; tap releases a sky lantern | LANTERN FESTIVAL |
| 10 | Constellation | 星 HOSHI | Tap-to-place stars snapped to the field, glow lines draw on between nodes, completion kanji + constellation name | CONSTELLATION |
| 11 | Origami Map | 図 ZU | Paper map unfolds in stages (crease shadows, street grid, river), route draws itself, pins pop with springs | ORIGAMI MAP |
| 12 | Elastic Pull | 弾 DAN | Rubber-band drag — stretch + thinning along the pull, spring snap-back with wobble, ripples + droplets, kanji past the limit | ELASTIC PULL |
| 13 | Ink Tabs | タブ TABU | Brush stroke sweeps to the selected tab (turbulence ink edges + soft under-stroke), splatter, panel ink-fade | INK TABS |

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

## D. Fluid Kit — fluid-components.html, 30 types × 4 variants (120)

Board rule: variant 1 of every type is the FLUID one (goo/wave/pour/drip,
re-colours through 6 liquid themes: Ink · Honey Amber · Ocean Blue · Grape
Jelly · Mint Syrup · Rose Syrup); variants 2–4 are different motion
inventions each. Code location: the type's object in the `TYPES` array in
the inline script + the CSS block with matching class names. Full spec:
see `FLUID_KIT.md`.

| # | Type | Fluid variant | Other motion inventions (examples) |
|---|---|---|---|
| 01 | Buttons | Drip Button | Sakuga Burst · Magnetic Snap · Coin Flip |
| 02 | Toggles | Pour Toggle | Typewriter · Smear Trail · Rolling Pill |
| 03 | Tabs | Gooey Tab Bar | Odometer · Split-Flap · Rolling Indicator |
| 04 | Sliders | Sloshing Slider | Ticks Burst · Elastic Snap · Draw-On |
| 05 | Progress Rings | Wave Ring | Confetti Complete · Counter Spin · Segment Fill |
| 06 | Loaders | Metaball Loader | Orbit Satellite (upgraded) · Morph · Dots Halo |
| 07 | Like / Reactions | Splash Like | Heartbeat · Burst Ring · Float-Up |
| 08 | Menus | Blob Menu | Unfold Peel (upgraded) · Fan Arc · Cascade |
| 09 | Cards | Wave Card | 3D Flip · Drag-Peel · Tilt Shine |
| 10 | Checkboxes | Liquid Check | Draw-On Tick · Stamp · Pop Fill |
| 11 | Inputs & Forms | Liquid-Rise Field | Pen Underline · Slot OTP · Elastic Strength |
| 12 | Search Bars | Blob-Open Search | Cascade Suggestions · Shutter · Waveform Voice |
| 13 | Dropdowns & Selects | Pour-Down Menu | Domino Fall · Slot Roll · Origami Fold |
| 14 | Modals & Sheets | Splash-In Modal | Shutter Sheet · Origami Invite · Elastic Drag Sheet |
| 15 | Accordions | Flow-Open | Highlighter Lines · Side-Slide Rows · Elastic Snap |
| 16 | Carousels | Goo Dots | Page Turn · Vertical Slot Roll · Ken Burns Drift |
| 17 | Pricing | Liquid Tier Level | Shutter Swap · Spotlight Plans · Heartbeat Badge |
| 18 | Stats & Charts | Liquid Columns | Draw-On Line · Cascade KPIs · Live ECG |
| 19 | Avatars & Badges | Goo Stack | Fan-Out · Slot XP Level-Up · Heartbeat Status |
| 20 | Toasts & Alerts | Drip Toast | Cascade Stack · Shutter Alert · Elastic Timer |
| 21 | Hero Sections | Rising-Tide Hero | Scramble Decode · Glitch · Mesh Pan |
| 22 | Footers & CTAs | Wave Footer | Sheen CTA (upgraded) · Twinkle Stars · Sticky Rise |
| 23 | Timelines & Steppers | Pour Stepper | Pulse Runner · Lift Rail Steps · Slide Cascade |
| 24 | Tables & Kanban | Splash Kanban | Arc Flight (upgraded) · Sort Stagger · Expand Rows |
| 25 | Media Players | Liquid-Progress Player | Vinyl Spin + Tonearm · Chapter Skip · Waveform |
| 26 | Maps & Delivery | Flowing Route | Rider Dot (upgraded) · Pin Bounce · Radar Locate |
| 27 | E-commerce | Filling Cart | Wishlist Burst · Price Flip · Order Steps |
| 28 | Social & Engagement | Pour Poll | Star-Burst Rating · Reaction Floats · Share Sheet |
| 29 | Calendars & Booking | Ink-Bleed Calendar | Stamp Book · Week Slide · Slot Cascade |
| 30 | Empty / Error / Success | Liquid-Check Success | Seal Pop Steps · Glitch 404 · Shake-Retry |

## E. Flagship Kit — flagship-pieces.html (100)

100 bespoke scene-level pieces in 10 genre batches. Each piece is an
`<article class="piece">` in its batch section; its engine lives in that batch's
isolated script — find it by the `data-canvas` name. Every piece has one matched
kanji moment earned by an in-scene event. Averages are the corrected scores from
each batch's own Rate → Correct → Rate review panel (in the file, after each batch).

**Batch 01 — Night & Festival (avg 80.6):** Fireworks Crackle Sky · Rain Window ·
Campfire · Neon Street Sign · Paper Lantern Release · Shooting-Star Wish ·
Thunderstorm · Festival Drum · Fireflies in a Jar · Moon Phases Dial

**Batch 02 — Ocean & Water (avg 82.5):** Tidal Wave · Waterfall · Ice Cracking ·
Jellyfish Drift · Deep Sea Anglerfish · Bubble Column · Ferry Wake ·
Monsoon Puddle · Glacier Calving · Hot Spring Onsen

**Batch 03 — Sky & Cosmos (avg 83.4):** Solar Eclipse · Aurora Veil · Comet Pass ·
Rocket Launch · Satellite Orbit · Meteor Shower Peak · Nebula Forge ·
Sunrise Summit · Kite Festival Sky · Gravity Well

**Batch 04 — Seasons & Forest (avg 83.2):** Celebi Forest · Cherry Blossom Storm ·
Autumn Leaf Whirlwind · First Snowfall · Monsoon Jungle · Bamboo Grove Wind ·
Desert Dunes · Volcano · Misty Valley Dawn · Seed to Tree

**Batch 05 — City Night & Streets (avg 83.1):** Rush Hour Traffic · Metro Train Pass ·
Rooftop City · Rainy Alley Steam · Traffic Signal Junction · Skyscraper Windows ·
Night Market · Highway Interchange · Clock Tower Midnight · Street Performer Circle

**Batch 06 — Music & Rhythm (avg 84.0):** Vinyl Groove · Piano Waterfall ·
Drum Kit Storm · Guitar String Pluck · Equalizer City · Metronome Pendulum ·
Tape Reel Machine · Step Sequencer Garden · Saxophone Smoke · DJ Deck Battle

**Batch 07 — Creatures & Companions (avg 84.1):** Sleeping Cat · Goldfish Bowl Orbit ·
Spider Weaver · Butterfly Garden Chase · Owl Watch · Ant Colony · Chameleon Catch ·
Penguin Waddle · Dragon Hatchling · Crow Messenger

**Batch 08 — Machines & Invention (avg 84.2):** Gear Train · Pendulum Clock Escapement ·
Steam Engine Piston · Marble Run Machine · Conveyor Factory · Hydraulic Press ·
Magnetic Crane · Perpetual Chain Reaction · Jacquard Loom · Lighthouse Mechanism

**Batch 09 — Journeys & Travel (avg 84.6):** Hot Air Balloon Drift · Mountain Cable Car ·
Desert Caravan · River Raft Rapids · Night Train Window · Paper Plane Voyage ·
Submarine Descent · Rickshaw Alley Run · Sailboat Regatta · Space Elevator

**Batch 10 — Grand Finale: Elements & Wonder (avg 85.3):** Storm Sea Lighthouse ·
Volcano Ocean Birth · Aurora Glacier Night · Festival of a Thousand Sparks ·
Dragon Storm Rider · Clockwork Garden · Moonlit Tide Pools · Grand Waterfall Shrine ·
Star Whale Migration · One Hundred Sparks Finale

Collection average **83.5/100** · Top piece: **Night Train Window (87)**.
Full spec + how the file is organised: see `FLAGSHIP_KIT.md`.

## F. Sakuga Components — sakuga-components.html (150)

150 everyday website components in Sakuga style (near-black + crimson + earned kanji),
15 categories × 10, each fully functional with real content and all states. Every batch
closes with a Rate → Correct → Rate review panel inside the file itself — the panels
carry the per-piece details, weaknesses and fixes. Corrected batch averages:

| Batch | Category | Pieces | Avg |
|---|---|---|---|
| 01 | Search Bars | Library · Command Palette · Flight · Voice · People · Products · Location · FAQ · Code · Trending | 84.8 |
| 02 | Buttons & CTAs | Buy Now · Download · Follow · Like & Save · Hold-to-Delete · Submit · Copy Text · Play/Pause · Get OTP · Upgrade Pro | 86.5 |
| 03 | Navigation & Menus | Top Nav · Sidebar · Mobile Dock · Breadcrumbs · Mega Menu · Tabs · Pagination · Hamburger Overlay · Stepper · Floating Pill | 86.7 |
| 04 | Inputs & Forms | Floating Label · Password Strength · Email Suggest · Phone +91 · OTP Row · Textarea Counter · Date & Time · Branch Select · Multi-Step Form · File Drop | 87.1 |
| 05 | Login & Signup | Classic Login · Signup · Social Login · Forgot Password · OTP Login · Username Check · Remember Me · 2FA Gate · Magic Link · Guest Upgrade | 87.4 |
| 06 | Cards & Lists | Product · Profile · Music Tracks · Task List · Pricing · Article · Weather · Notifications · Stats · Event RSVP | 87.6 |
| 07 | Tables & Data Lists | Marks · Leaderboard · Inventory · Comparison · Timetable · Expenses · Standings · Price List · Attendance · Orders | 87.9 |
| 08 | Toasts & Notifications | Success Toast · Error Retry · Stack Manager · Island · Bell Panel · Undo Toast · Uploads · Banners · Snackbar · Live Order | 88.7 |
| 09 | Sliders & Progress | Volume · Price Range · Brightness · Rating Stars · Skill Ring · Savings Goal · Seek Bar · Temp Dial · Upload Bar · Survey Scale | 88.8 |
| 10 | Quiz, Polls & Surveys | MCQ · Quiz Runner · True/False Sprint · Poll · Live Poll · Odd One Out · Fill Blank · Match Pairs · Survey · Daily Challenge | 88.8 |
| 11 | Loading & Empty States | Skeleton Feed · Spinner Family · Page Bar · Empty Search · Inbox Zero · Error Retry · Blur-Up Images · Loading Buttons · App Loader · Filter Empty | 89.1 |
| 12 | Timelines & Activity | Order Tracker · Activity Feed · Exam Countdown · Milestones · Day Schedule · Story Timeline · Workout · Streak Grid · Changelog · Journey Map | 89.5 |
| 13 | Settings & Preferences | Theme · Notifications · Accent Colour · Font & Density · Language · Privacy · Quiet Hours · Settings Page · Danger Zone · Accessibility | 89.6 |
| 14 | Heroes, Banners & Footers | Hero Search · Hero Email · Announcement Bar · Cookie Banner · Sale Countdown · Newsletter Band · App Banner · Mega Footer · Sticky CTA · Hero Carousel | 89.7 |
| 15 | Chat & Social | Chat Window · Message Input · Typing Stage · Reactions · Stories · Comments · Voice Note · Group Members · Share Sheet · Live Chat | 89.8 |

Collection average **88.1/100**. Sakuga Kit total: **163** (13 showcase + 150 components).
Spec: see `SAKUGA_KIT.md`, section "The 150".
