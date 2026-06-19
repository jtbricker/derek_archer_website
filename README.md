# derekarcher.com

Personal academic website for **Derek B. Archer, PhD** — Assistant Professor of Neurology at Vanderbilt University Medical Center.

## About

A digital CV and research showcase featuring:

- Professional bio, education, positions, and awards
- Curated publications with links to Google Scholar and PubMed
- Research area overviews (neuroimaging, computational genetics, white matter neurodegeneration, AI brain signatures)
- Collaboration and project affiliations (VMAP, VADRC, CNT, VALIANT)
- Citation and publication metrics
- Links to institutional profiles, Google Scholar, and publication PDFs

## Tech Stack

- [Astro](https://astro.build/) — static site generator with islands architecture
- [Tailwind CSS v4](https://tailwindcss.com/) — utility-first styling
- [React](https://react.dev/) — available for interactive islands when needed

## Development

```bash
npm install        # Install dependencies
npm run dev        # Start dev server
npm run build      # Production build
npm run preview    # Preview production build
```

## Deployment

Pushes to `main` trigger a GitHub Actions workflow that builds the Astro site and deploys to GitHub Pages at [www.derekarcher.com](https://www.derekarcher.com).

## Documentation

- [Hosting & Domain Setup](docs/hosting.md) — DNS configuration, GitHub Pages setup, deployment pipeline
- [Publications](docs/papers/PUBLICATIONS.md) — Curated first & last author papers with PDFs
- [Papers TODO](docs/papers/TODO.md) — Papers still needing manual PDF upload

## Current Status

The site is fully built and deployable. All five content pages exist, content JSON files are populated, and the GitHub Actions pipeline and DNS are configured per `docs/hosting.md`.

**What's done:**
- Complete Astro 5 site with `/`, `/about/`, `/research/`, `/publications/`, `/contact/`, and `/404` pages
- Content loaded from JSON files in `src/data/` (publications, CV, research areas, citations, collaborations)
- Publication PDFs in `docs/papers/` served as static assets
- GitHub Actions deploy pipeline (`.github/workflows/deploy.yml`)
- DNS configured: Squarespace → GitHub Pages → `www.derekarcher.com`
- Three design mockups explored (stored in `mockups/`, not shipped)

**Outstanding tasks:**
1. **Verify the site is live** — confirm GitHub Pages is enabled, DNS has propagated, and `www.derekarcher.com` resolves. Push to `main` and watch the Actions workflow.
2. **Upload missing PDF** — one paper needs manual sourcing (JAMA Neurology 2025, PMID 40513084). See [Papers TODO](docs/papers/TODO.md) for the filename and instructions.
3. **Interactive components (future)** — D3.js citation charts, Three.js 3D brain viewer, and a collaboration network graph were in the design mockups but not yet implemented. Dependencies (`d3`, `three`, `@react-three/fiber`) are already in `package.json`.
