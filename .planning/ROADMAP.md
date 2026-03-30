# Roadmap: MTAM Homepage Demo — JTBD Redesign

## Overview

Three phases deliver a single-file HTML presentation demo: first, a working scaffold with the design system locked (so every section shares one source of truth for brand tokens); second, all page sections built in JTBD job-map order (Define through Execute); third, the two required documentation artifacts and a pre-delivery test pass. Each phase produces something verifiable before the next begins.

## Phases

**Phase Numbering:**
- Integer phases (1, 2, 3): Planned milestone work
- Decimal phases (2.1, 2.2): Urgent insertions (marked with INSERTED)

Decimal phases appear between their surrounding integers in numeric order.

- [ ] **Phase 1: Foundation** - HTML scaffold + design system (file structure, CDN stack, brand tokens, desktop layout baseline)
- [ ] **Phase 2: Page Sections** - All JTBD-structured content sections from Hero (Define) through Footer (Execute)
- [ ] **Phase 3: Documentation** - Prompt list and JTBD decision notes artifacts + pre-delivery test pass

## Phase Details

### Phase 1: Foundation
**Goal**: A browser-openable HTML file exists with the full CDN stack loaded, brand design tokens defined, and desktop layout baseline verified — ready for section content to be added
**Depends on**: Nothing (first phase)
**Requirements**: STRC-01, STRC-02, STRC-03, STRC-04, DSGN-01, DSGN-02, DSGN-03, DSGN-04
**Success Criteria** (what must be TRUE):
  1. Opening the file in a browser shows a styled page with no console errors and all CDN assets loaded (fonts, icons, animation library)
  2. Brand tokens (color palette, font families, spacing scale) are defined once in a `:root` block and visibly applied — changing one token updates the whole page
  3. The page renders correctly on a desktop/presentation resolution without horizontal scrolling or layout breakage
  4. The file is saved to the `slideshows/` directory and can be opened by double-clicking (no build step, no server)
**Plans**: 1 plan

Plans:
- [ ] 01-01-PLAN.md — HTML scaffold with CDN stack, design tokens, token verification block, and JTBD section placeholders

**UI hint**: yes

### Phase 2: Page Sections
**Goal**: The complete homepage exists with all JTBD-structured sections in job-map order (Define > Locate > Prepare > Confirm > Execute), every headline using outcome-based language, and all three job dimensions (functional, emotional, social) explicitly addressed
**Depends on**: Phase 1
**Requirements**: HERO-01, HERO-02, HERO-03, HERO-04, HERO-05, CONT-01, CONT-02, CONT-03, TRST-01, TRST-02, TRST-03, CONV-01, CONV-02
**Success Criteria** (what must be TRUE):
  1. Scrolling from top to bottom reveals sections in Define > Locate > Prepare > Confirm > Execute order with no section out of sequence
  2. The hero headline describes what the stylist achieves (outcome), not what the platform offers (feature) — no feature-count language or "Access/Get + product noun" patterns present
  3. The anti-gatekeeping manifesto block and struggle acknowledgment section explicitly name stylist identity frustrations before introducing any solution content
  4. Pricing shows 3 tiers with value comparison framing anchored against per-method certification costs (not just price-point listing)
  5. A presenter can point to any section and explain in one sentence which JTBD job step put it there and why
**Plans**: TBD
**UI hint**: yes

### Phase 3: Documentation
**Goal**: All three required deliverables exist — the HTML file (from Phase 2), a prompt list document, and a JTBD decision notes document — and the HTML file passes an offline test on the presentation device
**Depends on**: Phase 2
**Requirements**: DLVR-01, DLVR-02
**Success Criteria** (what must be TRUE):
  1. The prompt list document exists in bullet format, organized by build phase, showing the prompts used to construct the demo
  2. The JTBD decision notes document maps every page section to the specific framework decision that shaped it, with one-sentence rationale per section
  3. The HTML file loads all assets and renders correctly with WiFi disabled (or explicit confirmation of venue internet reliability and CDN fallback plan documented)
**Plans**: TBD

## Progress

**Execution Order:**
Phases execute in numeric order: 1 → 2 → 3

| Phase | Plans Complete | Status | Completed |
|-------|----------------|--------|-----------|
| 1. Foundation | 0/1 | Checkpoint (awaiting human verify) | - |
| 2. Page Sections | 0/TBD | Not started | - |
| 3. Documentation | 0/TBD | Not started | - |
