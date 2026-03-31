# MTAM Homepage Demo — JTBD Redesign

## What This Is

A demo-ready, single-page HTML redesign of the MoreThanAMethod.com homepage that demonstrates how AI combined with the Jobs-To-Be-Done framework can intentionally drive website design decisions for hair stylists. Built for a STYSTS business presentation in Chennai showing what AI can do for beauty professionals trying to build a web presence.

## Core Value

Every section of the page exists because a JTBD framework decision put it there — the demo must visually prove that AI + JTBD produces intentional, customer-job-driven design, not just pretty layouts.

## Requirements

### Validated

- [x] Single HTML file with all CSS/JS inline, saved to `slideshows/` folder — Validated in Phase 1: Foundation
- [x] Page structure driven by JTBD job map: Define > Locate > Prepare > Confirm > Execute — Validated in Phase 1: Foundation (placeholder comments in correct order)
- [x] Looks polished and presentation-ready (modern design, smooth typography, visual hierarchy) — Validated in Phase 1: Foundation (design token system established)
- [x] Retains MTAM brand essence: professional yet approachable, anti-gatekeeping, empowerment-focused — Validated in Phase 1: Foundation (brand tokens: DM Serif Display + Manrope, warm gold accent)
- [x] Creative reimagining of morethanamethod.com homepage (not a pixel clone) — Validated in Phase 2: page-sections (JTBD job-map layout with modern dark aesthetic, real educator photos, sticky header)
- [x] Messaging uses outcome-based language (what the customer achieves, not feature lists) — Validated in Phase 2: page-sections (all headings use outcome language, zero feature-count patterns)
- [x] Addresses functional job (learn extension techniques), emotional job (feel confident, not judged), and social job (be seen as a skilled professional) — Validated in Phase 2: page-sections (hero=functional, struggle+manifesto=emotional, educators+testimonials=social)
- [x] Scroll-only static page — no functional interactivity required — Validated in Phase 2: page-sections (10 sections scroll top-to-bottom with GSAP animations)

### Active

(None — all requirements validated)

### Recently Validated (Phase 3)

- [x] Prompt list document — beginner-friendly AI prompt guide with 30 conversational prompts organized by design concept — Validated in Phase 3: Documentation
- [x] JTBD decision notes — 10-row table mapping every page section to its JTBD stage, framework, and rationale — Validated in Phase 3: Documentation

### Out of Scope

- Working sign-up/login functionality — demo only
- Backend or database — single static HTML file
- Multiple pages or routing — homepage only
- Presentation slide (PowerPoint/Google Slides) — handled separately
- ~~Real founder/educator photos~~ — moved to validated: real photos pulled from morethanamethod.com during Phase 2
- Mobile-responsive perfection — desktop-first for presentation context
- E-commerce or payment integration

## Context

- **Domain**: Hair extension education platform (online courses, community, certifications)
- **Current site**: morethanamethod.com — built on Uscreen, uses Raleway/Manrope fonts, black/white aesthetic, subscription model ($250-$1,250/yr)
- **Founders**: Christine Woods and Alex — emphasize "why" behind techniques, anti-gatekeeping philosophy
- **Target audience for the site**: Hair stylists seeking extension education without rigid method loyalty
- **Target audience for the demo**: Business meeting attendees evaluating AI + JTBD for web design
- **JTBD frameworks applied**: Job Map Framework, Four-Dimensional Job Analysis, JTBD Anti-Vanity Framework, Outcome-Based Messaging Strategy, JTBD for IA, Customer Success Language Model
- **Presentation context**: STYSTS business meeting in Chennai — demonstrating AI capabilities for the beauty industry

## Constraints

- **Format**: Single self-contained HTML file (all CSS/JS inline, no external dependencies except CDN fonts/icons)
- **Location**: Must be saved to `slideshows/` directory so link can be clicked during presentation
- **Complexity**: Simple enough to explain in a meeting, polished enough to impress
- **Framework**: Must demonstrably apply JTBD principles from the `/JTBD/` reference files
- **Deliverables**: HTML file + prompt list + JTBD decision notes (3 artifacts total)

## Key Decisions

| Decision | Rationale | Outcome |
|----------|-----------|---------|
| Creative reimagine over faithful clone | JTBD-first layout proves the framework's value better than copying existing structure | Confirmed Phase 2 |
| Scroll-only, no interactivity | Demo is viewed during a presentation — simplicity over functionality | Confirmed Phase 2 |
| Real MTAM educator photos from CDN | Presenter requested actual headshots instead of placeholders — makes demo more credible | Added Phase 2 |
| Sticky header with MTAM text logo | Presenter requested header similar to original site but more modern | Added Phase 2 |
| Hero background image from MTAM site | Full-bleed background with gradient overlay for modern aesthetic | Added Phase 2 |
| Single HTML file | Clickable link in slideshow must just work — no build step, no server | Confirmed Phase 1 |
| Desktop-first design | Will be shown on a presentation screen, not mobile devices | Confirmed Phase 1 |

## Evolution

This document evolves at phase transitions and milestone boundaries.

**After each phase transition** (via `/gsd:transition`):
1. Requirements invalidated? -> Move to Out of Scope with reason
2. Requirements validated? -> Move to Validated with phase reference
3. New requirements emerged? -> Add to Active
4. Decisions to log? -> Add to Key Decisions
5. "What This Is" still accurate? -> Update if drifted

**After each milestone** (via `/gsd:complete-milestone`):
1. Full review of all sections
2. Core Value check — still the right priority?
3. Audit Out of Scope — reasons still valid?
4. Update Context with current state

---
*Last updated: 2026-03-31 after Phase 3 completion — all milestone v1.0 phases complete*
