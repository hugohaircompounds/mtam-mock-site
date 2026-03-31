# Phase 3: Documentation - Context

**Gathered:** 2026-03-31
**Status:** Ready for planning

<domain>
## Phase Boundary

Create the two required documentation artifacts (prompt list + JTBD decision notes) and verify the HTML file renders correctly on the presentation device. All three deliverables (HTML + 2 docs) saved to `slideshows/`.

</domain>

<decisions>
## Implementation Decisions

### Prompt List (DLVR-01)
- **D-01:** Curated summaries — clean, readable bullets capturing intent, not raw verbatim prompts
- **D-02:** Organized as a beginner's guide for someone new to Claude/vibe coding who wants to design a website for their hair salon. NOT organized by build phase. Foundation and Documentation phases excluded entirely — only page design prompts included.
- **D-03:** Conversational tone — written like you're talking to a friend ("Tell Claude to build you a hero section that..."). Approachable for someone who's never used AI tools.
- **D-04:** Generalized for any hair salon — "your salon name" / "your services" instead of MTAM-specific references. The audience should immediately picture using this for their own business.

### JTBD Decision Notes (DLVR-02)
- **D-05:** Table mapping format — Page Section | JTBD Stage | Framework Used | Why This Section Exists. Quick to scan during a presentation.
- **D-06:** Framework name + principle level of specificity — e.g., "Job Map Framework — Define stage: name the struggle before offering a solution." Shows which JTBD cheat sheet drove each decision.
- **D-07:** MTAM-specific — these notes explain THIS demo's decisions. The audience points at a section and reads why it exists.

### Document Format & Location
- **D-08:** Markdown (.md) files for both documents
- **D-09:** Saved to `slideshows/` alongside the HTML demo — all three deliverables in one folder

### Offline Test Strategy
- **D-10:** Assume WiFi available at Chennai venue — CDN-loaded fonts, icons, and scripts are acceptable
- **D-11:** Target device is Chrome on Windows laptop — no cross-browser testing needed

### Claude's Discretion
- Naming conventions for the two .md files
- Exact number of prompts to include in the prompt list (enough to be useful, not exhaustive)
- Which JTBD frameworks from `JTBD/` to reference per section (use best judgment based on what actually drove the design)

</decisions>

<canonical_refs>
## Canonical References

**Downstream agents MUST read these before planning or implementing.**

### JTBD Frameworks (source material for decision notes)
- `JTBD/Foundational Frameworks-20260330121422.md` — Core JTBD theory, Job Map Framework
- `JTBD/Marketing Frameworks-20260330121414.md` — Outcome-Based Messaging Strategy
- `JTBD/Product JTBD Framework Cheat Sheet-20260330121436.md` — Four-Dimensional Job Analysis
- `JTBD/Design Team Framework Cheat Sheet-20260330121518.md` — JTBD for IA, Anti-Vanity Framework
- `JTBD/Strategy Frameworks Cheat Sheet-20260330121526.md` — Customer Success Language Model

### Existing Deliverable
- `slideshows/mtam-homepage-demo.html` — The HTML demo file (source of truth for section structure and content)

### Project Context
- `.planning/PROJECT.md` — Project overview, constraints, key decisions
- `.planning/REQUIREMENTS.md` — DLVR-01 and DLVR-02 acceptance criteria

</canonical_refs>

<code_context>
## Existing Code Insights

### Reusable Assets
- `slideshows/mtam-homepage-demo.html` — 591-line single-file HTML demo with 10 sections in JTBD job-map order

### Established Patterns
- Section order follows JTBD Job Map: Define (hero, struggle, manifesto) > Locate (topics, educators, founders) > Confirm (testimonials, pricing) > Execute (CTA, footer)
- Design system: Tailwind v4 Play CDN, GSAP ScrollTrigger, Phosphor Icons, Google Fonts (DM Serif Display + Manrope)
- Color palette: alternating `#E1EFE6` (sage) and `#271204` (chocolate) sections with `#C9A84C` gold accent

### Integration Points
- Both new .md files go into `slideshows/` alongside the HTML file
- JTBD decision notes must map to actual sections in the HTML (IDs: hero, struggle, manifesto, topics, educators, founders, testimonials, pricing, cta, footer)

</code_context>

<specifics>
## Specific Ideas

- The prompt list is a **teaching tool for the audience**, not a build log. It should read as "here's how YOU would prompt AI to build your salon website" — a template the Chennai audience walks away with.
- The JTBD decision notes are the **proof artifact** — they demonstrate that every section exists because a framework decision put it there, not because it looked nice.
- Together, the two documents tell the story: the prompt list shows HOW (AI + conversational prompting), the decision notes show WHY (JTBD framework driving every choice).

</specifics>

<deferred>
## Deferred Ideas

None — discussion stayed within phase scope.

</deferred>

---

*Phase: 03-documentation*
*Context gathered: 2026-03-31*
