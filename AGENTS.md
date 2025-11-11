# Repository Guidelines

## Project Structure & Module Organization
- `content/` holds Markdown sources; organize long-form posts under `content/posts/` and section pages (e.g. `categories/`, `podcasts.md`) at the root.
- `static/` exposes assets verbatim (images, favicons); prefer placing new media under `static/img/`.
- `archetypes/` stores front-matter templates; extend these when adding new content types.
- `resources/` and `public/` are Hugo build outputs—never edit them manually.
- `themes/LoveIt/` contains the upstream LoveIt theme; keep local tweaks isolated to avoid merge conflicts.

## Build, Test, and Development Commands
- `hugo server -D` launches the live-reload dev server and includes drafts; visit `http://localhost:1313`.
- `hugo` builds the site into `public/`; run with `--gc --minify` before deployment to clean unused assets.
- `hugo new posts/<slug>/index.md` scaffolds a new post directory with TOML front matter.

## Coding Style & Naming Conventions
- Write content in Markdown with TOML front matter (`+++`) to match existing pages.
- Use descriptive, dash-separated slugs (`recipes-kombu-dashi`) and keep titles in Title Case.
- Keep paragraphs short (<6 sentences) and prefer fenced code blocks for formulas or snippets.
- Run `hugo fmt` (from Hugo 0.123+) when editing configuration to normalize TOML formatting.

## Testing Guidelines
- Treat a clean `hugo server` console (no WARN/ERROR) as the baseline quality check.
- Manually verify that generated pages render math, images, and shortcodes correctly.
- Use browser dev tools to confirm static assets resolve under their `static/` paths.

## Commit & Pull Request Guidelines
- Follow the existing short, imperative commit style (`add recipe`, `update e1`); keep the subject ≤50 characters.
- Reference related issues in the body when applicable and explain visible changes or new content.
- For pull requests, include screenshots or local URLs for layout updates, and note any draft content toggles.

## Content Authoring Tips
- Store shared figures in `static/img/` and reference them via `/img/<file>` paths.
- Enable drafts by adding `draft = true` while iterating, then flip to `false` once reviewed.
- Leverage LoveIt shortcodes (`{{< image >}}`, `{{< admonition >}}`) for richer layouts without custom HTML.
