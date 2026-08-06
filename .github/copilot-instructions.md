# Copilot instructions for DEVINJ

Purpose: give AI coding agents the repo context they need to be productive quickly.

- **Project type:** Single-page static website (HTML, CSS, images, minimal JS). Entry: `devinj.html`.
- **No build tool:** There is no `package.json` or build pipeline. Serve `devinj.html` directly (open in browser or run a local static server).

Key files & structure
- `devinj.html` — main page, imports `css/reset.css` and `css/style.css` and expects `js/main.js` (note: the repo's JS file is `is/main.js`, see "Paths" below).
- `css/style.css` — primary stylesheet (large, contains design tokens in `:root`).
- `css/reset.css` — reset styles.
- `asset/img/` — images and media assets.
- `is/main.js` — JavaScript file present but currently empty; HTML references `js/main.js` (path mismatch).

Important repo-specific notes (do not assume common defaults)
- This is a static site with no tests or CI configured. Avoid adding complex build steps unless the user requests them.
- The contact form uses `action="#"` and is a placeholder. Any backend integration requires adding an API endpoint and updating the form action/method.
- Fonts and icons are loaded from CDNs (Google Fonts, Font Awesome). Keep CDN usage consistent unless replacing with local assets.
- The HTML references `js/main.js` but the repo contains `is/main.js` — check and fix paths before running scripts.

Developer workflows
- Quick local preview: open `devinj.html` in a browser or run a simple static server, e.g. `python -m http.server 8000` from repo root, then visit `http://localhost:8000/devinj.html`.
- Editing styles: modify `css/style.css` and `css/reset.css`; images live under `asset/img/`.
- Adding JS: place scripts under `js/` (or update HTML to point to `is/main.js`) — be explicit about which path you choose.

Conventions & patterns to follow
- Keep assets under `asset/` and styles under `css/`.
- Use the existing CSS variables in `:root` (colors) to keep the design consistent.
- Preserve external CDN links for fonts/icons unless the change is requested.

Integration points & possible pitfalls
- Relative paths in `devinj.html` assume the file is served from repo root. If you change directory layout or host routes, update paths accordingly.
- Contact and newsletter forms are static — integration will require both frontend changes and a server endpoint.

When you modify files
- Make minimal, focused changes. This repo is small and primarily static; prefer simple fixes (path corrections, content updates, CSS tweaks) over introducing complex tooling.

If you need clarification
- Ask the repo owner about the intended script folder (`js/` vs `is/`) and whether they want a hosting or backend integration.

---
If this file existed already, merge remaining useful guidance from the prior file. After review, tell me any missing details (hosting, intended JS path, backend plans) to refine these instructions.
