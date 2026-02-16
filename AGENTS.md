# Agent Operating Rules

## Project Overview

Personal academic website for **Derek B. Archer, PhD**, Assistant Professor of Neurology at Vanderbilt University Medical Center. Deployed to **www.derekarcher.com** via GitHub Pages.

Derek's research focuses on neuroimaging and computational genetics for neurodegenerative diseases (Alzheimer's, white matter neurodegeneration, aging). He has 2,060+ citations on Google Scholar.

## Tech Stack

- **Framework**: Astro 5 (static site generator with islands architecture)
- **Styling**: Tailwind CSS v4 (via `@tailwindcss/vite` plugin, CSS-first `@theme` config in `src/styles/global.css`)
- **Interactive components**: React islands (hydrated with `client:visible`)
- **Visualization libraries**: D3.js, Chart.js, Three.js (via react-three-fiber)
- **Content**: JSON data files in `src/data/` with Zod schemas in `src/content/config.ts`
- **Deployment**: GitHub Actions → GitHub Pages (triggered on push to `main`)

## Git Workflow

- **Push directly to `main`**. No pull requests needed until the site is live and serving public content.
- Write clear commit messages describing what changed and why.
- Do not force-push to `main`.

## Project Structure

```
.github/workflows/deploy.yml    # GitHub Actions deployment
public/                         # Static assets (CNAME, images, robots.txt)
src/
  components/
    layout/                     # Header, Footer, SEOHead, Navigation
    home/                       # Home page sections
    cv/                         # CV/About page components
    publications/               # Publication list components
    research/                   # Research page components
    interactive/                # React island components (.tsx)
    ui/                         # Reusable UI primitives (Button, Card, etc.)
  content/
    config.ts                   # Astro content collection schemas (Zod)
  data/                         # JSON data files (publications, CV, citations, etc.)
  layouts/                      # BaseLayout.astro, PageLayout.astro
  pages/                        # Route pages (index, about, research, publications, contact, 404)
  styles/
    global.css                  # Tailwind import + @theme design tokens
```

## Build & Dev Commands

```bash
npm run dev        # Start local dev server
npm run build      # Production build (run this to check for errors before pushing)
npm run preview    # Preview production build locally
```

## Design System

- **Color palette**: Dark navy backgrounds (`#0a1628` base), teal accent (`#14b8a6`), gold accent (`#f59e0b`), purple for interactive elements (`#8b5cf6`)
- **Typography**: Inter (headings), Source Sans 3 (body), JetBrains Mono (data/code)
- **Component style**: Glass-morphism cards on dark backgrounds with subtle hover effects
- **Tone**: Professional, modern academic — not flashy, but polished

## Coding Conventions

- Use `.astro` components for static content (zero JS shipped to browser).
- Use `.tsx` React components **only** for interactive elements that require client-side JS.
- Always use `client:visible` (not `client:load`) for React islands to defer hydration.
- Structured data lives in `src/data/*.json`, not hardcoded in components.
- Keep components focused and small. Prefer composition over large monolithic components.
- Use Tailwind utility classes. Avoid writing custom CSS unless truly necessary.
- Tailwind v4 uses `@theme` in CSS — do NOT create a `tailwind.config.js` file.

## Content Guidelines

- Publications are curated in `src/data/publications.json` (15-20 key papers). The site links to Google Scholar for the full list.
- CV data is structured in `src/data/cv.json` (education, positions, awards, skills).
- Citation metrics and yearly data live in `src/data/citations.json`.
- Research areas are defined in `src/data/research-areas.json`.
- When adding or modifying content, follow the Zod schemas defined in `src/content/config.ts`.

## Key External Links

- Google Scholar: https://scholar.google.com/citations?user=InzF7XUAAAAJ&hl=en
- VUMC Neurology profile: https://www.vumc.org/neurology/person/derek-b-archer-phd
- VMAC profile: https://www.vumc.org/vmac/person/derek-b-archer-phd
- CNT profile: https://www.vumc.org/cnt/person/derek-archer-phd
- Contact: derek.archer@vumc.org

## Deployment

The site deploys automatically via `.github/workflows/deploy.yml` on every push to `main`. The workflow uses `withastro/action@v5` to build and `actions/deploy-pages@v4` to deploy. The custom domain is configured via `public/CNAME`.

## Session Management

- **"Wrap up" or "save context"**: When the user says either of these phrases, update memory files with all important context from the session before ending. This includes research findings, decisions made, current status, and anything that would be needed to resume work.
- **Proactive saves**: If the session has been long and productive, proactively suggest saving context even if not asked.
- Memory files live in the auto memory directory. See `MEMORY.md` for the index of topic files.

## Things to Avoid

- Do not add a `tailwind.config.js` — Tailwind v4 is configured in CSS via `@theme`.
- Do not use `client:load` for heavy interactive components — use `client:visible`.
- Do not auto-fetch publications from external APIs — maintain the curated JSON file.
- Do not create PR branches — push to `main` directly.
- Do not add unnecessary JS to `.astro` components. Keep them static.
