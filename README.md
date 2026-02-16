# derekarcher.com

Personal academic website for **Derek B. Archer, PhD** — Assistant Professor of Neurology at Vanderbilt University Medical Center.

## About

A digital CV and research showcase featuring:

- Professional bio, education, positions, and awards
- Curated publications with links to Google Scholar and PubMed
- Research area overviews (neuroimaging, computational genetics, white matter neurodegeneration, AI brain signatures)
- Collaboration and project affiliations (VMAP, VADRC, CNT, VALIANT)
- Interactive visualizations: 3D brain viewer, citation trends, collaboration network graph

## Tech Stack

- [Astro](https://astro.build/) — static site generator with islands architecture
- [Tailwind CSS v4](https://tailwindcss.com/) — utility-first styling
- [React](https://react.dev/) — interactive components (hydrated on scroll)
- [D3.js](https://d3js.org/), [Chart.js](https://www.chartjs.org/), [Three.js](https://threejs.org/) — data visualization

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
