<div align="center">

# Lendra: Marketing Website

**A private loan management system for private lenders, presented.**

</div>

---

## What this is

This repository holds the public marketing site for **Lendra**, a closed-source, local-first loan management system. It's a static, multi-page site designed to look and feel like a premium commercial product while accurately representing a private, native desktop application. Lendra is not publicly distributed, so every "download" CTA from a typical SaaS site is replaced with a contact link instead.

Every screenshot on this site is captured from the running app using fictional demo data (made-up borrowers, loans, and amounts), never real user data.

## Pages

| Page | Purpose |
|---|---|
| `index.html` | Landing page: hero, product tour, feature grid, currencies, how it works |
| `gallery.html` | Full-size screenshot gallery of every core workspace |
| `docs.html` | Complete product guide with sticky sidebar navigation |
| `changelog.html` | Version history and release notes |
| `about.html` | Why Lendra exists, its principles, honest limitations, and contact |
| `privacy.html` | Privacy policy |
| `terms.html` | Terms of service |

## Tech

No framework, no build step, no package manager. Just:

- **HTML5**: one file per page, shared header/footer markup
- **Plain CSS** (`assets/css/main.css`): design tokens matching the Lendra brand (petrol `#0B4A52`, paper `#F7F4EE`, petrol-mint accent `#5FC7CE`), dark mode via `prefers-color-scheme` + manual toggle
- **Vanilla JavaScript** (`assets/js/main.js`): theme toggle, scroll-reveal animations, mobile nav, page-transition fade, docs TOC scroll-spy, docs search, obfuscated contact link
- **Google Fonts**: Instrument Sans (display) + Hanken Grotesk (body) + IBM Plex Mono

Open any `.html` file directly in a browser, or serve the folder with anything static (`npx serve`, `python -m http.server`, Vercel, Netlify, GitHub Pages). There is nothing to install and nothing to compile.

## Project structure

```
.
├── index.html, gallery.html, docs.html,
│   changelog.html, about.html, privacy.html, terms.html
├── assets/
│   ├── css/main.css           Shared design system
│   ├── js/main.js             Shared behavior
│   ├── screenshots/           Captures from the Lendra app (fictional demo data)
│   ├── lendra-logo.svg        Vector brand mark (used in nav/footer)
│   └── lendra-logo.png        Raster logo (favicon/OG fallback)
├── robots.txt
└── sitemap.xml
```

## Keeping this site honest

This site only advertises features that are actually shipped in the Lendra app, sourced directly from its README and in-app docs, including an explicit "What Lendra Doesn't Do" section on the About page. When the product changes:

- **Screenshots**: recapture from the running app with fictional demo data (never real borrower/loan records) and drop the updated PNGs into `assets/screenshots/`, replacing the old files with the same names.
- **Feature copy**: cross-check against the app's own README/docs before adding a claim to the feature grid or hero.
- **Contact**: the site has no download flow by design. The "Get in Touch"/"Contact" links use an obfuscated email (base64-encoded in `data-mail`, decoded client-side on click, so it's not plaintext-scannable in the page source); the About page's creator card links out to a personal profile site instead.

## Deployment

This site can be deployed on [Vercel](https://vercel.com) as a static site with zero build configuration.
