# Recipe Sheet — UI Kit

A print-first recreation of the existing JuniorChef Saigon 2-page recipe sheet, built as reusable HTML/CSS components. This is the **current** product; use it as the ground-truth reference when building anything else. Open `index.html` to see a full rendered sheet.

## Components (in this folder)

- `RecipeSheet.html` — the whole 2-page layout
- `RecipeHeader.html` — logo + "RECIPE" eyebrow row
- `DishTitle.html` — big display dish name
- `IngredientsList.html` — left column list with "For 4" header
- `DirectionsList.html` — right column numbered steps
- `HeroPhoto.html` — dish photo in rounded frame
- `ColoringPage.html` — page 2 line-art scene

Open each standalone HTML to view that component in isolation.

## Sizing

Each page is 2100 × 1485px (A4 landscape-ish at ~180dpi). Scale to fit your print setup; the layout is proportionally clean at that size.

## Fidelity

Content is taken verbatim from the user's 5 PDFs, using the Summer Berry Shortcakes recipe as the demo in `index.html`. The coloring-page asset is the actual page-2 image from the PDF — do not recreate it in SVG.
