<!-- Copilot / AI agent instructions for Feria-tecnologia-drones-2026 -->
# Copilot instructions — Feria Tecnológica de Drones 2026

Purpose: short, actionable guidance so an AI coding agent can be productive immediately in this repository.

- **Big picture**: This is a small static website (single-page) built with plain HTML and CSS plus Bootstrap CDN. Primary files are `feria.html` (the page markup) and `styles.css` (site styles). Images and screenshots are stored under `img/Img/` and `capturas/`.

- **Key files and patterns**:
  - `feria.html`: single entry HTML file. Uses Bootstrap classes heavily (navbar, cards, grid). Note the hero section uses an inline `style` background that currently contains absolute local file paths. Example: the hero `style` includes `/Users/luisgracia/.../img/Img/smboro-...jpg`.
  - `styles.css`: small, focused stylesheet. Cards rely on `.card-img-top` fixed height + `object-fit: cover`.
  - `img/Img/`: image assets; filenames are used directly from `feria.html`.

- **Project-specific quirks** (important to preserve/fix):
  - Image references in `feria.html` are absolute system paths (e.g. `/Users/luisgracia/.../img/Img/xxx.jpg`). Convert these to relative paths (`img/Img/xxx.jpg`) before publishing or testing on another machine.
  - The images folder name uses mixed capitalization (`img/Img`) — be careful on case-sensitive filesystems.

- **Developer workflows** (how to run/preview and common edits):
  - No build system or tests. To preview locally run a simple static server from repository root:

    python3 -m http.server 8000

  - Or open `feria.html` directly in a browser for quick edits. Using VS Code Live Server is also appropriate.

- **When editing**:
  - Keep HTML structure in `feria.html` and avoid breaking Bootstrap class names. If adding JS, include it via a new script file and reference it at the end of the body.
  - Prefer relative image paths. Example replacement for the hero section:

    style="background: linear-gradient(rgba(0,0,0,0.6), rgba(0,0,0,0.6)), url('img/Img/smboro-ytoKYKF-9Os-unsplash.jpg') center/cover no-repeat;"

- **External integrations**:
  - Bootstrap CSS/JS are loaded from jsDelivr CDN (version 5.3.3). No other package manager or runtime is present.

- **PR / commit guidance for agents**:
  - Small atomic changes only (fix a relative path, adjust CSS rule, add a missing image). When adding images, place them under `img/Img/` or `capturas/` and reference relatively.
  - If you change image paths, update every `src` and inline `style` that references them.

- **Searchable examples to consult**:
  - `feria.html` — hero background, cards with `card-img-top` and absolute image paths.
  - `styles.css` — hover effect for `.card` and fixed image sizing for `.card-img-top`.

If any section above is unclear or you want more detailed rules (naming, compression, CI steps), tell me which area to expand.
