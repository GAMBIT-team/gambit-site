# projectgambit.org

Public landing page for **GAMBIT** (Guided AI for Magnetic Boride/Carbide
Intermetallic Technologies), an ARPA-E MAGNITO project.

Pure static HTML/CSS with no build step or dependencies. Hosted on GitHub Pages
from the `main` branch; every push publishes within about a minute.

## Publishing a news post

1. Copy `news/_template.html` to `news/YYYY-MM-short-slug.html`.
2. Edit everything marked `TODO` in the file (title, date, body).
3. Add the post's `<article class="news-item">` card to the top of the list in
   `news/index.html` (the template has instructions).
4. Optionally feature it on the homepage: the News section in `index.html`
   uses the same card format.
5. Commit and push to `main`.

## Team headshots

Roster photos live in `assets/img/team/` as square JPGs (480x480 or larger),
one per person. To replace one, overwrite the file with the same name and push.

## Local preview

```sh
python3 -m http.server 8000
# then open http://localhost:8000
```

## Repo layout

```
index.html          landing page
news/               news archive, posts, and _template.html
assets/css/site.css single stylesheet (design tokens at the top)
assets/fonts/       self-hosted webfonts (Clash Display, Archivo)
assets/img/         logo, team photos, and favicon
CNAME               custom-domain marker for GitHub Pages
_config.yml         keeps internal docs out of the published site
```

## Content policy

Program-level, public information only. No funding figures, performance
targets, or proposal content.
