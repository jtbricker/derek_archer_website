# Field Notes

> A researcher's notebook — organized, searchable, always open on the desk.

![Field Notes wireframe](field-notes.svg)

---

## Vibe
Documentation-first. The site looks like a well-organized research notebook or a Stripe docs page. There's a persistent sidebar table of contents, a wide readable main column, and an optional right sidebar for contextual info. It's designed for depth — visitors who want to actually read about the research, not just skim a CV. Think: a technical documentation site, but for a person instead of a product.

## Color Palette

| Role | Color | Hex |
|------|-------|-----|
| Sidebar background | Off-white warm | `#f9f8f6` |
| Main background | White | `#ffffff` |
| Right sidebar bg | Off-white cool | `#f8fafc` |
| Border | Warm gray | `#e7e5e4` |
| Primary accent | Indigo | `#4f46e5` |
| Secondary accent | Teal | `#0d9488` |
| Heading text | Stone 900 | `#1c1917` |
| Body text | Stone 700 | `#44403c` |
| Muted text | Stone 500 | `#78716c` |
| Code/data bg | Stone 100 | `#f5f5f4` |

Light, warm, highly legible. The palette is deliberately simple — the content is the star. Indigo is used sparingly for links and active states. Teal highlights key data points.

## Typography
- **Headings:** Crimson Pro — a refined serif that says "academic" without being stuffy
- **Body:** Source Sans 3 — excellent readability for long-form text
- **Code/Data:** IBM Plex Mono — for DOIs, PMIDs, code snippets, methodology labels
- **Line length:** Capped at 680px for optimal readability. This is a READING site.

## Page Structure

The defining feature is the **three-column layout**: persistent left sidebar + main content + contextual right sidebar.

### Left Sidebar (Fixed, 260px)

#### Top: Identity Block
- Name in Crimson Pro (18px), no PhD or title — just the name
- Affiliation in muted text (13px)
- Small headshot (48x48, circular)
- Thin divider

#### Navigation
- Organized into **sections**, not just pages:
  - **Overview** (the homepage)
  - **Research**
    - Neuroimaging Biomarkers
    - Computational Genetics
    - White Matter Neurodegeneration
    - AI Brain Signatures
  - **Publications**
    - Featured Papers
    - All Publications
    - By Topic
  - **Projects**
    - VMAP
    - VADRC
    - CNT
    - VALIANT
  - **About**
    - Biography
    - CV
    - Awards
  - **Contact**
- Active page is highlighted with indigo left border + indigo text
- Sections are collapsible (click section header to toggle)
- Each item is a page — this is a MULTI-PAGE site with deep content

#### Bottom: External Links
- Google Scholar, ORCID, PubMed, GitHub
- Small icon + text links
- Thin divider above

### Main Content Column (Scrollable, ~680px)

#### On the Overview Page:
- **Page title** in large Crimson Pro: "Overview"
- **Breadcrumb** at top: "Overview" in muted text
- **Research summary** — 2-3 paragraphs in Source Sans, readable body text
- **Callout boxes** — indigo-bordered boxes for key highlights:
  - One for "Research Focus" — a 3-sentence distillation
  - One for "Current Work" — what he's working on right now
- **Quick stats grid** — a 2x2 grid of small stat cards:
  - Each has a number in IBM Plex Mono, a label below
  - Subtle teal left border
- **Recent publications** — compact list with titles as links
- **News/Updates** — optional, a few recent updates (new paper, grant, talk)
- All content has clear heading hierarchy: H2 for sections, H3 for subsections

#### On a Research Area Page (e.g., "Neuroimaging Biomarkers"):
- Breadcrumb: "Research > Neuroimaging Biomarkers"
- Long-form description of the research area (3-5 paragraphs)
- **Key Publications** in this area (auto-filtered)
- **Methodology** section with monospace-styled technical details
- **Figure** — an SVG diagram or chart embedded inline
- "Related Areas" links at the bottom

#### On the Publications Page:
- Search/filter bar at the top
- Publications grouped by year with year headers
- Each entry: title (Crimson Pro bold), authors (Source Sans, "Archer DB" highlighted), journal in indigo, year
- Small pill badges for "First Author" / "Last Author"
- DOI link in IBM Plex Mono
- PDF download button if available
- Click title to expand inline abstract

### Right Sidebar (Fixed, 220px, contextual)
This is the secret weapon — it shows different content depending on the current page:

#### On Overview:
- "On this page" — section links for the current page content (like a table of contents within the page)
- Quick links: Google Scholar, Contact

#### On a Research Area Page:
- "Key Metrics" — citation counts for papers in this area
- "Collaborators" — names of key collaborators in this area
- "Related Topics" — links to other research areas

#### On a Publication Page:
- "Citation" — copyable citation in APA/BibTeX
- "Metrics" — citation count, Altmetric score
- "Related Work" — other papers by Archer on the same topic

The right sidebar is hidden on mobile and on pages where it's not needed.

### Header
- **No traditional header** — the sidebar IS the navigation
- A minimal top bar on mobile with hamburger to toggle sidebar

### Footer
- Minimal, inside the main content column only
- Copyright, last updated date, "Built with Astro" credit
- Not full-width — just text at the bottom of the content

## Mobile Adaptation
- Sidebar collapses into a hamburger drawer (slides in from left)
- Right sidebar hidden entirely (content moves inline where needed)
- Main content goes full-width with padding
- Bottom tab bar with 4 icons: Overview, Research, Papers, Menu
- Search icon in top bar

## What Makes This Design Distinctive
- **Three-column layout** — the persistent sidebars make this feel like a reference document, not a marketing page. Visitors can navigate deep content without losing context.
- **Docs-style navigation** — collapsible sections with deep hierarchy. Each research area, each project gets its own page. This is for people who want to READ, not skim.
- **Contextual right sidebar** — changes based on what you're looking at. On a publication, you see citation info. On a research area, you see related metrics. Smart and useful.
- **Light, warm palette** — off-white backgrounds and warm grays feel like paper. This is deliberately anti-dark-mode.
- **Reading-optimized** — 680px max content width, generous line height, Crimson Pro serif headings. This is typeset for reading, not scanning.
- **Inline expandable content** — publication abstracts expand inline, reducing the need for separate pages for each paper.
- **Search-first** — the publications page has a real search/filter bar. This is a REFERENCE site.
- **No hero section** — the overview page starts with text, not a splash. The sidebar provides all the context about who this person is.
- **Breadcrumbs** — always know where you are. This is a deep site and breadcrumbs prevent disorientation.
