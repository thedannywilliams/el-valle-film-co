# CLAUDE.md — El Valle Film Co. site

Auto-loaded by Claude Code when run in this folder.

## What's here

- `index.html` — home page (hero, About, Films, Team)
- `contact.html` — contact page with Netlify form
- `brownie-still.jpg` — film still used on the Brownie card in the Films section

Single-page-each, no build step. All CSS/JS inline.

## Design system (current)

- **Dark cinematic palette** (Caribbean dusk): `--paper: #100b08` background, `--ink: #f2eadc` cream type, `--red: #E2402E` terracotta accent
- **Type**: Fraunces (italic body), Archivo (sans), Archivo Black (display caps), JetBrains Mono (labels), Allura (cursive V mark)
- **Display headlines**: Archivo Black uppercase — section titles + film titles. Red emphasis = `<em>` (no italic in display caps).
- **Top strip**: "An El Valle Ventures Company" mono caps fixed across the top of every page
- **Films section**: 3 cards, 16:9 stills, image-left + meta-right on desktop, stacked on mobile
- **Contact form**: Netlify Forms — needs `data-netlify="true"` to stay on the form for Netlify to detect on deploy; AJAX submit replaces form with inline confirmation

## Live preview

Pointed at `/tmp/el-valle/` on port 4324 (launch.json name: `el-valle`). When iterating, edit files here, then copy to `/tmp/el-valle/` to preview. `python3 -m http.server` can't serve from `~/Desktop` reliably due to macOS sandbox — always preview from `/tmp/el-valle/`.

## Deploy (Netlify)

1. Drag this folder onto https://app.netlify.com/drop
2. After first deploy: Forms tab → enable email notifications for the contact form
3. Suggested domain: `elvallefilmco.com`

## Outstanding

- Vandal + Divinity stills are empty 16:9 placeholders (show a faint X cross). Drop in `vandal-still.jpg` and `divinity-still.jpg` to fill — same `<img>` pattern as the Brownie card.
- No favicon yet (add `<link rel="icon" ...>` in both files)
- No `og:image` for social shares
