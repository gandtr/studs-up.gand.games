# Studs Up! — official website

A static game page for **Studs Up!**, published by [Gand Games](https://gand.games/).

- Primary address: `https://studs-up.gand.games/`
- Old address: `https://gand.games/studsup/` redirects here (a stub, not a copy).
- Hosting: GitHub Pages, `main` branch, repository root, matching the Aldith site.
- DNS: CNAME `studs-up` to `gandtr.github.io` (managed by the site owner).
- No framework, build step, external fonts or third-party scripts.

Edit `index.html`, validate with `npx --yes html-validate@9 index.html`, then push
to `main`. Screenshots live under `public/shots/`; all six are lossless captures
at 1920 × 1080. Asset provenance and capture instructions are in `CAPTURES.md`.

The game checkout at `~/projects/games/studs-up/StudsUp` is actively edited by another
agent. Keep it read-only and use isolated copies for screenshots.

## The gand.games card

There is no fallback copy any more. `gand.games/studsup/` in the `gand.games`
repository (`~/projects/gand/gand.games`) is a noindex redirect stub to this site,
because GitHub Pages cannot send a 301; it needs no syncing.

The catalogue card repeats some of this page's copy: description, spec row, Steam
links, release status. It lives in `gand.games/index.html` with its screenshots in
`gand.games/public/studsup/`. When the release date, platforms, campaign wording
or store links change here, change the card too.

## Validation

The initial publication passed HTML validation, local asset checks, and browser
checks at 360, 390, 768 and 1440 pixels. The six-image viewer supports previous /
next, arrow keys, Escape, focus return and opening original images. Without
JavaScript the screenshot links still work.

## Trailer

The native HTML video player is at `#trailer`, linked from the hero and catalogue
card. It uses `preload="none"`, a poster, inline playback, standard controls and
optional English WebVTT captions. No autoplay or JavaScript is required.

Files in `public/trailer/` come from `../studs-up-trailer/output/`: the 62-second
1080p60 H.264/AAC MP4, an optimized JPEG of its title-card poster, and narration
captions converted from SRT to WebVTT. Trailer staging and credits are documented
in the source project's README.
