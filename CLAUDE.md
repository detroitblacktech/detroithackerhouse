# CLAUDE.md

This file provides guidance to Claude Code (claude.ai/code) when working with code in this repository.

## Project Overview

Static HTML/CSS website for the Detroit Hacker House, a residential startup pre-accelerator. Deployed via GitHub Pages at `detroithackerhouse.com` (configured in `CNAME`).

## Development

No build system or package manager. Open HTML files directly in a browser or use any static file server:

```sh
# Quick local server (Python)
python3 -m http.server 8000

# Or with Node (if available)
npx serve .
```

## Architecture

Pure static site — no frameworks, no preprocessors, no JavaScript beyond Google Analytics.

**Pages:**
- `index.html` — Main homepage (hero video, program info, team, contact/apply)
- `events.html` — Upcoming events listings
- `live-inn-play.html` — LIPH (Live Inn Play) residency program details
- `media.html` — Press coverage and media features

**Styling:**
- `styles.css` — Single stylesheet for the entire site. Uses CSS custom properties for the design system:
  - Colors: Navy `#1B4D4A`, Teal `#57b9a8`, Gold `#F5A623`
  - Font: Plus Jakarta Sans (loaded from Google Fonts)
  - Component classes: `.btn`, `.card`, `.container`, `.section-tag`, etc.
  - Includes responsive breakpoints and a JavaScript-free mobile menu (requires inline JS in each HTML file)

**External services (hardcoded in HTML):**
- Cloudinary — image and video asset hosting
- Google Analytics — tracking ID `G-GM35TMQMR8`
- Mailchimp — email list verification/embed

**Archived site:**
The `/archived-site/` directory contains the previous Bootstrap-based design. It is not linked from the live site and exists for reference only.

## Deployment

Pushing to the `main` branch on GitHub automatically deploys via GitHub Pages. No CI/CD pipeline is configured.
