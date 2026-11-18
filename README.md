# Plate Map

A single-page tool for laying out cell culture plates (6, 12, 24, 48, 96 or 384 wells) and exporting a clean plate map.

**Use it:** https://lphilbrooks.github.io/plate-map/

1. Pick a plate size, and add a title and notes if you want them.
2. Make groups (name + colour).
3. Click or drag across wells, then assign a group or type a label (optionally numbered 1, 2, 3…).
4. Export as PNG, SVG (editable vector), PDF (via print), Excel `.xlsx` or CSV (well list), or copy the image to the clipboard. Save a `.json` to reopen and edit later.

   For Excel, use the `.xlsx`: every label is stored as text, so `1/10`, `0012` or `=1+1` stay exactly as typed. Excel can change the same labels when it opens a CSV (dates, dropped zeros), and CSV labels starting with `=`, `+`, `-` or `@` get a leading `'` so spreadsheets don't run them as formulas.

Shortcuts: `1`–`9` assign a group, `0` removes it, `Delete` clears wells, `Esc` deselects, `Ctrl+Z` undoes, `Ctrl+Y` redoes, `Ctrl+A` selects all, and arrow keys (with `Shift` to extend) move the selection. On touch screens, tap wells to select or deselect them.

## Seeding calculator

The panel next to the plate (below it on smaller screens; toggle with **Calculator**) works out how to seed the wells:

- **Vessel:** "This plate" follows the plate size you picked and fills in the growth area and medium volume per well. Other plates, dishes, flasks or a custom size are also available. Defaults come from Thermo Fisher's [Useful numbers for cell culture](https://www.thermofisher.com/us/en/home/references/gibco-cell-culture-basics/cell-culture-protocols/cell-culture-useful-numbers.html) table; brands differ slightly, so check your plate's datasheet.
- **Target density:** in cells/cm², cells/well or cells/mL. Switching units converts the number so the seeding stays the same.
- **Counted suspension:** type it as `1.2e6`, `1.2 x 10^6`, `1,200,000` or `1.2M`.
- **Wells to seed:** the number of selected wells, or the whole plate when nothing is selected. You can type your own, plus an extra-volume margin (10% by default).

It gives cells per well, the cells/mL the seeding suspension needs, the total volume to make, and how much stock and medium to mix. If the stock is too dilute it tells you how much to pellet and what volume to resuspend in. **Add to notes** puts a one-line summary in the plate notes so it appears on the exported map.

The rough starting densities (fast-growing adherent lines, MSCs, endothelial cells, suspension lines) each link to their source. They are starting points only: the right density depends on the cell type, line, passage, medium, assay and timing, so check your supplier's datasheet and test a few densities.

Everything runs in your browser; nothing is uploaded.

## Tests

Serve the folder (`python -m http.server`) and open `/tests/`. The page drives the app in an iframe and shows the result, also in the tab title. It uses its own storage key, so it never touches a saved map. Live copy: https://lphilbrooks.github.io/plate-map/tests/

It is one HTML file with no dependencies, so you can also download `index.html` and open it offline.
