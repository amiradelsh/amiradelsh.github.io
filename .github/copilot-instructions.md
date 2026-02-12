<!-- Copilot / AI agent instructions for contributors working on this Jekyll site -->
# Copilot instructions — al-folio Jekyll site

Purpose
- Help AI coding agents become productive quickly in this repository (a Jekyll-based al-folio site).

Big picture
- This is a static site built with Jekyll (see `Gemfile`) using the al-folio theme layout. Key runtime pieces:
  - Configuration: `_config.yml`
  - Templates: `_layouts/` and `_includes/`
  - Content: `_posts/`, `_pages/`, and `assets/`
  - Data & citations: `_data/` and `_bibliography/papers.bib` (uses `jekyll-scholar`)
  - Custom Ruby plugins: `_plugins/` (e.g., `terser.rb`, `cache-bust.rb`) — these change site build behavior and run inside Jekyll.
  - Styling: `_sass/` and `purgecss.config.js` (CI runs a purge step).

Developer workflows (explicit)
- Local development (observed in container/terminal):
  - Start live server: `jekyll serve --port 8080 --livereload`
  - If using Bundler (recommended):
    - `bundle install`
    - `bundle exec jekyll serve --livereload --port 8080`
- Docker: use the provided images via `docker-compose.yml` or `docker-compose-slim.yml`:
  - `docker-compose up --build` or `docker-compose -f docker-compose-slim.yml up`
- CI / Production build (see `.github/workflows/deploy.yml`):
  - CI installs Ruby gems, runs `bundle exec jekyll build` with `JEKYLL_ENV=production`.
  - CI also runs `purgecss -c purgecss.config.js` (requires Node/npm) and installs system deps like `imagemagick` and `nbconvert`.
  - Do not change build steps without updating `.github/workflows/deploy.yml`.

Project-specific conventions and patterns
- Front matter & content:
  - Posts live in `_posts/` and follow Jekyll front-matter (title, date, tags, categories). Example: `_posts/2024-01-27-code-diff.md`.
  - Pages are in `_pages/` and use layout templates under `_layouts/`.
- Custom plugins: `_plugins/` contains Ruby plugins that alter build output. Examples: `hide-custom-bibtex.rb`, `terser.rb`.
  - Editing these affects site generation; run `bundle exec jekyll build` locally to validate.
- Bibliography & citations:
  - Bibliography stored at `_bibliography/papers.bib` and consumed via `jekyll-scholar` and template includes like `citation.liquid`.
- Asset processing:
  - JS/CSS may be minified or purged in CI. Avoid manual removal of assets referenced by templates; check `_includes/scripts.liquid` and `_layouts` for usage.

Integration points & external dependencies
- Ruby gems: declared in `Gemfile` — changes require `bundle install` and affect CI.
- Node tooling: `purgecss` used in CI via `purgecss.config.js` (global `npm install -g purgecss` in CI). Prettier plugin configured via `package.json` devDependencies.
- CI actions: `.github/workflows/deploy.yml` (build & deploy) and `.github/workflows/broken-links.yml` (link checking using `lycheeverse/lychee-action`).

Editing guidance for AI agents
- When modifying templates, update only the specific partial in `_includes/` or the layout in `_layouts/` unless a site-wide change is needed.
- When changing Ruby plugins in `_plugins/`:
  - Run `bundle exec jekyll build` locally to catch Ruby errors.
  - Keep changes minimal and preserve plugin interfaces used by templates and other plugins.
- When adding/removing assets:
  - Ensure references are updated in `_layouts/` or `_includes/` and consider effects on `purgecss` (CI may remove unused CSS).
- When updating bibliography or citation usage, validate rendered pages locally because `jekyll-scholar` output is not obvious from markdown alone.

Quick file references (examples to inspect)
- `_config.yml` — site configuration & variables
- `_plugins/` — custom build plugins (Ruby)
- `_layouts/` and `_includes/` — templates and reusable components
- `_posts/` and `_pages/` — content to edit
- `_data/` and `_bibliography/papers.bib` — structured data and citations
- `.github/workflows/deploy.yml` — CI build steps

If unsure
- Prefer small, reversible changes and run a local build. Provide a short PR description explaining why the change is needed and how it was validated (local build command and example page).

Questions for repo owner
- Any conventions not detectable in code (preferred authoring workflow, extra CI steps, or exclusions to avoid)?

End.
