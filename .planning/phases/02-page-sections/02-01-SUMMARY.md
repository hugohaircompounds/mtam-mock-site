---
phase: 02-page-sections
plan: 01
subsystem: ui
tags: [html, tailwind, jtbd, sections, phosphor-icons]

# Dependency graph
requires:
  - phase: 01-foundation
    provides: "HTML scaffold with CDN stack, design tokens, @theme utilities, section placeholder comments"
provides:
  - "DEFINE zone: hero section with outcome headline and CTA"
  - "DEFINE zone: struggle stack with 5 named stylist frustrations"
  - "DEFINE zone: anti-gatekeeping manifesto with identity-first philosophy"
  - "LOCATE zone: 6 course topic cards with outcome-based headings"
  - "LOCATE zone: 8 verified educator cards with founder badges"
  - "LOCATE zone: founders section with struggle-origin narrative"
affects: [02-02, phase-03]

# Tech tracking
tech-stack:
  added: []
  patterns:
    - "Section container: py-[96px] bg-brand-bg with max-w-[1200px] mx-auto px-8"
    - "Card pattern: bg-brand-surface rounded-[16px] p-6 with class marker (topic-card, educator-card)"
    - "Accent divider: h-[2px] bg-brand-accent w-16 for manifesto and founders"
    - "Badge pattern: inline-block bg-brand-accent text-brand-bg font-body font-semibold text-[14px] px-3 py-1 rounded-[8px]"
    - "Struggle item: py-6 border-b border-brand-border for vertical list rhythm"

key-files:
  created: []
  modified:
    - "slideshows/mtam-homepage-demo.html"

key-decisions:
  - "Straight apostrophes used in HTML copy (not curly quotes) for maximum browser compatibility"
  - "Icon element rendered as inline <i> with display:block implied by mb-4 spacing for card layout"
  - "Educator photo placeholders use ph-user icon at 48px; founders placeholder uses ph-user-circle at 96px for visual distinction"

patterns-established:
  - "JTBD zone comment markers: <!-- JOB MAP: DEFINE --> and <!-- JOB MAP: LOCATE --> for section grouping"
  - "Alternate surface sections: bg-brand-surface on manifesto (DEFINE zone emotional anchor)"
  - "Grid column patterns: 3-col for topics, 4-col for educators, 2-col for founders narrative"

requirements-completed: [HERO-01, HERO-02, HERO-03, HERO-04, HERO-05, CONT-01, CONT-02, CONT-03]

# Metrics
duration: 3min
completed: 2026-03-31
---

# Phase 02 Plan 01: DEFINE + LOCATE Zones Summary

**6 JTBD-structured HTML sections (hero, struggle stack, manifesto, topics grid, educator cards, founders narrative) with outcome-based language enforced across all headings and zero feature-count patterns**

## Performance

- **Duration:** 3 min
- **Started:** 2026-03-31T15:01:52Z
- **Completed:** 2026-03-31T15:05:19Z
- **Tasks:** 2
- **Files modified:** 1

## Accomplishments
- Built complete DEFINE zone: hero with outcome headline addressing functional job, struggle stack naming 5 specific stylist frustrations in second-person, and anti-gatekeeping manifesto bridging identity frustration to MTAM philosophy
- Built complete LOCATE zone: 6 course topic cards with outcome language (not feature counts), 8 verified educator cards with correct names/specializations and founder badges, and founders section with struggle-origin narrative
- Removed Phase 1 token verification block cleanly, preserving GSAP script and all remaining zone comment placeholders
- Enforced all JTBD anti-patterns: no brand name in DEFINE zone (except manifesto philosophy close), no feature-count headings, no hardcoded hex values, no unauthorized font sizes or weights

## Task Commits

Each task was committed atomically:

1. **Task 1: Remove verification block and build DEFINE zone** - `254905e` (feat)
2. **Task 2: Build LOCATE zone (topics, educators, founders)** - `dab04aa` (feat)

**Plan metadata:** pending (docs: complete plan)

## Files Created/Modified
- `slideshows/mtam-homepage-demo.html` - Added 6 content sections (hero, struggle, manifesto, topics, educators, founders), removed token verification block

## Decisions Made
- Followed plan exactly as specified for all section content, layout, and class patterns
- Used straight apostrophes in HTML copy for browser compatibility (plan used curly quotes in some places)
- Photo placeholders differentiated: ph-user at 48px for educator grid, ph-user-circle at 96px for founders section

## Deviations from Plan

None - plan executed exactly as written.

## Issues Encountered
None - all sections built cleanly from plan specifications, all automated verifications passed on first attempt.

## User Setup Required
None - no external service configuration required.

## Known Stubs
- **Educator photo placeholders** (`slideshows/mtam-homepage-demo.html`, educator-card elements): All 8 educator cards use `ph ph-user` icon placeholders instead of real photos. Intentional per PROJECT.md ("Real founder/educator photos -- placeholder imagery acceptable"). No future plan to resolve; photos can be swapped in if available.
- **Founders photo placeholder** (`slideshows/mtam-homepage-demo.html`, founders section left column): Uses `ph ph-user-circle` icon at 96px instead of real photo. Same rationale as educator placeholders.

## Next Phase Readiness
- DEFINE and LOCATE zones are complete; CONFIRM zone (testimonials, pricing) and EXECUTE zone (final CTA, footer) are ready to be built in Plan 02
- GSAP animation script block is preserved and ready for animation wiring (likely Plan 02 or Phase 3)
- Remaining zone comment placeholders (PREPARE, CONFIRM, EXECUTE) are intact for Plan 02

## Self-Check: PASSED

- FOUND: slideshows/mtam-homepage-demo.html
- FOUND: .planning/phases/02-page-sections/02-01-SUMMARY.md
- FOUND: commit 254905e (Task 1)
- FOUND: commit dab04aa (Task 2)

---
*Phase: 02-page-sections*
*Completed: 2026-03-31*
