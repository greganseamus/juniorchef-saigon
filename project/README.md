# JuniorChef Saigon — Design System

> A design system for **JuniorChef Saigon**, a company providing international cooking clubs to schools in Ho Chi Minh City, Vietnam. The audience is children ages 6–12 at international schools, and (indirectly) their teachers and parents.

---

## The company, in plain English

JuniorChef Saigon runs cooking clubs *inside* schools in HCMC. Each session, kids follow a recipe from a different part of the world, cook it together with an instructor, and take home an illustrated recipe sheet + a **coloring page** themed to the cuisine. Kids are the primary audience; teachers and parents are the secondary audience.

The current output format (what we have source material for) is a **printed recipe sheet** — 2 pages, A4/letter landscape-ish, with:

- **Page 1** — a recipe. Logo top-left, dish name in big type, ingredients list on the left, numbered directions on the right, and a real photo of the finished dish.
- **Page 2** — a **coloring page** themed to the cuisine (Vietnamese market, Korean BBQ stall, Tuscan village, Russian winter cabin, summer garden picnic). Clean black-and-white line art, age 6–12 appropriate, with playful anthropomorphic ingredient characters.

The **next step**, which this system supports, is graduating older kids (roughly 9–12) from pure coloring sheets to **worksheets that challenge them more** — reading comprehension, math-in-the-kitchen, kitchen vocabulary, cultural-context prompts, design-your-own-dish, etc.

---

## Source material used to build this system

All from the project's `uploads/` folder — five recipe PDFs provided by the user:

| Recipe | File |
|---|---|
| Summer Berry Shortcakes | `uploads/Summer Berry Shortcakes.pdf` |
| Lemongrass Chicken and Rice Noodle Salad | `uploads/Lemongrass Chicken and Rice Noodle Salad.pdf` |
| Korean Beef Bulgogi Skewers | `uploads/Korean Beef Bulgogi Skewers.pdf` |
| Chicken Stroganoff | `uploads/Chicken Stroganoff.pdf` |
| Lentil Bolognese | `uploads/Lentil Bolognese.pdf` |

Raw images extracted from each PDF live in `uploads/extracted/`. Cleaned copies used by this system live in `assets/`.

**No codebase, Figma file, or brand guidelines were provided** — the visual foundations below are reverse-engineered from the PDFs. Flag any call where this assumption is wrong so I can correct it.

---

## Index — what lives where

```
.
├── README.md                        ← you are here
├── SKILL.md                         ← entry point when used as a Claude skill
├── colors_and_type.css              ← design tokens (colors, type, space, radii, shadows)
├── assets/
│   ├── logo/juniorchef-logo.png     ← the master wordmark (clean, on white)
│   ├── photos/                      ← hero dish photos, one per recipe
│   └── coloring/                    ← page-2 line-art scenes, one per recipe
├── preview/                         ← design-system cards (shown in the Design System tab)
├── ui_kits/
│   └── recipe-sheet/                ← the current recipe-sheet product
│   └── worksheet/                   ← the new older-kids worksheet product
└── uploads/                         ← original PDFs + extracted image layers
```

---

## Content fundamentals

How JuniorChef *sounds*. All observations taken from the 5 recipe PDFs.

**Voice: an encouraging adult chef talking to a capable kid.** Not babyish. Not pretentious. Warm, practical, and specific. The reader is trusted to handle a knife and a hot pan — with guidance, not hand-holding.

- **Address: "you" + imperatives.** Every direction is a command the kid gives themselves. "Chill everything first." "Pour into the flour mixture." "Trust your tastebuds." Never "the student should" or "one would."
- **Contractions everywhere.** "don't," "it's," "they'll." Formal writing would feel cold here.
- **Sentence rhythm: short punchy lines, then one longer sensory one.** "Lumpy is fine — do NOT overwork the dough or it turns tough." "Summer in a mouthful." "Fold and eat — Korean BBQ style!"
- **Step headings are verb-led and friendly, not clinical.** "Wake Up the Dried Mushrooms," "The Magic Marinade," "Build the Sauce," "Whip the Cream," "Wrap and Go!" NOT "Step 4: Rehydrate Mushrooms."
- **One culinary fact per recipe, explained simply.** "Here's the secret: enzymes in the pear actually break down the meat and make it melt-in-your-mouth tender." "Cold ingredients are the secret to flaky shortcake." These are the "a-ha" moments that make the kid feel like they learned something real.
- **Honest safety nudges, not warnings.** "Wash your hands after touching the raw chicken!" — a single casual exclamation, not a boxed-out ALLERGEN NOTICE. "Slice the thickest piece of chicken to check it's fully cooked through — no pink!"
- **Sensory language.** "coarse, lumpy sand," "juicy and syrupy," "toasty," "glossy," "caramelised." Kids are taught to cook by *feel and sight*, not by thermometer numbers.
- **Judgement calls encouraged.** "Taste and adjust — more honey for sweet, more vinegar for tangy." "Does it need salt? More mustard? Trust your tastebuds."
- **Casing: Title Case on step headings, sentence case in body.** The dish name itself is rendered ALL CAPS in the big display slot, but spelled Title Case in body copy.
- **Units: metric-first, grams and millilitres.** Tablespoons and teaspoons only for very small quantities. Temperatures in °C.
- **Emoji: never in body copy.** The coloring pages use smiley-face cartoons for anthropomorphic ingredients, but that's illustration, not type.
- **Numbers: numerals always** ("2 stalks lemongrass," "60ml fish sauce") — never "two stalks."
- **"For 4"** is the standard serving label. Short, understated, always in the ingredients block.

**Words we use:** chunks, piles, ribbons, coat, crack (of pepper), pinch, splash, scatter, wake up, build, bring it together, assemble, go! pile, tuck, fold.

**Words we avoid:** "yummy," "delicious!" (overused in kids' food media), "scrumptious," "little chefs," "tiny hands" — condescending. No "kiddos." No "magic" outside of one literal callout per recipe. No baby talk.

---

## Visual foundations

The full aesthetic, reverse-engineered from the PDFs and logo.

### Overall vibe
**Printed cookbook for kids meets bright market stall.** Warm paper, confident chunky type, hand-drawn line-art illustrations, real food photography that looks like it was shot on a kitchen counter — not styled-to-death Instagram food. The whole thing should feel like something a 9-year-old would want to pin to the fridge.

### Color

Palette sampled pixel-exact from the logo:

| Token | Hex | Role |
|---|---|---|
| `--jc-red` | `#D82828` | Primary brand. "J" + "SAIGON" + accent lines. Default for buttons, key callouts. |
| `--jc-teal` | `#28A090` | Primary brand. "UNIO" + tomato-leaf. Default for "fresh / success / go" moments. |
| `--jc-orange` | `#F88000` | Secondary. "H" + tomato body. Warm-food accent. |
| `--jc-yellow` | `#F8C048` | Secondary. "R" + "C." Highlights, sun, happy. |
| `--paper` | `#FFFDF7` | Default page background — warm off-white, not pure white. |
| `--paper-warm` | `#FBF3E2` | Cards, section fills. Cream. |
| `--ink` | `#1F1A14` | Body text + coloring-book line art. Warm black, never pure `#000`. |

**Rules:**
- Never use blue or purple. This palette is deliberately warm — teal is the only cool hue and it reads as "fresh mint / jade," not "tech blue."
- When multiple brand colors appear together, they share roughly equal visual weight — like the logo itself. Don't pile them on top of each other with no breathing room.
- Tints (`--jc-*-tint`) are for fills behind text; shades (`--jc-*-deep`) are for text on light fills.

### Typography

- **Display: Fredoka** (Google Fonts). Chunky rounded geometric sans. Used ALL CAPS for dish titles, section headers, and any "sign-painter" moment.
- **Body: Nunito** (Google Fonts). Friendly rounded sans. Sentence case, weight 400 for body, 700–800 for emphasis.
- **Hand: Caveat** (Google Fonts). Used *very* sparingly — tip callouts, "chef's note" boxes, or wherever we want the feel of a marker scribble.

⚠️ **SUBSTITUTION FLAG**: The logo uses a *custom* chunky rounded display face (not quite Fredoka, not quite Baloo, not quite Bagel Fat One). Fredoka is the nearest widely-available free match. **If you have the original logo's font file, please share it so we can swap in the real thing.** Until then, the logo image is used as a raster asset (`assets/logo/juniorchef-logo.png`) and is NOT recreated in CSS type.

### Backgrounds & texture
- Default page is **warm off-white paper** (`--paper` `#FFFDF7`). Never pure `#FFFFFF` for large canvases — it's too clinical.
- Cards and section fills use **cream** (`--paper-warm` `#FBF3E2`).
- No gradients. No noise. No stock patterns.
- Imagery *is* the texture: full-bleed food photos, or line-art coloring scenes.

### Illustration style
- Line-art coloring pages use **thick confident strokes** (~3px equivalent), clean corners, rounded contours, anthropomorphic vegetables/fruits/ingredients with big round eyes and closed-mouth smiles. Scenes are richly detailed — market stalls, kitchen props, banners with the dish name spelled out in playful caps.
- Each coloring scene is **culturally grounded to the dish** — Korean lanterns for Bulgogi, Tuscan arches for Bolognese, etc. Never generic.
- NEVER hand-roll SVG illustrations when a coloring-page asset already exists. Treat them as shipped artwork.

### Photography
- Dish photos are **top-down or 3/4 angle**, shot on natural wood or neutral countertop, minimal props. The food is the hero. No over-styling, no scattered herbs for decoration.
- Light is **warm, soft, slightly overexposed** — like a sunny kitchen window. Never cool daylight.
- Photos are square or near-square (600×600 was the source size) and sit inside a generous rounded-corner frame or free-floating on paper.

### Borders, radii, shadows
- **Radii are generous**: cards `22px` (`--radius-lg`), tiles `14px`, pills for buttons. Nothing sharp.
- **Borders are either absent or thick**: either no border, or a confident `2.5px`–`4px` line in `--ink` or a brand color. No 1px hairlines except for data rules.
- **Shadows are warm and soft**: `0 12px 32px rgba(31,26,20,0.12)` — cast from warm black, not grey-blue.
- We also use a **"sticker drop"** shadow (`--shadow-pop`: flat `0 6px 0` in near-black) on some buttons and callouts for that "printed on heavy paper" feel. This is intentional kid-friendly trope territory — use it on worksheet/game elements, not on trust-building parent-facing copy.

### Motion
- Subtle. These are mostly print-adjacent artifacts.
- When we do animate: **quick, springy, slightly overshooting.** 200–350ms, easing like `cubic-bezier(0.34, 1.56, 0.64, 1)` (a mild bounce).
- Fades are fine. Bluish-purple-gradient "aurora" effects are forbidden.

### Interaction states
- **Hover (desktop):** lift by 2–4px with shadow growth; or brighten the fill by ~8% (mix with white).
- **Active / press:** push DOWN 2px and kill the shadow. "Stamping" feel.
- **Focus:** a `3px` outer ring in `--jc-teal` with `2px` offset. Visible, on-brand, never the default browser blue.
- **Disabled:** 40% opacity, no pointer events.

### Layout
- Generous whitespace. Kids' materials fail when they feel crowded.
- Print-oriented: respect A4 (`210×297mm`) and US Letter (`8.5×11in`) page bounds.
- Column structures: ingredients and directions live side-by-side on the recipe sheet, with the dish title spanning the full width.
- Hit targets on any screen-based variant: **48px min.** (ages 6–12, fingers vary.)

### What we explicitly DON'T do
- No bluish-purple gradients.
- No 1px-left-border accent cards.
- No rainbow-gradient text.
- No emoji in product copy. (Emoji ≠ our cartoon illustrations.)
- No drop-cap fancy-cookbook serifs. Wrong audience.
- No skeuomorphic chalkboards / notebook-paper backgrounds. It reads "early-2010s scrapbook" and fights the clean line-art look.

---

## Iconography

The source PDFs **do not contain an icon system**. They rely on illustration, typography, and photography to carry meaning. We have two honest choices:

1. **Keep it illustration-first.** Use the anthropomorphic ingredient characters from the coloring pages as "icons" where a symbol would normally go.
2. **Pair with a free icon set** for UI moments that genuinely need a glyph (timer, serves, difficulty, allergen).

We go with **both**. Recipe-sheet style artifacts lean on illustration. Worksheet / UI style artifacts use **Lucide** icons (via CDN) — rounded, open, friendly stroke style — which matches the visual DNA of Fredoka + the coloring-page linework far better than sharp-cornered sets like Heroicons outline or Material.

**Lucide usage:**
- CDN: `https://unpkg.com/lucide@latest`
- Stroke width: `2px` (default) for inline; `2.5px` for large standalone marks.
- Color: `currentColor` — tint via CSS.
- Sizes: 16px, 20px, 24px, 32px. Nothing in between.

⚠️ **SUBSTITUTION FLAG**: Lucide is a substitution, not a discovered system. If you already have an icon set or want bespoke illustrated icons, tell me and I'll swap it in.

**Emoji**: do not use in UI copy. Anthropomorphic-ingredient illustrations from the coloring pages fill that role. Unicode glyphs (★, ✓) are fine for ratings / checkmarks but prefer Lucide where possible.

**Logo as icon**: the logo is never used as a favicon-sized mark — it doesn't read below ~80px wide. For small-mark moments (app icon, favicon), use the **"J" letterform** from the logo on a solid-color tile. (TODO: produce this asset — flagged below.)

---

## Caveats / open questions (please confirm!)

1. **Logo font.** Fredoka is a substitution. If you have the original font file, share it.
2. **Icon system.** Lucide is a substitution. Confirm or provide an alternative.
3. **Brand voice examples** are drawn entirely from 5 recipe PDFs. If you have other copy (parent-facing emails, website, enrollment forms), share so the voice guide can cover more situations.
4. **"Junior Chef" app / website.** I did not find one. If there's an existing digital surface (enrollment site, Facebook page, parent portal), share a link or screenshots and I'll build a UI kit for it.
5. **Small logo / favicon.** I do not have a compact "J" mark. Happy to produce one once you confirm direction.
6. **Worksheet scope.** For the older-kids worksheet UI kit, I'm interpreting "more challenge" broadly — reading comprehension, math-in-kitchen, vocab, design-your-own. Please confirm which of these you actually want.
