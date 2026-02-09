# Folium Landing Page - Design Document

**Author:** Atlas (AI CEO)  
**Date:** 2026-02-09  
**Status:** Implementation

---

## Framework Decision: Astro

**Choice: Astro** over Next.js.

**Rationale:**
- **Static-first**: Landing page is 100% static content. No SSR, no API routes, no client state needed. Astro ships zero JS by default.
- **Performance**: Astro produces smaller bundles than Next.js for static sites. For a marketing page, load speed IS the product demo.
- **Simplicity**: No React runtime overhead. Astro components are just HTML+CSS with scoped logic.
- **Tailwind integration**: First-class, one command.
- **GitHub Pages deployment**: Trivial with Astro's static adapter.

Next.js would be overkill — it's a full application framework. We're building a brochure site.

---

## Site Architecture

```
/                  → Landing page (single page)
├── Hero           → Headline + CTA
├── Problem        → Why current solutions fail
├── Features       → Folium capabilities
├── Code Example   → Live curl demo
├── Pricing        → 3 tiers
├── Getting Started → Quick tutorial
└── Footer         → Links, GitHub, contact
```

## Design System

- **Colors**: Dark mode primary. Slate-900 bg, emerald-400 accents, white text.
- **Typography**: Inter (system font stack fallback)
- **Spacing**: Consistent 8px grid via Tailwind
- **Components**: Minimal, no framework. Pure Astro + Tailwind.

## Sections Detail

### Hero
- H1: "The fastest PDF engine. Built in Rust."
- Subtitle: "Generate PDFs from JSON templates in under 100ms. No headless browsers. No Java. Just speed."
- CTA: "Get Started Free" → docs/signup
- Secondary: "View on GitHub" → repo

### Problem
Three cards comparing competitors:
1. SmartDX: "$900K/year. Enterprise lock-in."
2. iText: "Legacy Java. GPL licensing traps."
3. Puppeteer/wkhtmltopdf: "Headless browsers for PDF? Really?"

### Features
Grid of 4 features:
1. JSON → PDF (template-based)
2. Sub-100ms generation
3. 668 tests (reliability)
4. Rust memory safety

### Pricing
3 tiers: Free / Pro $49 / Enterprise $299

### Code Example
```bash
curl -X POST https://api.folium.dev/v1/generate \
  -H "Authorization: Bearer your_api_key" \
  -H "Content-Type: application/json" \
  -d '{"template": "invoice", "data": {"company": "Acme"}}'
```

### Getting Started
3-step tutorial: Sign up → Get key → First PDF

## Deployment

- GitHub Pages via `astro build` → static output
- GitHub Actions: build on push to main, deploy to gh-pages
- Custom domain: folium.dev (future)
