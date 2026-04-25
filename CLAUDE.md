# CLAUDE.md

This file provides guidance to Claude Code (claude.ai/code) when working with code in this repository.

## What this is

Jekyll site for the **IMPSY** (Intelligent Musical Prediction System) project, deployed to GitHub Pages at `https://cpmpercussion.github.io/impsy-homepage`. The site is a small marketing-free landing zone for researchers and music technologists who want to adopt or adapt IMPSY — see `README.md` for the editorial brief.

## Commands

```bash
bundle install                  # install Ruby gems (first run / Gemfile changes)
bundle exec jekyll serve        # local preview at http://localhost:4000/impsy-homepage/
bundle exec jekyll build        # one-shot build into _site/
```

`_config.yml` is **not** reloaded by `jekyll serve` — restart the server after editing it.

## Deploy

Pushes to `main` trigger `.github/workflows/pages.yml`, which builds with `actions/jekyll-build-pages` and publishes via `actions/deploy-pages`. The repo is **not** using the legacy `github-pages` gem — Jekyll runs at the version pinned in `Gemfile`. The workflow injects `--baseurl` from `actions/configure-pages`, so the static `baseurl: "/impsy-homepage"` in `_config.yml` is for local builds.

For Pages to pick up the workflow, the repo's *Settings → Pages → Source* must be set to **GitHub Actions** (not "Deploy from a branch").

## Architecture

- **Pages are top-level `.md` files** with explicit `permalink:` (`index.md`, `get-started.md`, `research.md`, `gallery.md`, `404.html`). There is no `_posts/` directory and no blog — this is intentional per the brief; do not reinstate it.
- **Layouts** live in `_layouts/`: `default.html` is the shell (Bootstrap 5 CDN, SEO tag, theme bootstrapper); `home.html` is a thin wrapper used by `index.md` so the hero can use bespoke markup; `page.html` is the standard article wrapper used by all content pages.
- **Includes** in `_includes/`: `header.html` (nav driven by `site.nav` in `_config.yml`, plus the theme toggle button) and `footer.html` (driven by `site.links`).
- **Styling**: `assets/css/main.scss` (front-matter triggers Jekyll SCSS compilation to `main.css`). Bootstrap loads via CDN; the SCSS adds an accent palette, hero, workflow cards, timeline, publication list, and gallery grid. Component CSS classes used in markdown — `hero`, `workflow-step`, `timeline`, `pub-list`, `gallery-grid`, `video-grid`, `btn-impsy` — are defined here.
- **Theme switching**: `assets/js/theme-toggle.js` cycles auto → light → dark, persists to `localStorage`, and writes `data-bs-theme` on `<html>`. An inline script in `_layouts/default.html` applies the stored choice before paint to prevent FOUC. Both scripts must agree on the storage key (`impsy-theme`).
- **SEO/discovery**: `jekyll-seo-tag` reads each page's `title`, `description`, and `image` front matter to emit Open Graph, Twitter, and JSON-LD. Always set these on new pages. `jekyll-sitemap` generates `sitemap.xml` using `site.url` + `site.baseurl`.

## Editorial conventions (from README)

- Voice is research-oriented NIME-community, not marketing. Link to source code and papers rather than describing them in promotional terms.
- Images come from the paper repositories under `cpmpercussion/*` (mainly `impsypi-opening-design-space-paper/figures/`). Don't introduce stock photos or generated graphics.
- Keep the site to a small set of clearly-written pages. Long-form news belongs on `charlesmartin.au` or `smcclab.au`, both linked in `_config.yml` under `site.links`.

## Adding a new page

1. Create `<slug>.md` at the repo root with `layout: page`, `title:`, `subtitle:` (optional), `permalink: /<slug>/`, and `description:` (used by SEO).
2. Add an entry to `nav:` in `_config.yml` to surface it in the header.
3. Reuse existing component classes from `main.scss` before adding new ones.
