# CLAUDE.md

This file provides guidance to Claude Code (claude.ai/code) when working with code in this repository.

## Project Overview

Static single-page marketing website for K12 AI Lab, a Turkish-language academic consultancy offering AI and Data education programs for K-12 schools in Istanbul, Turkey.

## Project Structure

Zero-build-step static website. The entire site lives in a single file:

- `index.html` — Complete website (HTML + inline CSS + inline JS, ~1,300 lines)
- `BilimYZ_Tanitim_Brosuru.pdf` — Company brochure (Turkish)
- `Bilim_ve_YZ_Enstitusu_Is_Plani.pdf` — Business plan document (Turkish)

## Technology

Pure HTML5, CSS3, Vanilla JavaScript — no framework, no build toolchain. Fonts via Google Fonts (Playfair Display, Outfit, JetBrains Mono). Hosted on Cloudflare with email obfuscation.

## Development

No build step. Serve locally and reload:

```bash
python3 -m http.server 8080
```

## Language

All user-facing content is in **Turkish**. Code-level naming (CSS classes, JS) is in English.

## Architecture Notes

- All styles are inline in `<style>` tags within `index.html`
- All JavaScript is inline at the bottom of `index.html`
- JS uses IntersectionObserver for scroll-triggered fade-up animations, mobile menu toggle, and smooth scrolling
- The contact form (`#contactForm`) is UI-only — `submitForm()` shows a success message but does not POST anywhere; a real backend needs to be wired in
- Color palette: ink blues (`#0A1628`, `#111E30`, `#1C2E45`), gold accents (`#B8922A`, `#D4AC50`, `#EDD07C`), parchment backgrounds (`#F7F3EC`, `#EEE8DC`, `#E5DDD0`)

## Deployment

Upload `index.html` and PDFs to any static host. Cloudflare is currently used.
