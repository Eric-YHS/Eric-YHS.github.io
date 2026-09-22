# ericyhs.me

![CI](https://github.com/Eric-YHS/Eric-YHS.github.io/workflows/CI/badge.svg)
[![License: MIT](https://img.shields.io/badge/License-MIT-yellow.svg)](LICENSE)

Source of the personal landing page served at <https://ericyhs.me>
(from this repository, `Eric-YHS/Eric-YHS.github.io`, via GitHub Pages).

## Contents

| Path | Purpose |
| --- | --- |
| `index.html` | The published landing page. Self-contained: inline CSS, no build step, no third-party scripts. |
| `CNAME` | Custom domain binding for GitHub Pages. |
| `_config.yml` | Minimal Jekyll configuration used by the legacy GitHub Pages build. |
| `LICENSE` | MIT for the page and its sources (see [License](#license)). |
| `.github/workflows/ci.yml` | Checks described under [Checks](#checks). |

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

## Checks

There is no build step, so CI only guards the invariants this page promises:

- `_config.yml` parses as YAML and `CNAME` still says `ericyhs.me`.
- `index.html` stays a single dependency-free document: doctype, `lang`, `<title>`,
  no external script/stylesheet/image/iframe, no web fonts, and still reacting to
  `prefers-color-scheme`.
- every project card still points at a repository that exists — a renamed or
  deleted project turns into a 404 on the landing page, and that is what this step
  catches before it is published.

## License

The page, its inline styles and this repository's sources are MIT licensed
(see [`LICENSE`](LICENSE)). The name "Eric-YHS" and the ericyhs.me domain are not
included in that grant, so a fork may reuse the layout but must not present itself
as the author's personal site; each linked project keeps its own repository's
license.
