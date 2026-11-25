# Studs Up! — official website

A static game page for **Studs Up!**, published by [Gand Games](https://gand.games/).

- Primary address: `https://studs-up.gand.games/`
- Old address: `https://gand.games/studsup/` redirects here (a stub, not a copy).
- Hosting: a Cloudflare Worker with static assets (`studs-up-gand-games`, Gand
  account), deployed by hand (see Deploy). Until 2026-11-25 it was GitHub Pages
  from `main`; GitHub could not renew its certificate behind the Cloudflare proxy.
- Trailer: too big for Workers static assets (25 MiB per file), so it is served
  from the R2 bucket `studs-up-media` at `https://media.studs-up.gand.games/`.
- No framework, build step, external fonts or third-party scripts.

Edit `index.html`, validate with `npx --yes html-validate@9 index.html`, commit,
then deploy (below). Screenshots live under `public/shots/`; all eight are lossless captures
at 1920 × 1080. Asset provenance and capture instructions are in `CAPTURES.md`.

The game checkout at `~/projects/games/studs-up/StudsUp` is actively edited by another
agent. Keep it read-only and use isolated copies for screenshots.

## Deploy

```bash
tools/deploy_cloudflare.sh
```

It runs `tools/build_site.sh`, which builds `_site/` from the **committed** tree
(commit first) with only `index.html`, `public/`, `robots.txt` and `sitemap.xml`
(this file, `CAPTURES.md`, `capture-manifest.json`, `tests/` and the dotfiles are
not served), then `wrangler deploy` uploads it with your local wrangler login
([`wrangler.jsonc`](wrangler.jsonc) holds the custom domain).

Files in `tools/r2_media.txt` (the trailer MP4) stay in git but are left out of
the build: they are served from R2 at `https://media.studs-up.gand.games/<repo
path>`, the page links there, and `_redirects` sends the old path there. After a
new encode, commit it and run `tools/push_media_r2.sh` (by hand) before deploying.

## The gand.games card

There is no fallback copy any more. `gand.games/studsup/` in the `gand.games`
repository (`~/projects/games/gand.games`) is a noindex redirect stub to this site,
made while gand.games was on GitHub Pages, which cannot send a 301; it needs no syncing.

The catalogue card repeats some of this page's copy: description, spec row, Steam
links, release status. It lives in `gand.games/index.html` with its screenshots in
`gand.games/public/studsup/`. When the release date, platforms, campaign wording
or store links change here, change the card too.

## Validation

The initial publication passed HTML validation, local asset checks, and browser
checks at 360, 390, 768 and 1440 pixels. The screenshot viewer (six images then, eight since 1.1) supports previous /
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
