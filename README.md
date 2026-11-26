# layla-adeli.github.io

Personal academic site — static HTML and CSS, no build step and no dependencies.

## Structure

```
index.html                       single-page home: bio, research, projects,
                                 publications, honors, teaching, skills
research-thesis.html             senior thesis detail page
research-feature-extraction.html on-chip feature extraction detail page
research-iontophoresis.html      Cambridge iontophoresis detail page
research-synthetic-cells.html    Murray Lab synthetic cells detail page
project-spike.html               Tiny Tapeout spike detector ASIC
project-dll.html                 8 GHz DLL
style.css                        all styling (design tokens at the top)
img/                             figures, mostly pulled from the portfolio deck
Layla_Adeli_CV.pdf               CV, compiled from LaTeX
research.html, projects.html,    redirects to index.html anchors, so old links
awards.html                      keep working
```

## Editing

**Colors, fonts, spacing** live in the `:root` block at the top of `style.css`:

| Variable | Purpose |
| --- | --- |
| `--paper` | page background |
| `--grid-minor` / `--grid-major` | the two grid line layers (8px / 40px) |
| `--accent` | drafting blue, used for links and figure ticks |
| `--accent-2` | redline, callout borders only |
| `--col` | content column width |

To make the grid fainter or stronger, change the alpha in `--grid-minor` and
`--grid-major`. To remove it entirely, delete the four `background-image`
gradients in the `body` rule.

**Adding a research entry or project:** copy an existing `<div class="entry">`
block in `index.html`. Use `class="entry no-thumb"` for entries without a
thumbnail image.

**Adding a detail page:** copy any `research-*.html` file — the header, nav, and
footer are identical across pages, so only the content inside `<main>` changes.

**Swapping the intro image for a photo:** add `img/portrait.jpg` and change the
`src` in the `<figure>` inside `section.intro` in `index.html`.

## Local preview

```sh
python3 -m http.server 8000
# then open http://localhost:8000
```

## Deploying

Served as-is by GitHub Pages from the repository root. `.nojekyll` tells Pages
to skip Jekyll processing.
