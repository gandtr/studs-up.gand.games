# Studs Up! — official website

A static game page for **Studs Up!**, published by [Gand Games](https://gand.games/).

- Primary address: `https://studsup.gand.games/`
- Fallback: `https://gand.games/studsup/`
- Hosting: GitHub Pages, `main` branch, repository root, matching the Aldith site.
- DNS: CNAME `studsup` to `gandtr.github.io` (managed by the site owner).
- No framework, build step, external fonts or third-party scripts.

Edit `index.html`, validate with `npx --yes html-validate@9 index.html`, then push
to `main`. Screenshots live under `public/shots/`; all six are lossless captures
at 1920 × 1080. Asset provenance and capture instructions are in `CAPTURES.md`.

The game checkout at `~/projects/games/StudsUp` is actively edited by another
agent. Keep it read-only and use isolated copies for screenshots.

## Keeping the fallback current

The `gand.games` repository contains a complete fallback at `studsup/`, with the
same relative asset paths. After editing this page, copy `index.html` and
`public/` there and run that repository's HTML and asset checks. The catalogue
card and its five screenshots are maintained in `gand.games/index.html` and
`gand.games/public/studsup/`.

## Validation

The initial publication passed HTML validation, local asset checks, and browser
checks at 360, 390, 768 and 1440 pixels. The six-image viewer supports previous /
next, arrow keys, Escape, focus return and opening original images. Without
JavaScript the screenshot links still work.
