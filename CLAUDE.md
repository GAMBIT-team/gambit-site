# CLAUDE.md

Guidance for Claude Code when working in this repository.

## What this is

The public landing page for **GAMBIT** (Guided AI for Magnetic Boride/Carbide Intermetallic Technologies), an ARPA-E MAGNITO project led by the University of Houston with Rice University, Colorado State University, and Newfound Materials. Live at https://projectgambit.org, served by GitHub Pages from `main`. Every push to `main` publishes within about a minute, so treat `main` as production.

Pure static HTML and CSS. No build step, no package manager, no JavaScript framework. Preview with `python3 -m http.server 8000`.

## Layout

```
index.html            landing page (sections: hero, approach, team, market, news, contact)
news/index.html       news archive
news/_template.html   copy this for a new post; edit everything marked TODO
news/YYYY-MM-slug.html  individual posts
assets/css/site.css   the single stylesheet; design tokens live at the top
assets/fonts/         self-hosted Public Sans (variable, upright + italic)
assets/img/           logo, favicons, institution marks, team headshots
CNAME, _config.yml    GitHub Pages config; leave alone
```

The related project document library (proposal, milestones, meeting notes, marketing assets) lives in the GAMBIT SharePoint/OneDrive folder, not in this repo.

## Typography: one family, Public Sans

**Public Sans is the only typeface on the site**, for headings and body alike. This was decided on 2026-09-03 to unify the website with GAMBIT slides and documents, which use the same family. Do not add a second face.

- Both CSS tokens, `--display` and `--body`, resolve to `"Public Sans"`. Keep using the tokens rather than writing font-family literals.
- The font is self-hosted in `assets/fonts/` as two variable woff2 files (weight axis 100 to 900, upright and italic), declared with `@font-face` at the top of `site.css`. Do not link Google Fonts or any other font CDN.
- Display roles (hero title, section titles, roster names, nav brand) use weights 600 to 800; body runs at 400 to 550. Public Sans is lighter than the display face it replaced, so do not thin display weights below 600.
- Headings are sentence case. Never set a heading, eyebrow, or label in all caps, whether typed or via `text-transform: uppercase`. The nav links still use uppercase from the original build; if you touch that rule, convert it to sentence case rather than extending it.

## Design tokens and style

- Colors and the gradient are CSS custom properties in `:root` at the top of `site.css`. Use them; do not introduce new literal colors.
- The site was built as a dark, gradient-accented design. For new work, prefer solid colors from the token set over additional gradients, and keep the existing gradient usage contained rather than spreading it.
- No inline styles in HTML except for SVG geometry that already lives inline.

## Content policy

Program-level, public information only. Do not publish funding figures, performance targets, milestone specifics, candidate chemistries, or anything from the proposal. Team bios stay to title, institution, and one-line focus. When in doubt, leave it out; the internal document library is where detail belongs.

## Editing conventions

- Team headshots are square JPGs, 480x480 or larger, in `assets/img/team/`, named by surname. Replace by overwriting the file with the same name.
- New news posts: copy `news/_template.html`, fill the TODOs, add the card to `news/index.html`, and optionally feature it on the homepage News section.
- Commit only when asked. Do not push to `main` without explicit confirmation, since that deploys the site.
