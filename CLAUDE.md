# CLAUDE.md

This file provides guidance to Claude Code (claude.ai/code) when working with code in this repository.

## Project Overview

Landing page for **R. Amaral**, a Brazilian transport and tourism company (school transport + group travel) located in Tijucas, SC. Built as a single-page site following a Figma prototype at 1440px desktop resolution. WhatsApp contact: +48 999503368. Multi-page expansion is planned — see `PLANO-PAGINAS.md` for the roadmap (Destinos, Serviços, Blog, Sobre, Contato pages).

## Tech Stack

- **Astro 6** (SSG) with `.astro` components
- **Tailwind CSS 4** via `@tailwindcss/vite` plugin (configured in `astro.config.mjs`)
- **Swiper** for carousels (Partners, News)
- **Google Fonts**: Inter (400, 600, 700)
- **Playwright** for E2E tests (Chromium only)

## Commands

```bash
npm run dev         # Start dev server (port 4321)
npm run build       # Production build
npm run preview     # Preview production build

# Tests (Playwright E2E)
npm test                          # Run all tests (~93)
npm test -- tests/hero.spec.ts    # Run tests for a specific component
npm run test:ui                   # Interactive visual UI
npm run test:report               # Open HTML report from last run
```

## Architecture

- `src/pages/index.astro` — Single page composing sections: Navbar → Hero → Benefits → Partners → Services → NewsCarousel → Footer
- `src/layouts/BaseLayout.astro` — HTML shell with meta tags, Google Fonts, global CSS import. Body applies `font-sans text-dark-gray bg-white`
- `src/components/` — One `.astro` file per page section. `BenefitCard` and `ServiceCard` are sub-components used inside their parent sections
- `src/styles/global.css` — Tailwind import + custom theme tokens (colors, font via `@theme`)

## Design Tokens (defined in `global.css` via `@theme`)

| Token              | Value     | Usage                          |
|--------------------|-----------|--------------------------------|
| `--color-primary`  | `#0099CC` | CTAs, headlines, icons         |
| `--color-dark`     | `#1A1A2E` | Navbar/footer background       |
| `--color-light-gray` | `#F5F5F5` | Alternate section backgrounds |
| `--color-dark-gray` | `#333333` | Body text                     |
| `--color-medium-gray` | `#666666` | Secondary text              |
| `--color-light-blue` | `#DCF0F7` | Benefit icon backgrounds     |

## Key Conventions

- Language: site content is in **Brazilian Portuguese** (lang="pt-BR")
- All components are Astro-only (no React/Vue/Svelte)
- Tailwind 4 syntax: use `@theme` directive for custom tokens, not `tailwind.config.js`
- Asset directories: `assets/images/{hero,gallery,icons,logos}`, `assets/fonts/`, `assets/videos/`
- **Design reference**: `ASSETS.md` has the full Figma spec (colors, typography, sections, required images/icons); `figma/figma-page-1.jpeg` is the full-page screenshot; Figma prototype link in `README.md`
- Swiper is initialized via `<script>` tags inside the component `.astro` files (not imported as a framework component); import from `swiper/bundle`
- **Hero form JS patterns**: date picker uses a hidden `<input type="date" class="sr-only">` + visible readonly display input (JS calls `showPicker()` on click, formats as DD/MM/AAAA); service type uses radio inputs with `sr-only` + styled `<span>` pills; origin/destination uses OpenStreetMap Nominatim autocomplete with 350ms debounce (3+ chars); school dropdown replaces destination field in `escolar` mode
- **Tests**: Playwright E2E in `tests/`. One file per component (e.g. `Hero.astro` → `tests/hero.spec.ts`). Run the affected test after each change. Playwright's `webServer` auto-starts the dev server if not running (`reuseExistingServer: true`). Tests run on Chromium only
