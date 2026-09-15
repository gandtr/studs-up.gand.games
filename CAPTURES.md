# Studs Up! website assets

Captured on 2026-09-16 from the current working tree of
`/home/arda/projects/games/StudsUp`, including its updated player artwork.
The game repository was read-only throughout. No commits, files, saves, running
sessions or generated artifacts in that repository were changed by this task.

## Source and isolation

- A full copy of the root Lua files, `data/`, `assets/`, and `scripts/` was made at
  `/tmp/studsup-site-20260916/game` before running anything.
- The source HEAD, UTC copy time, and SHA-256 digest of every copied file are
  recorded in `capture-manifest.json` (not included in the published site).
  Source HEAD: `21712b046dc51b9f109e5de95822afdb2c7924fe`; copied at
  `2026-09-15T20:54:15.596184+00:00` (September 16 in Tokyo).
- Captures used the game's `scripts/visual-review.sh` with a separate headless
  Cage compositor and temporary `XDG_DATA_HOME` for each invocation.
- The screenshot harness ran the real LÖVE renderer at 1920 × 1080.
  Menu captures use the game's existing review fixtures; match captures run
  live simulation with the existing harness steering the active player.
- Screenshots were converted to lossless WebP without retouching, cropping,
  resizing, compositing, or adding overlays.

## Published screenshots

| Website file | Engine scene | Capture point |
|---|---|---|
| `public/shots/01-pub-league.webp` | `pubyard` | 5 seconds |
| `public/shots/02-concrete.webp` | `concrete` | 4 seconds |
| `public/shots/03-recruitment.webp` | `menu-draft` | frame 2 |
| `public/shots/04-pub-office.webp` | `menu-hub` | frame 2 |
| `public/shots/05-upgrades.webp` | `menu-shop` | frame 2 |
| `public/shots/06-medical.webp` | `menu-medical` | frame 2 |

`public/lineup.webp` was freshly rendered using the game's existing store-art
`lineup()` function, current character models, names and Mincers kit. Only the
isolated renderer copy was adapted to output the lineup on a transparent canvas.
`public/og.jpg` uses the freshly rendered main capsule with aspect-preserving
resizing and background padding. The favicon comes from the current game assets.

Fonts are copied from the game and self-hosted; their OFL licenses are included.
The original PNG captures and unused alternate takes remain under
`/tmp/studsup-site-20260916/`. To refresh, take another isolated snapshot rather
than running the game or generators in its actively edited checkout.

## Content and validation

Copy is based on the game's `README.md`, `PROJECT.md`, and
`steam/store/description.md`. Release date, price, store availability and
multiplayer availability are not claimed.

The page works as static HTML without JavaScript; screenshots link to their
originals. JavaScript enhances them with a native dialog, arrow-key navigation,
Escape to close and browser-managed focus return. The site has no third-party
scripts or remote fonts.

Run the main repository's HTML and asset checks before deployment. Browser checks
cover desktop and mobile layouts, image loading, the catalogue card, thumbnail
selection, screenshot navigation and keyboard focus.
