# Fieldwork Festival — website

A two-day creative festival for 400 independent designers, artists and creative founders.
**Make something. Meet someone. Leave inspired.**

- **When:** Saturday Dec 5 & Sunday Dec 6, 2026 · 10:00 AM – 5:00 PM Pacific, each day
- **Where:** Foundry Yard, Los Angeles
- **Tickets:** Weekend pass $80 · Single-day pass $45 — workshops & talks included, food sold separately, workshop seats first come, first served

## Live site

Published with GitHub Pages (public, no login required):
<https://mikkomikkomi.github.io/fieldwork-festival-website/>

## Quick start

The site is fully static — no build step, no dependencies.

```bash
# any static server works, e.g.:
python3 -m http.server 8080
# then open http://localhost:8080
```

## Project structure

```
index.html          # all markup (semantic, accessible)
css/style.css       # all styles, organized in commented sections
js/main.js          # vanilla JS enhancements (~150 lines, no dependencies)
assets/img/*.webp   # optimized stock photography (WebP)
```

HTML, CSS and JS are kept in separate files for readability, as requested.

## Design system

- **Brand palette (from the brief):** Forest `#183F35`, Butter `#F4E8AB`, Lilac `#C7AFE8`,
  plus warm paper neutrals derived from them.
- **Wordmark:** text-only "Fieldwork✳Festival" set in Fraunces with a lilac asterisk.
- **Type:** [Fraunces](https://fonts.google.com/specimen/Fraunces) for display,
  [Inter](https://fonts.google.com/specimen/Inter) for body — both via Google Fonts
  with `display=swap`.
- **Motion:** scroll reveals, marquee, ken-burns hero, floating stickers, hover lifts —
  all `transform`/`opacity` only (GPU-friendly) and fully disabled under
  `prefers-reduced-motion`.

## Features

- **Schedule with parallel tracks** — Main Stage and Studio shown side by side per day,
  simultaneous sessions share a row and are flagged with a lilac "same time" marker;
  day tabs (Sat/Sun) with full keyboard support (←/→/Home/End).
- **Day comparison** — each tab is summarized ("prints · collage · voice" vs
  "zines · murals · farewells") plus a what's-included table on the ticket cards.
- **Ticket comparison table** for weekend vs single-day passes.
- **Mobile-first responsive** — schedule collapses to stacked cards, hamburger nav,
  fluid type via `clamp()`.
- **Countdown** to doors opening (Dec 5, 2026, 10:00 PT).

## Accessibility & performance

- Semantic landmarks, skip link, ARIA tabs/tables, visible focus states,
  `prefers-reduced-motion` support, sufficient color contrast on all text.
- Works without JavaScript (nav stays open, all content visible).
- WebP imagery (~520 KB total), `width`/`height` attributes to avoid layout shift,
  lazy-loading below the fold, preloaded hero, deferred JS, two font families only.

## Photo credits (stock photography, free licenses)

All photos are stock photography served under free licenses — no AI-generated imagery.

| Used as                | Source | License |
| ---------------------- | ------ | ------- |
| Hero workshop table    | [Unsplash](https://unsplash.com/photos/photo-1757085242652-f8cd4d3de889) | Unsplash license |
| Print studio           | [Pexels 6620972](https://www.pexels.com/photo/6620972/) | Pexels license |
| Main Stage talk        | [Pexels 10401268](https://www.pexels.com/photo/10401268/) | Pexels license |
| Maker Market stall     | [Pexels 34247681](https://www.pexels.com/photo/34247681/) | Pexels license |
| Market lane (CTA band) | [Pexels 16414304](https://www.pexels.com/photo/16414304/) | Pexels license |
| Collaborative mural    | [Pexels 38429713](https://www.pexels.com/photo/38429713/) | Pexels license |
| Community meetup       | [Pexels 9630189](https://www.pexels.com/photo/9630189/) | Pexels license |
| Foundry Yard (venue)   | [Pexels 18344067](https://www.pexels.com/photo/18344067/) | Pexels license |

## Deployment

Static hosting on GitHub Pages via `.github/workflows/deploy-pages.yml`
(upload + deploy artifact on every push to `main` or the working branch).

**One-time setup (repository admin only):** GitHub Settings → Pages →
*Build and deployment* → Source: **GitHub Actions**. Creating a Pages site
requires admin rights that CI tokens don't have, so this single click can't
be automated; every deploy afterwards is automatic.
