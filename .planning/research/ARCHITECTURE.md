# Architecture Research

**Domain:** JTBD-driven single-page homepage — hair extension education platform
**Researched:** 2026-03-30
**Confidence:** HIGH

---

## Standard Architecture

### Page Structure Overview

The page is a single vertical scroll. Each section corresponds to one step in the Universal Job Map
(Define → Locate → Prepare → Confirm → Execute). The visitor's scroll position IS their job progression.

```
┌─────────────────────────────────────────────────────────────┐
│  SECTION 1: HERO                                            │
│  Job Step: DEFINE                                           │
│  "Who this is for and what you'll achieve"                  │
├─────────────────────────────────────────────────────────────┤
│  SECTION 2: PROOF BAR / SOCIAL SIGNAL                       │
│  Job Step: LOCATE (entry point)                             │
│  "Others like you are here — you're in the right place"     │
├─────────────────────────────────────────────────────────────┤
│  SECTION 3: PROBLEM / STRUGGLE ACKNOWLEDGMENT               │
│  Job Step: LOCATE (framing)                                 │
│  "We know your struggle. Here's what's different."          │
├─────────────────────────────────────────────────────────────┤
│  SECTION 4: CURRICULUM / WHAT YOU GET                       │
│  Job Step: LOCATE (content)                                 │
│  "Here are the specific resources you've been looking for"  │
├─────────────────────────────────────────────────────────────┤
│  SECTION 5: HOW IT WORKS                                    │
│  Job Step: PREPARE                                          │
│  "Here's exactly how to plug this into your practice"       │
├─────────────────────────────────────────────────────────────┤
│  SECTION 6: INSTRUCTOR / PLATFORM CREDIBILITY               │
│  Job Step: CONFIRM                                          │
│  "Christine and Alex have done this — you can trust them"   │
├─────────────────────────────────────────────────────────────┤
│  SECTION 7: TESTIMONIALS                                    │
│  Job Step: CONFIRM (peer validation)                        │
│  "Stylists like you already got results"                    │
├─────────────────────────────────────────────────────────────┤
│  SECTION 8: FAQ / OBJECTION HANDLING                        │
│  Job Step: CONFIRM (remove last friction)                   │
│  "Your hesitation has been addressed"                       │
├─────────────────────────────────────────────────────────────┤
│  SECTION 9: CALL TO ACTION / ENROLL                         │
│  Job Step: EXECUTE                                          │
│  "Join now — here's your path forward"                      │
└─────────────────────────────────────────────────────────────┘
```

### Section-to-Job-Step Mapping

| Section | Job Step | JTBD Function | Three-Dimensional Job Served |
|---------|----------|---------------|------------------------------|
| 1. Hero | DEFINE | Visitor confirms this platform matches their goal | Emotional: "I'm seen." Functional: "This teaches extensions." |
| 2. Proof Bar | LOCATE | Social signal reduces search cost | Social: "Real stylists are here." |
| 3. Struggle Acknowledgment | LOCATE | Validates frustration with gatekeeping | Emotional: "They get it." |
| 4. Curriculum Overview | LOCATE | Delivers the information being sought | Functional: "This has what I need." |
| 5. How It Works | PREPARE | Removes setup anxiety about how to engage | Functional: "I can fit this in." |
| 6. Instructor Credibility | CONFIRM | Authority establishes trust | Social: "I'm learning from someone credible." |
| 7. Testimonials | CONFIRM | Peer evidence removes "will this work for me?" | Social + Emotional |
| 8. FAQ | CONFIRM | Resolves final hesitations before commitment | Functional: "No surprises." |
| 9. CTA / Enroll | EXECUTE | Single, frictionless action | Functional: "I know exactly what to do next." |

---

## Recommended File Structure

This is a single self-contained HTML file. Internal organization matters for build order and editing.

```
slideshows/
└── mtam-homepage-demo.html     # Entire page — all CSS/JS inline

    Internal structure (comment blocks):
    ├── <!-- HEAD: fonts, meta, base CSS variables -->
    ├── <!-- SECTION 1: Hero (DEFINE) -->
    ├── <!-- SECTION 2: Proof Bar (LOCATE) -->
    ├── <!-- SECTION 3: Struggle / Anti-Gatekeeping (LOCATE) -->
    ├── <!-- SECTION 4: Curriculum Overview (LOCATE) -->
    ├── <!-- SECTION 5: How It Works (PREPARE) -->
    ├── <!-- SECTION 6: Instructor Credibility (CONFIRM) -->
    ├── <!-- SECTION 7: Testimonials (CONFIRM) -->
    ├── <!-- SECTION 8: FAQ (CONFIRM) -->
    └── <!-- SECTION 9: CTA / Enroll (EXECUTE) -->
```

### Structure Rationale

- **Comment-separated sections:** Each JTBD step is its own clearly labeled block. This makes the
  JTBD decision notes artifact easy to produce — one comment per section maps directly to the
  framework.
- **CSS variables at the top:** Brand tokens (colors, fonts, spacing) defined once so all sections
  stay visually consistent without repetition.
- **No JS required for scroll flow:** Static scroll is sufficient. The job progression happens
  through vertical layout, not interactive logic.

---

## Architectural Patterns

### Pattern 1: Outcome-First Hero

**What:** The hero section leads with a customer outcome statement, not a product feature or
tagline. Following the Customer Success Language Model, it converts a desired outcome ("minimize
time to become confident with installation techniques") into emotionally resonant copy.

**When to use:** Always — this is the Define step. The visitor must immediately confirm they are
in the right place or they leave.

**Trade-offs:** Outcome-first copy requires committing to a specific customer job. The benefit is
high relevance for the target audience. The risk is that generic visitors feel excluded — which is
intentional for this platform.

**Example structure:**
```
H1: [Outcome statement — what they'll achieve]
H2/subhead: [Who this is for — job performer identification]
CTA button: [First call to action — visible above fold]
Visual: [Professional styling image — social job signal]
```

### Pattern 2: Struggle-Before-Solution Sequencing

**What:** Section 3 (Struggle Acknowledgment) appears BEFORE Section 4 (Curriculum Overview).
The platform names the frustration (gatekeeping, method loyalty pressure, lack of judgment-free
resources) before presenting its solution. This follows the JTBD Four-Dimensional Job Analysis —
the emotional job ("feel safe to learn") must be addressed before functional content lands.

**When to use:** Any time the target customer has a trust deficit or past negative experience with
the product category. Hair stylists who have felt gatekept by method-specific educators arrive
with skepticism. Name it before selling to it.

**Trade-offs:** Adds a section to the page. Worth it here because the emotional job is the primary
differentiator — other platforms lead with curriculum, MTAM leads with philosophy.

### Pattern 3: CONFIRM as a Multi-Component Zone

**What:** The Confirm job step requires the most page real estate because it must address multiple
types of doubt: authority doubt (does this person know what they're doing?), peer doubt (did this
work for someone like me?), and practical doubt (what if I have questions?). Three distinct
sections — Instructor Credibility, Testimonials, FAQ — each handle one type of doubt.

**When to use:** Any education platform where the purchase involves risk and the visitor cannot
trial the product before committing.

**Trade-offs:** Three sections in sequence can feel long. Solve with visual variation — change
background colors, card layouts, or column structure between confirm sections to signal new
information, not repetition.

### Pattern 4: Single Execute Point

**What:** The CTA section at the bottom is the ONLY hard sell on the page. All upstream sections
use soft framing. This follows the JTBD Anti-Vanity Framework — CTAs embedded in earlier sections
are vanity additions that interrupt job progression without contributing to the visitor's progress
toward Confirm.

**When to use:** When the product requires high trust before purchase (subscription, education,
recurring investment). Do not scatter CTAs. One CTA at Hero (for ready buyers), one CTA at Execute
(for visitors who needed the full job progression).

**Trade-offs:** Fewer conversion touchpoints. This is correct. Forcing the Execute action before
the visitor has completed Confirm produces bounced clicks, not enrollments.

---

## Data Flow

### Visitor Scroll Journey (Job Progression)

```
Visitor arrives
    ↓
DEFINE: "Is this for me?" — Hero resolves this
    ↓
LOCATE: "What do they offer? Is this legitimate?" — Proof Bar + Struggle + Curriculum resolves this
    ↓
PREPARE: "How would this actually work for me?" — How It Works resolves this
    ↓
CONFIRM: "Can I trust this?" — Instructor + Testimonials + FAQ resolves this
    ↓
EXECUTE: "What do I do now?" — CTA section makes action frictionless
    ↓
Enrollment / inquiry
```

### Three-Dimensional Job Coverage Across Sections

```
Functional job:  Section 4 (Curriculum) + Section 5 (How It Works) + Section 8 (FAQ)
Emotional job:   Section 1 (Hero) + Section 3 (Struggle) + Section 7 (Testimonials)
Social job:      Section 2 (Proof Bar) + Section 6 (Instructor) + Section 7 (Testimonials)
```

Every section serves at least one job dimension. No section is purely cosmetic — this is the
Anti-Vanity Framework applied to layout.

---

## Visual Hierarchy Supporting Job Progression

| Section | Visual Treatment | JTBD Reason |
|---------|-----------------|-------------|
| Hero | Full viewport height, large type, centered | Define needs immediate clarity — no visual noise |
| Proof Bar | Narrow strip, small text, logos or numbers | Locate signal — should feel like a footnote of confidence, not a shout |
| Struggle / Anti-gatekeeping | Dark or contrasting background, generous white space | Emotional section needs breathing room — feels different from product content |
| Curriculum | Card grid or numbered list | Locate — scannable information architecture, visitor is in research mode |
| How It Works | Numbered steps or 3-column icons | Prepare — process clarity, reduce setup anxiety |
| Instructor | Side-by-side photo + bio | Confirm — faces build trust more than text alone |
| Testimonials | Card carousel or quote blocks with names/photos | Confirm — specificity of peer signals matters |
| FAQ | Accordion or simple Q&A list | Confirm — functional, low visual weight, get out of the way |
| CTA | High contrast, isolated, single action | Execute — nothing competes for attention |

---

## Build Order

Build sections in job map order. Each section is a standalone HTML block that can be written,
styled, and reviewed independently before assembly.

**Recommended sequence:**

1. **CSS foundation first** — Define brand tokens (colors, typography, spacing) as CSS custom
   properties. All subsequent sections reference these. Changing a token updates the whole page.

2. **Section 1: Hero (DEFINE)** — This is the hardest copy to write and the most important
   section. Get the outcome-first headline right before building anything else. If the Define
   section doesn't work, the rest of the page is irrelevant.

3. **Section 9: CTA / Enroll (EXECUTE)** — Build this second. It defines what the visitor is
   being asked to do. Every upstream section exists to make this action feel natural. Knowing the
   Execute section helps you frame all middle sections toward it.

4. **Sections 3–4: Struggle + Curriculum (LOCATE)** — This is the substantive product content.
   Build these together — they are the "what we offer and why" pairing.

5. **Section 5: How It Works (PREPARE)** — Short section, high value for reducing friction. Build
   after curriculum content is locked.

6. **Sections 6–8: Confirm zone** — Instructor, Testimonials, FAQ. Build in this order: authority
   first, peer proof second, objection handling third. Together they form the trust arc.

7. **Section 2: Proof Bar (LOCATE entry)** — Build last. Numbers and social signals are often
   placeholder ("1,200 stylists enrolled") and should be finalized after all other content is set.

8. **Final pass: scroll flow review** — Read the page top to bottom as a job progression. Each
   section should answer the question left unanswered by the prior section. If a section creates
   no new progress, remove or merge it.

---

## Anti-Patterns

### Anti-Pattern 1: Feature-First Hero

**What people do:** Open with "The #1 Platform for Hair Extension Education" or a product feature
list above the fold.

**Why it's wrong:** Fails the Define step. The visitor has not yet confirmed this platform matches
their goal. Feature language skips to Locate before the visitor has committed to searching here.
Results in high bounce from the target audience (stylists who've been burned by gatekeeping
platforms) because nothing addresses their emotional job first.

**Do this instead:** Open with an outcome statement that names the visitor's job and what they
will achieve. "Build extension skills on your terms — no method loyalty required" addresses the
functional job (build skills) and the emotional/social job (anti-gatekeeping) simultaneously.

### Anti-Pattern 2: CTA Scattered Across All Sections

**What people do:** Embed "Start Today" buttons in the hero, after the curriculum section, inside
the testimonials section, and before the FAQ.

**Why it's wrong:** Interrupts job progression. A visitor who is in the LOCATE or PREPARE step
is not ready to Execute. Premature CTA pressure signals the platform prioritizes conversion over
the visitor's progress. Following the JTBD Anti-Vanity Framework, any CTA that doesn't serve the
visitor's current job step is a vanity addition.

**Do this instead:** One soft CTA in the hero (for ready buyers who already know what they want).
One full CTA section at the end as the Execute step. Nothing in between.

### Anti-Pattern 3: Testimonials Before Credibility

**What people do:** Place testimonials high on the page to lead with social proof before
establishing instructor authority.

**Why it's wrong:** Peer proof only works once authority is established. The visitor's internal
sequence is: "Do I trust the platform?" then "Did it work for others like me?" Inverting this
puts peer evidence before the foundation that makes peer evidence meaningful.

**Do this instead:** Instructor credibility (Section 6) before testimonials (Section 7). The
Confirm arc runs: authority → peer proof → objection handling. Each step amplifies the prior.

### Anti-Pattern 4: FAQ as an Afterthought

**What people do:** Write a FAQ section with generic questions ("Do you offer refunds?") as a
legal/logistical appendix at the bottom.

**Why it's wrong:** The FAQ is the final piece of the Confirm job step. Its function is to remove
the last specific friction before the visitor executes. Generic questions don't resolve specific
hesitations. The FAQ must address the actual objections of the target audience — for stylists
considering MTAM, these are: "Will this work for my texture clientele?", "Do I need prior
extension experience?", "How much time per week does this take?"

**Do this instead:** Write FAQ questions from JTBD interview data (or simulated customer voice).
Each question should represent a known struggle at the Confirm step.

---

## Integration Points

### External Services (for demo — CDN only)

| Service | Integration Pattern | Notes |
|---------|---------------------|-------|
| Google Fonts (Raleway + Manrope) | CDN link in `<head>` | Matches MTAM brand — fonts load from Google CDN |
| Placeholder images | `/placeholder.svg` or `via.placeholder.com` | No real photos needed for demo |
| Icons | Inline SVG or Unicode | Keeps file self-contained, no external icon CDN dependency |

### Internal Boundaries

| Boundary | Communication | Notes |
|----------|---------------|-------|
| CSS variables → all sections | Single declaration block at top | Color/font changes propagate to entire page |
| Hero CTA → Execute CTA | Visual consistency | Both CTAs should look identical so the Execute CTA feels familiar, not new |
| Struggle section → Curriculum section | Narrative bridge | A single transitional sentence connects the emotional claim to the functional evidence |

---

## Sources

- JTBD Foundational Frameworks (Job Map Framework) — `/JTBD/Foundational Frameworks-20260330121422.md`
- JTBD Design Team Cheat Sheet (Anti-Vanity Framework, JTBD for IA, Job Step Mapping) — `/JTBD/Design Team Framework Cheat Sheet-20260330121518.md`
- JTBD Marketing Frameworks (Four-Dimensional Job Analysis, Customer Success Language Model, Outcome-Based Messaging Strategy) — `/JTBD/Marketing Frameworks-20260330121414.md`
- JTBD Product Frameworks (Universal Job Map, Full Job Mapping) — `/JTBD/Product JTBD Framework Cheat Sheet-20260330121436.md`
- PROJECT.md — Project requirements, constraints, and JTBD framework application context

---

*Architecture research for: JTBD-driven single-page homepage, morethanamethod.com hair extension education platform*
*Researched: 2026-03-30*
