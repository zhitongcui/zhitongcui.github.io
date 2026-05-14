# CLAUDE.md

This file provides guidance to Claude Code (claude.ai/code) when working with code in this repository.

## Overview

A static personal CV/portfolio website. No build step — open `index.html` directly in a browser to preview.

## Architecture

- `cv.md` — source of truth for all personal content (bio, publications, contact info). Written in a mix of Chinese and English.
- `index.html` — hand-authored HTML derived from `cv.md`. The two files must stay in sync manually; there is no generator.
- `styles.css` — all styling. Uses CSS custom properties defined in `:root` for the color palette and two font stacks (`--font-body`: Source Sans 3 / Noto Sans SC; `--font-display`: Merriweather).
- `avatar.jpg` — profile photo referenced directly in `index.html`.

## Content update workflow

When updating publications or bio text:
1. Edit `cv.md` first (it is the canonical record).
2. Mirror the change into the corresponding section of `index.html`.

Publications in `index.html` are grouped into `<article class="pub-group">` blocks, each with a `.group-kicker` label, a Chinese-language theme heading (`<h3>`), and one or more `.paper` divs. Match this structure when adding entries.

## Deployment

Push to the `main` branch root of a GitHub repository; GitHub Pages serves `index.html` as the site root.
