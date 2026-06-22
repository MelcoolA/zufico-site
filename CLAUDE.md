# CLAUDE.md

This file provides guidance to Claude Code (claude.ai/code) when working with code in this repository.

## Project Overview

Zufico is a static single-page HTML website for a home essentials brand. There is no build system, package manager, or JavaScript framework — everything lives in `index.html`.

## Development

To preview locally, open `index.html` directly in a browser or use any static file server:

```bash
python3 -m http.server 8000
# or
npx serve .
```

## Architecture

**Single file**: All HTML structure, CSS (~450 lines in a `<style>` tag), and JavaScript (~7 lines) are in `index.html`.

**Navigation**: Anchor-based (`#kitchen`, `#household`, `#beauty`, `#decor`, `#car`, `#about`, `#contact`). Sticky nav with a mobile hamburger menu toggled via `classList.toggle('open')`.

**Product images**: Stored in `pics/<category>/` subdirectories (`beauty/`, `car/`, `health/`, `home decore/`, `kitchen/`). Logo files are in `pics/`.

**CSS design tokens** (defined as custom properties on `:root`):
- Colors: `--bg`, `--bg-warm`, `--surface`, `--border`, `--text`, `--text-muted`, `--accent`, `--accent-hover`, `--accent-soft`
- Typography: Bricolage Grotesque (display/headings), Manrope (body) — loaded from Google Fonts
- Spacing scale: `--space-xs` through `--space-xl`

## Key Details

- All product "Buy on Amazon" links currently contain the placeholder `REPLACE_WITH_AMAZON_ATTRIBUTION_LINK` and need to be replaced with real Amazon Attribution URLs.
- The Amazon store URL is `https://www.amazon.com/stores/zufico`.
- Contact email: `info@zufico.com`.
- Product grids use CSS `auto-fill` with `minmax(240px, 1fr)` for responsive layout without media queries.
- Mobile breakpoint: `768px` (controls nav toggle, about section column layout).
