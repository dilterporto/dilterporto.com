# CLAUDE.md

This file provides guidance to Claude Code (claude.ai/code) when working with code in this repository.

## Overview

This is a static personal website for dilterporto.com. The entire site lives in a single self-contained `index.html` — no build step, no framework, no dependencies.

## Development

To preview locally, open `index.html` directly in a browser or serve it:

```bash
python3 -m http.server 8080
```

## Deployment

The site is deployed via GitHub Pages at `dilterporto.com`. Push to `main` and GitHub Pages serves from the repo root. See `DEPLOY.md` for the full DNS/HTTPS setup.

## Architecture

- All HTML, CSS, and any future JS lives in `index.html` (inline styles, no external stylesheets).
- CSS custom properties are defined in `:root` — use them when adding styles (`--bg`, `--text`, `--muted`, `--accent`, `--border`, `--max`).
- Blog posts are separate HTML files placed under `posts/`. The index page links to them via `.post-item` anchors inside `<section id="blog">`. A commented-out template is already in `index.html`.
- The site is in Brazilian Portuguese (`lang="pt-BR"`).
