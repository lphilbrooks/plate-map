# Plate Map

A single-page tool for laying out cell culture plates (6, 12, 24, 48, 96 or 384 wells) and exporting a clean plate map.

**Use it:** https://lphilbrooks.github.io/plate-map/

1. Pick a plate size, and add a title and notes if you want them.
2. Make groups (name + colour).
3. Click or drag across wells, then assign a group or type a label (optionally numbered 1, 2, 3…).
4. Export as PNG, SVG (editable vector), PDF (via print), CSV (well list) or copy the image to the clipboard. Save a `.json` to reopen and edit later.

Shortcuts: `1`–`9` assign a group, `0` removes it, `Delete` clears wells, `Esc` deselects, `Ctrl+Z` undoes.

Shortcuts also include `Ctrl+Y` to redo, `Ctrl+A` to select all, and arrow keys (with `Shift` to extend) to move the selection. On touch screens, tap wells to select or deselect them.

Everything runs in your browser; nothing is uploaded.

## Tests

Serve the folder (`python -m http.server`) and open `/tests/`. The page drives the app in an iframe and shows the result, also in the tab title. It uses its own storage key, so it never touches a saved map. Live copy: https://lphilbrooks.github.io/plate-map/tests/

 It is one HTML file with no dependencies, so you can also download `index.html` and open it offline.
