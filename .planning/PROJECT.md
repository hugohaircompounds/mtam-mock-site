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

### Active

- [ ] Creative reimagining of morethanamethod.com homepage (not a pixel clone)
- [ ] Messaging uses outcome-based language (what the customer achieves, not feature lists)
- [ ] Addresses functional job (learn extension techniques), emotional job (feel confident, not judged), and social job (be seen as a skilled professional)
- [ ] Scroll-only static page — no functional interactivity required
- [ ] Prompt list document — bullet format showing prompts used to build the demo
- [ ] JTBD decision notes — maps each page section to the JTBD framework decision that shaped it

### Out of Scope

- Working sign-up/login functionality — demo only
- Backend or database — single static HTML file
- Multiple pages or routing — homepage only
- Presentation slide (PowerPoint/Google Slides) — handled separately
- Real founder/educator photos — placeholder imagery acceptable
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
| Creative reimagine over faithful clone | JTBD-first layout proves the framework's value better than copying existing structure | -- Pending |
| Scroll-only, no interactivity | Demo is viewed during a presentation — simplicity over functionality | -- Pending |
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
*Last updated: 2026-03-30 after Phase 1 completion*
