# CLAUDE.md

This file provides guidance to Claude Code (claude.ai/code) when working with code in this repository.

## Overview

This site started as a minimal static page to resolve the `dilterporto.com` domain quickly — just enough to have a presence online with basic personal info. The intent is to keep it simple and lightweight; avoid introducing build tools, frameworks, or external dependencies unless there's a clear and necessary reason.

The entire site lives in a single self-contained `index.html` — no build step, no framework, no dependencies.

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
- Blog posts are separate HTML files placed under `posts/`. The index page links to them via `.post-item` anchors inside `<section id="blog">`.
- The site supports PT-BR and EN via a lightweight JS i18n system — translatable elements use `data-i18n` attributes, strings live in the `T` object at the bottom of `index.html`, and the active language is stored in `localStorage`. The `<html lang>` attribute is set early in `<head>` to avoid a flash of the wrong language.
