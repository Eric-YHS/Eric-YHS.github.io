# ericyhs.me

Source of the personal landing page served at <https://ericyhs.me>
(from this repository, `Eric-YHS/Eric-YHS.github.io`, via GitHub Pages).

## Contents

| Path | Purpose |
| --- | --- |
| `index.html` | The published landing page. Self-contained: inline CSS, no build step, no third-party scripts. |
| `CNAME` | Custom domain binding for GitHub Pages. |
| `_config.yml` | Minimal Jekyll configuration used by the legacy GitHub Pages build. |

## How publishing works

GitHub Pages builds `main` with the legacy Jekyll pipeline. `index.html` has no
Jekyll front matter, so it is copied verbatim to the site root — edit the file,
push to `main`, and the site rebuilds within a minute.

## Local preview

Any static server is enough:

```bash
python3 -m http.server 8000
# then open http://127.0.0.1:8000
```

## Design notes

- Respects `prefers-color-scheme` (light and dark).
- No JavaScript, no external fonts, no analytics: the page is a single
  dependency-free HTML document.
- Project cards link to the public repositories; add or remove cards in the
  "Selected projects" section of `index.html`.
