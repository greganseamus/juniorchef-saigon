---
name: juniorchef-saigon-design
description: Use this skill to generate well-branded interfaces and assets for JuniorChef Saigon (international cooking clubs for ages 6–12 in Ho Chi Minh City, Vietnam) — either for production or throwaway prototypes, mocks, recipe sheets, worksheets, parent-facing pages, etc. Contains essential design guidelines, colors, type tokens, fonts, assets (logos, recipe photos, coloring-page line art), and UI kit components for both the existing recipe-sheet product and the new older-kids worksheet product.
user-invocable: true
---

Read `README.md` within this skill, and explore the other available files.

- `colors_and_type.css` is the token source of truth. Import it into any artifact.
- `assets/` holds the master logo, per-recipe dish photos, and per-recipe coloring-page line art. Copy these out; do NOT hand-draw SVG replacements.
- `ui_kits/recipe-sheet/` is the current printed 2-page product (recipe + coloring page).
- `ui_kits/worksheet/` is the new older-kids worksheet (ages 9–12). Use its card + step patterns for any other kid-facing challenge material.
- `preview/*.html` are small cards that document individual tokens / components.

If creating visual artifacts (slides, mocks, throwaway prototypes, worksheets, emails, one-off printables), copy assets out and create static HTML files for the user to view. For real production code, copy the tokens from `colors_and_type.css` and read the content + visual foundations in `README.md` to become an expert in designing with this brand.

If the user invokes this skill without any other guidance, ask them what they want to build or design (recipe sheet? worksheet? parent email? enrollment page? club poster?), ask which recipe or theme, ask the age band (6–8 or 9–12), then act as an expert designer who outputs HTML artifacts or production code, depending on the need.
