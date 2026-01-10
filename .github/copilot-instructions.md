# Copilot / AI assistant instructions for this repo

This repository is a simple static website (Start Bootstrap "Agency" theme) modified for a school. Provide focused, actionable changes only — avoid sweeping refactors.

- **Big picture:** single-page static site. Core files: [index.html](index.html), [css/styles.css](css/styles.css), [js/scripts.js](js/scripts.js). Assets live under `assets/` (images in `assets/img/`). The site uses Bootstrap 5, Font Awesome, Google Fonts and StartBootstrap SB Forms via CDNs.

- **What you can assume:** no build system, no package manager, no tests. Changes are live by editing HTML/CSS/JS and deploying static files. Recommend simple local preview via `python -m http.server` or the VS Code Live Server extension.

- **Key patterns & conventions (concrete examples):**
  - Navigation/scrollspy: the navbar id is `mainNav` and ScrollSpy is initialized in [js/scripts.js](js/scripts.js). Use `#mainNav` and `data-bs-*` attributes to integrate with Bootstrap JS.
  - Portfolio items: add a `.col-...` block under the section with id `portfolio` and a corresponding modal `#portfolioModalN` (see existing `portfolioModal1`..`portfolioModal6` in [index.html](index.html)). Keep modal IDs unique.
  - Contact form: the form uses StartBootstrap SB Forms. The form element has `data-sb-form-api-token="API_TOKEN"` — replace with a real token from https://startbootstrap.com/solution/contact-forms to activate. The submit button is initially disabled via the `disabled` class.
  - Theme: `css/styles.css` contains Bootstrap + theme styles (large single-file). Small visual changes can be made there; for larger edits prefer adding small new CSS rules rather than restructuring the file.

- **Integration points / external dependencies:**
  - Bootstrap JS bundle: included via CDN (Bootstrap 5.2.3). Avoid changing to a different major Bootstrap version unless updating JS and CSS together.
  - Font Awesome and Google Fonts: loaded via CDN in head — edits should preserve these links unless intentionally swapping assets.
  - SB Forms: script at bottom of `index.html` — site depends on their API for form submissions.

- **Developer workflows / quick commands:**
  - Preview locally: `python -m http.server 8000` then open `http://localhost:8000/index.html`.
  - Quick edits: small HTML/CSS/JS changes — no build step required; reload browser to see changes.
  - Deploy: copy the repo contents to any static host (GitHub Pages, Netlify, Vercel static site).

- **When editing, prefer minimal, reversible changes:**
  - Keep IDs, data attributes, and modal naming consistent.
  - When adding images, place them under `assets/img/` and reference relatively (e.g., `assets/img/portfolio/7.jpg`).
  - If modifying `css/styles.css`, append small rules at the end to avoid conflicts with the bundled stylesheet.

- **Examples of common tasks:**
  - Add a new portfolio item: copy one `.col-lg-4` portfolio block in the `#portfolio` section and create a matching `#portfolioModal7` modal below the footer.
  - Update navbar links: edit the `<ul>` under `#mainNav` in [index.html](index.html) and ensure corresponding section ids exist.
  - Enable contact form: register at StartBootstrap contact-forms, set the form `data-sb-form-api-token` to the provided token, remove the disabled state from the submit button if needed.

- **Do NOT:**
  - Introduce a JS framework (React/Vue) or a build system without prior approval — this repo is intentionally static.
  - Reformat or split `css/styles.css` unless requested; it's a bundled theme file and large diffs are noisy.

If anything in these instructions is unclear or you'd like more detail (for example, a recommended static deploy workflow or small refactor to split styles), tell me what to expand and I will iterate.
