# henryye2000.github.io

Personal homepage — plain HTML and CSS, no build step, no framework.

## Structure

```
index.html          About, experience timeline, education, three selected papers
publications.html   All five papers, grouped by type
assets/style.css    All styling (single file)
assets/avatar.jpg   Portrait
assets/favicon.ico
.nojekyll           Tells GitHub Pages to serve files as-is
```

Both pages repeat the same two blocks: the sticky top bar (monogram + page switcher) and the
sticky profile rail. Edit both files when changing either.

Experience entries carry title, organisation and dates only — no project detail anywhere on the
site; the home page only states that the current role is on the cloud-native container engine
platform.

## Local preview

```bash
python -m http.server 8000
# then open http://localhost:8000
```

## Deploy (GitHub Pages)

Push to `henryye2000/henryye2000.github.io`, branch `main`, root directory.
No Jekyll, no Actions required.

## Design notes

- No boxes anywhere: no card around the profile, no borders around papers. Structure comes from
  alignment, whitespace and hairline rules.
- Publications use a year rail: an 84px left column with the year in brown, then title, authors
  and a meta line (venue pill · conference · links). Below 560px the year moves above the title.
- White canvas. Colour lives in components only: deep blue (`--blue`) for links, the monogram,
  venue pills and the active nav pill; brown (`--brown`) for section labels, years, field labels
  and the best-paper badge.
- Type scale is rooted at `html { font-size: 17px }`; change that one value to resize everything.
- Layout: sticky top bar (66px) + two-column grid — 292px sticky profile rail, then content.
  Below 900px it collapses to a single column and the rail stops sticking.
- The avatar has no border and no shadow: the source photo has a white background, so it sits
  flush on the white canvas.
- Hover interactions: venue pills stay put, but the year shifts to blue, experience rows get a
  light wash, nav pills lift, profile links shift right, `All publications →` slides right.
  All motion is disabled under `prefers-reduced-motion`.
- All tokens are in the `:root` block of `assets/style.css`.

## Paper links

- Fremer → https://dl.acm.org/doi/abs/10.14778/3749646.3749656 (PVLDB DOI)
- CloudChurn → https://link.springer.com/chapter/10.1007/978-981-95-4158-4_20
- ADMA (PILES, Best Paper) → https://link.springer.com/chapter/10.1007/978-3-031-46661-8_1
- ATFNet → https://arxiv.org/abs/2404.05192
- Online Ensemble Transformer (ICDE 2026) → https://arxiv.org/abs/2508.12773
