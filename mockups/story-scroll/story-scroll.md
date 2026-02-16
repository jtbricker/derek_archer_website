# Story Scroll

> A research career told as a visual narrative — scroll to unfold.

![Story Scroll wireframe](story-scroll.svg)

---

## Vibe
Cinematic. Immersive. Each section is a full-screen "chapter" with its own visual identity, connected by smooth scroll transitions. The site feels like scrolling through a documentary about the research, not reading a CV. Sticky text panels stay in view while background visuals transition. It's the technique used by the NYT Upshot, Pudding.cool, and the best data journalism — applied to an academic profile. Think: if a researcher's career were told as a longform interactive piece.

## Color Palette

| Role | Color | Hex |
|------|-------|-----|
| Background (Chapter 1) | Deep indigo | `#0c0a3e` |
| Background (Chapter 2) | Forest dark | `#0a2818` |
| Background (Chapter 3) | Warm dark | `#1a0a0a` |
| Background (Chapter 4) | Slate dark | `#0f172a` |
| Accent (Chapter 1) | Violet | `#7c3aed` |
| Accent (Chapter 2) | Emerald | `#10b981` |
| Accent (Chapter 3) | Rose | `#f43f5e` |
| Accent (Chapter 4) | Blue | `#3b82f6` |
| Body text | Near-white | `#e2e8f0` |
| Muted text | Gray | `#94a3b8` |

Each chapter has its own color world — background + accent. As you scroll between chapters, the colors transition smoothly. This creates a feeling of traveling through different spaces.

## Typography
- **Display headings:** Playfair Display — high contrast, editorial, dramatic at large sizes
- **Body:** Source Sans 3 — clean, readable, journalistic feel
- **Accent/Labels:** Space Mono — monospace for chapter numbers and data labels

## Page Structure

The entire site is a **single-page scroll** with five distinct "chapters." Each chapter occupies at least one full viewport height. Navigation is minimal — a chapter indicator on the side replaces traditional nav.

### Chapter Indicator (Fixed, left edge)
- Vertical line of dots, one per chapter
- Active chapter dot is larger and colored
- Clicking a dot scrolls to that chapter
- Subtle chapter number appears next to the active dot
- This is the ONLY navigation element — no header, no menu

### Chapter 0: The Opening
- Full-viewport indigo background
- Name in massive Playfair Display (80px+), centered vertically
- Below the name: a single sentence in Source Sans italic
  - "Mapping the neuroscience of aging — from genes to brain to behavior."
- Subtle particle animation in the background (floating dots that drift slowly)
- Scroll indicator at bottom: a thin line with "Scroll to explore" in mono
- No buttons, no navigation, no metrics — pure dramatic opening

### Chapter 1: The Researcher
- Background transitions from indigo to a deep violet wash
- **Split layout**: sticky text panel on the left (40% width), visual panel on the right (60%)
- Left panel (sticky, stays in view):
  - Chapter number "01" in large Space Mono
  - "The Researcher" in Playfair Display
  - Bio text in Source Sans — not the entire CV, but a narrative paragraph about who Derek is
  - Affiliation, position
  - Awards and key career milestones as a small timeline
- Right panel (scrolls):
  - A stylized headshot or abstract portrait
  - As you scroll further, the image transitions to show the Vanderbilt campus, then to lab imagery
  - These visual transitions happen while the bio text stays pinned

### Chapter 2: The Science
- Background transitions to dark forest green
- **Horizontal card carousel** that scrolls vertically
  - As you scroll down, cards slide in from the right one at a time
  - Each card represents a research area
  - Cards are large (60% viewport width), glassy, with emerald accents
  - Each card: title, 3-4 sentence description, key methodology badges
  - 4 cards total for the 4 research areas
- Between cards, large data points appear as chapter title-sized typography
  - "2,060+ Citations" fades in between cards 1 and 2
  - "5 Major Cohorts" between cards 2 and 3
  - "NIH Funded" between cards 3 and 4

### Chapter 3: The Work
- Background transitions to warm dark red-black
- **Publications presented as a timeline**
  - A vertical line runs down the center of the viewport
  - Papers appear alternating left and right as you scroll
  - Each paper: year in large mono text, title, journal in accent color, author position badge
  - The timeline line animates — drawing itself as you scroll
  - Key papers are "highlighted" — larger card treatment, rose accent border, brief description of significance
- At the bottom: "Full publication list →" link to Google Scholar

### Chapter 4: The Network
- Background transitions to dark slate blue
- **Full-screen interactive collaboration graph**
  - Sticky heading: "The Collaborators"
  - Force-directed graph with Derek as the central node
  - Project nodes (VMAP, VADRC, CNT, VALIANT) orbit around him
  - Co-author nodes connected to projects
  - Nodes glow, edges pulse subtly
  - Hover on a project node: description tooltip appears
  - This section is taller than one viewport — scrolling zooms/pans the graph

### Chapter 5: The Contact (Brief)
- Minimal closing section
- "Let's Connect" in Playfair Display
- Email, institutional profile links
- Simple, short — the narrative is over

## Scroll Mechanics
- **Sticky panels**: Key text stays in view while visuals scroll past
- **Parallax layers**: Background elements move at different speeds
- **Scroll-triggered animations**: Elements fade in, slide in, or draw on as they enter the viewport
- **Color transitions**: Background color morphs between chapters using CSS transitions tied to scroll position
- **Chapter snapping**: Optional (can be turned off), chapters snap to viewport boundaries

## Mobile Adaptation
- Sticky panels become sequential (text, then visual)
- Horizontal card carousel becomes a vertical stack
- Timeline becomes left-aligned (line on left edge, content on right)
- Chapter indicator dots remain, moved to bottom center
- Particle animation reduced for performance

## What Makes This Design Distinctive
- **No traditional page structure** — it's a continuous narrative, not sections on a page. There's no header, no footer in the traditional sense.
- **Each chapter has its own color world** — transitioning between chapters feels like moving between rooms in a museum.
- **Scrollytelling mechanics** — sticky text + scrolling visuals is a proven technique from data journalism that's rarely seen on academic sites.
- **Dramatic typography** — Playfair Display at large sizes creates an editorial, almost book-like quality.
- **Publications as timeline** — instead of a list, papers are presented chronologically along a vertical line, making career progression visible.
- **Full-screen collaboration graph** — not a section, but an entire chapter dedicated to the interactive network.
- **Minimal navigation** — just chapter dots. The scroll IS the navigation.
- **Cinematic opening** — the first viewport is just the name and one sentence. Confidence in restraint.
