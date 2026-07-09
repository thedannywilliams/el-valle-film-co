# CLAUDE.md — El Valle Studios site (elvallestudios.com)

Auto-loaded by Claude Code when run in this folder.

## What's here

- `index.html` — home page (hero, About, Films, Team, Contact form). ~1MB: several images are inlined as base64 (palm silhouettes, filmmaker figure, V watermark, BTS photo)
- `contact.html` — standalone contact page (NOT linked from the homepage nav — the homepage has an in-page contact form; keep contact.html styled in sync anyway since it's reachable by URL)
- `daniel-portrait.jpg`, `brownie-still.jpg`, wordmark/favicon assets

Single-page-each, no build step. All CSS/JS inline.

## Design system (light studio redesign, 2026-07)

- **LIGHT studio palette** (flipped from the old dark cinematic look — do not reintroduce dark backgrounds): `--paper: #f2eadc` warm cream bg, `--ink: #171009` near-black warm brown type, `--red: #E2402E` brand red accent, `--paper-deep: #0d0805` reserved for the fixed "An El Valle Ventures Company" strip
- **Hero**: giant edge-to-edge typographic wordmark — "EL VALLE" / "STUDIOS." stacked in Archivo Black with a red period, sized via `calc(…vw - …px)` so BOTH lines fill the container width exactly (Archivo Black @100px: "EL VALLE" ≈ 528px, "STUDIOS." ≈ 533px — retune these calcs if the text or tracking changes). Inspired by neonrated.com / wmeagency.com. Static for now — motion comes later
- **Type**: Fraunces (serif italic accents), Archivo (sans), Archivo Black (display caps), JetBrains Mono (labels), Allura (cursive V)
- **Texture**: fine ink-noise paper grain via `body::before` (multiply, 5%). The old dark vignette was removed
- **Palm/filmmaker art**: source PNGs are black ink — they sit directly on cream with only a slight sepia warm filter (no `invert()`)
- Red emphasis in display caps = `<em>` (no italic). Spanish flourishes use `.es` (Fraunces italic red)
- **Contact form**: Netlify Forms — keep `data-netlify="true"`; AJAX submit swaps in inline confirmation

## Live preview

launch.json name `el-valle` serves `/tmp/el-valle/` on port 4324. Edit here, then `cp` changed files to `/tmp/el-valle/` (macOS sandbox blocks serving from ~/Desktop).

## Deploy

**Auto-deploy connected (2026-07-07):** GitHub `thedannywilliams/el-valle-film-co` → Netlify. Workflow = commit + push; no manual drag-and-drop.

## Outstanding

- Hero is static — user plans motion/video later
- Film cards (Brownie, Conspiracy Theory) currently have no stills on the homepage
