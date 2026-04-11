# CLAUDE.md

This file provides guidance to Claude Code (claude.ai/code) when working with code in this repository.

## Project Overview

Static marketing website for the **InMyEyes iOS app**, owned by Jofi Creations AB. No build tools, package managers, or frameworks — pure HTML/CSS/JS served directly.

## Development

Serve locally with any static HTTP server:

```bash
python -m http.server 8000
```

Then open `http://localhost:8000` in a browser. No build step required.

## Architecture

The site is **bilingual (Swedish/English)** with separate HTML files per language:

- `index.html` / `index-en.html` — landing pages
- `privacy.html` / `privacy-en.html` — privacy policies

Language switching is implemented as plain `<a href>` links to the alternate file. All CSS and JavaScript are embedded directly in each HTML file (no external JS/CSS files).

Screenshots live in `screenshots/` (Swedish) and `screenshots-en/` (English, currently empty).

## Key Implementation Details

**Canvas animation**: The paw print animation (`#pawCanvas`) uses `requestAnimationFrame` with a 4-beat diagonal walk gait (RF→LH→LF→RH) and sine wave trajectory. It is defined at the bottom of the `<script>` block in each HTML file.

**Styling**: CSS custom properties define a warm/earthy color palette. Visual effects include a paper grain overlay (SVG `feTurbulence` filter as a data URI), skewed iPhone mockups with Dynamic Island rendering, and tape effects on quote cards.

**App Store links**: Currently placeholder `#` links — need to be updated with real App Store URLs when the app is published.
