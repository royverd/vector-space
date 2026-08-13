# vector-space

_(N-Space)_

Interactive N-dimensional (0–9D) vector space and linear transform visualizer, running entirely in the browser.

## Install

No install — it's a single self-contained HTML file. Clone and open it:

```bash
git clone <this-repo-url>
cd vector-space
```

Then open `vector_space.html` in any modern browser (double-click, or `open vector_space.html` / `start vector_space.html`). It loads three.js from a CDN, so an internet connection is required on first load.

## Usage

- **Dimensions** — set N (0–9). Dimensions 0–2 render as X/Y/Z; higher dimensions are embedded on a fixed spread of extra directions so they stay visually distinct.
- **Transform matrix (M)** — edit an N×N matrix, then click **Jump** to apply it instantly or **Animate** to ease into it. Editing the fields alone does not move anything until one of those is clicked.
- **Rigid transform** toggle — orthonormalizes M (Gram–Schmidt) into a pure rotation/reflection before applying, preserving spacing and angles. Off, M is used as typed, so shear and non-uniform scale are allowed.
- **Origin anchoring** — toggle off to add a translation after `M·v`, making the map affine instead of linear.
- **Vectors** — add named, colored vectors by component; edit or remove them from the list.
- **Display** — toggle the grid, a ghost overlay of the original (untransformed) grid, and vector span planes (translucent parallelogrms showing what each pair of vectors spans); adjust grid extent and background color.
- **Camera** — drag to rotate, shift+drag or drag empty space to pan, scroll to zoom, hover any axis/vector/origin to see its name. For N ≤ 2 the view locks to a flat orthographic camera with no rotation.

## Limitations

- Requires network access for the three.js CDN script — there's no offline/vendored fallback.
- No save/load or URL-state — vectors, matrix, and axis setup reset on reload.
- N is capped at 9; above ~6 the grid line count grows as N·(N−1)/2 and can get slow.
- Uses a manually-implemented orbit control (no `OrbitControls` addon), so camera behavior is custom rather than three.js's stock controls.

## License

[MIT](LICENSE)
