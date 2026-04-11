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

- The site currently ships as a static Astro build with five content pages (`/`, `/about/`, `/research/`, `/publications/`, `/contact/`).
- Content is sourced from JSON files in `src/data/`.
- The only documented outstanding task is the missing manual PDF upload listed in [Papers TODO](docs/papers/TODO.md).
