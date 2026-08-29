# AGENTS.md

Static portfolio for Logan Tolbert (logan-tolbert.com). Vanilla HTML/CSS/JS, no framework, no `package.json`, no local build/test/lint tooling. The repo root IS the source of truth; CI produces the deployable `dist/` and deploys it.

## Workflow
- Work on `dev`. `main` is deploy-only: a push to `main` triggers the GitHub Actions workflow at `.github/workflows/deploy.yml`, which copies `assets/`, `pages/`, `index.html`, `CNAME` into `dist/`, minifies the 5 CSS files (clean-css), optimizes images (imagemin), runs a **non-failing** lychee link check, and deploys to GitHub Pages (`www.logan-tolbert.com` per `CNAME`).
- Commit messages use gitmoji prefixes (✨ feature, 🎨 styling, 🐛 fix).
- To verify locally, open the HTML files in a browser or serve the repo; the lychee link check in CI is the only automated gate and it never fails the build.

## Structure & conventions
- **No templating.** The header nav and footer are copy-pasted into all 4 pages (`index.html`, `pages/about.html`, `pages/contact.html`, `pages/contact-success.html`). Editing navigation or footer means updating every page by hand. Asset references are relative per page: `./assets/...` at root, `../assets/...` in `pages/`.
- **CSS:** `assets/styles/tokens.css` holds the design tokens (role-semantic CSS custom properties: surfaces, text, accent, spacing/type scales). `assets/styles/components.css` holds shared components (navbar, buttons, cards, footer) and is linked on every page. Each page has its own stylesheet (`index.css`, `about.css`, `contact.css`) linked alongside `tokens.css` and `components.css` — every page links exactly 3 stylesheets. Add a page-specific file when adding a page; keep shared styles in `components.css` and new tokens in `tokens.css`. Page files should reference semantic tokens, never magic values.
- **JS:** `script.js` is loaded on every page (mobile nav toggle, scroll-reveal animations, footer year). `contact-form.js` is contact.html only: it POSTs the form to the Formspree endpoint in `contact.html` and redirects to `contact-success.html` on success.
- `dist/` is a CI artifact, never committed. Project images live in `assets/images/`.

## Agent skills

### Issue tracker

Issues and specs live as markdown files under `.scratch/<feature>/` in this repo. See `docs/agents/issue-tracker.md`.

### Triage labels

Five canonical triage roles, each label string equal to its name: `needs-triage`, `needs-info`, `ready-for-agent`, `ready-for-human`, `wontfix`. See `docs/agents/triage-labels.md`.

### Domain docs

Single-context: one `CONTEXT.md` + `docs/adr/` at the repo root. See `docs/agents/domain.md`.