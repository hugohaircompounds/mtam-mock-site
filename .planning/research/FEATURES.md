# Feature Research

**Domain:** Hair extension education platform homepage (JTBD-driven redesign demo)
**Researched:** 2026-03-30
**Confidence:** HIGH (current MTAM site verified via live fetch; competitor landscape from multiple sources)

---

## Context: The Core Job Being Done

Before mapping features, the JTBD analysis establishes what visitors are hiring this homepage to do.

**Functional job:** "Evaluate whether this platform will help me master hair extension techniques I can actually use with real clients."

**Emotional job:** "Feel like I belong here — that I'm not going to be judged for not knowing the 'right' method already."

**Social job:** "Be seen as a skilled, credible extension specialist who makes evidence-based technique decisions — not someone who just follows one brand's rules."

**Four-Dimensional Job Analysis (from MTAM context):**
- Functional: Learn installation techniques, troubleshooting, scalp health, business skills
- Emotional: Feel confident, not gatekept, not overwhelmed
- Social: Be perceived as technique-agnostic and professionally credible
- Identity: See myself as an educator, not just a practitioner — someone who understands the "why"

**Job Map stages this homepage must serve:**
1. **Define** — visitor identifies whether this platform matches their learning goal
2. **Locate** — visitor finds proof that the platform delivers what it claims
3. **Prepare** — visitor gathers enough confidence to make a purchase decision
4. **Confirm** — visitor validates the investment is worth the price
5. **Execute** — visitor converts (joins today)

Each homepage section below is mapped to the job step it primarily serves.

---

## Feature Landscape

### Table Stakes (Users Expect These)

Features stylists assume exist on any credible education platform homepage. Missing these = the page feels incomplete or untrustworthy.

| Feature | Why Expected | Job Step Served | Complexity | Notes |
|---------|--------------|-----------------|------------|-------|
| Hero with clear value proposition | Every subscription platform has one; absence signals amateur | Define | LOW | Must answer "who this is for" in < 8 words |
| Headline + subheadline above fold | Standard landing page convention; 3-second rule | Define | LOW | Outcome language beats method language here |
| Primary CTA button (above fold) | Visitors expect a clear next action immediately | Define | LOW | "Join Today" or outcome-phrased equivalent |
| What's included / course topics list | Visitors need to see scope before evaluating price | Locate | LOW | Can be bullet list or icon grid |
| Pricing section with tiers | Subscription platforms without visible pricing lose trust | Confirm | LOW | 3 tiers (monthly/quarterly/annual) are category norm |
| Social proof / testimonials | Trust signal required before any paid commitment | Prepare | LOW | Minimum 2-3 quotes with real names/photos |
| Founder or instructor identity | Who is teaching? Visitors need a face to trust | Locate | LOW | Photo + credentials + brief philosophy statement |
| Secondary CTA (mid-page) | Visitors who scroll need re-capture before pricing | Prepare | LOW | Placed after social proof or course topics |
| Footer with legal/nav links | Legal requirement + navigation fallback | Conclude | LOW | Terms, Privacy, Contact minimum |
| Mobile-responsive layout | 60%+ of web traffic is mobile | All | MEDIUM | Desktop-first acceptable for this demo context |

### Differentiators (Competitive Advantage)

Features that set MTAM apart from method-locked platforms like NBR Education, Platinum Seamless, or single-brand certification programs. These are where JTBD principles have the most design leverage.

| Feature | Value Proposition | Job Step Served | JTBD Framework | Complexity | Notes |
|---------|-------------------|-----------------|----------------|------------|-------|
| JTBD-structured page flow | Page sections mirror the visitor's decision-making job steps (Define > Locate > Prepare > Confirm > Execute) — not the platform's org chart | All | Job Map Framework + JTBD for IA | LOW (structural) | This is invisible to the visitor but immediately legible as "intentional" in a demo context |
| Outcome-based hero headline | Leads with what the stylist achieves ("Build the confidence to work across any extension system") not what the platform is ("A subscription platform") | Define | Outcome-Based Messaging Strategy | LOW | Replaces "Discover the MTAM difference" (vanity) with a desired outcome statement |
| Problem-first framing section | Names the specific struggles stylists face (being locked to one method, no troubleshooting support, gatekept knowledge) before offering the solution | Define | Struggle Stack Framework | LOW | Competitor platforms skip this entirely — they sell features, not problem relief |
| Anti-gatekeeping manifesto block | Explicit statement of philosophy: "We teach the why, not just the what. No method loyalty required." | Prepare | Four-Dimensional Job Analysis (identity job) | LOW | Directly addresses the identity/social job; no competitor articulates this so plainly |
| Guest educator grid with specialization labels | 11 educators shown with their specific expertise area, not just names/Instagram handles | Locate | JTBD for IA + Top Task Analysis | MEDIUM | Visitors hire educators for specific problems — showing specializations enables faster job matching |
| Outcome-labeled course topics | Course list uses outcome language ("Master weft application across 4 extension types") not feature language ("215 videos") | Locate | Customer Success Language Model | LOW | Direct application of CSS Modeling from JTBD frameworks |
| Testimonials with specific outcomes | Reviews quote what changed in the stylist's work, not just sentiment ("I now troubleshoot weft slips without calling anyone") | Prepare | Customer Success Statement (CSS) Modeling | LOW | Current MTAM testimonials are sentiment-based; outcome-based CSS approach is stronger |
| Value comparison signal | Shows what this replaces (expensive per-method certifications, scattered YouTube searches, brand-locked education) rather than features list | Confirm | Outcome-Based Competitive Matrix | LOW | Addresses the "is this worth $250/mo" job step with framing, not just listing benefits |
| JTBD annotation layer (demo-only) | Callout labels on each section explaining which JTBD framework decision produced it | All | JTBD Anti-Vanity Framework | LOW | This is the demo's unique value — showing the AI reasoning layer. No real platform has this. |
| Pricing anchored to outcome ROI | Pricing section leads with what you get per dollar relative to alternatives (e.g., "One in-person certification costs $2,500+ for one method. Here you get all methods.") | Confirm | Effort-Focused Market Sizing | LOW | Reframes price as effort reduction, not just cost |

### Anti-Features (Deliberately Not Building)

Features that appear valuable but would undermine the demo's goals, add complexity without payoff, or contradict the JTBD-driven approach.

| Feature | Why It Seems Appealing | Why It's Problematic for This Demo | Alternative |
|---------|------------------------|-------------------------------------|-------------|
| Working sign-up/login flow | Makes the demo feel more "real" | Breaks single-file constraint; adds backend complexity; if it fails during presentation it kills the demo | Static "Join Today" button scrolls to pricing section (in-page anchor) |
| Video player / embedded content | Platforms like MTAM lead with video content | External embed dependencies; videos can fail to load; adds load time; not needed to prove JTBD design value | Static before/after image grid or screenshot of course catalog |
| Interactive pricing calculator | Looks impressive | JavaScript state management in a single HTML file is fragile; if it breaks, the highlight of the demo fails | Static 3-tier pricing card layout with annual savings clearly labeled |
| "Before/after" photo carousel with JS | Visually compelling proof element | Carousel JS is brittle in single-file demos; images may not load in offline presentation contexts | Side-by-side static image grid with outcome captions |
| Live chat or contact widget | Seems like a conversion feature | Adds third-party script dependencies; irrelevant for a static demo page | "Contact Us" link in footer |
| Instagram feed integration | Social proof via real posts | Third-party API dependencies; breaks offline; rate limiting | Static grid of styled quote cards mimicking Instagram aesthetic |
| Countdown timer / urgency elements | Standard conversion tactic | Contradicts the anti-gatekeeping, low-pressure brand voice of MTAM; feels manipulative for an empowerment brand | Scarcity is implicit in the pricing anchor (limited-time annual rate) |
| Extensive FAQ section | Reduces purchase anxiety | Adds significant scroll length; dilutes JTBD narrative flow; FAQ answers should be embedded in the flow itself | Objections are addressed within the Struggle Stack section and testimonials |
| Detailed educator bios | Useful for trust-building | Creates content management burden; bios with 200+ words each slow the page; overly long for a scrolling demo | Name + one-line specialization label + photo in educator grid |
| Mobile-specific features | 60% of real traffic is mobile | Demo is shown on a presentation screen; mobile breakpoints add CSS complexity without demo value | Desktop-first layout; note in JTBD decision log that mobile would be phase 2 |

---

## Feature Dependencies

```
[JTBD-Structured Page Flow]
    └──requires──> [Defined Job Map: Define > Locate > Prepare > Confirm > Execute]
                       └──enables──> [All section placement decisions]

[Outcome-Based Hero Headline]
    └──requires──> [Four-Dimensional Job Analysis output]
                       └──requires──> [Functional + Emotional + Social jobs identified]

[Problem-First Framing Section]
    └──enhances──> [Anti-Gatekeeping Manifesto Block]
                       └──together reinforce──> [Emotional + Identity job completion]

[Testimonials with Specific Outcomes]
    └──requires──> [CSS Modeling: what does success look like for a stylist?]
    └──enhances──> [Pricing Section ROI framing]

[Guest Educator Grid with Specializations]
    └──requires──> [Educator names and specialization areas from MTAM source]
    └──enhances──> [Social proof value of the platform]

[JTBD Annotation Layer]
    └──requires──> [All other sections finalized]
    └──conflicts──> [Clean consumer-facing presentation]
    └──resolution──> [Annotations styled as subtle labels/tooltips, not inline text]

[Pricing Section]
    └──requires──> [All trust-building sections above it in scroll order]
    └──requires──> [Value comparison framing to land before price numbers]
```

### Dependency Notes

- **Job Map flow requires JTBD analysis completed first:** Section order on the page is not arbitrary — it follows the visitor's decision-making job steps. This structural decision must be made before writing any copy.
- **Outcome headlines require Four-Dimensional Job Analysis:** Cannot write outcome-based copy without first mapping functional, emotional, and social jobs for the MTAM audience specifically.
- **JTBD Annotation Layer conflicts with clean UX:** The annotation layer (which makes the demo legible as a JTBD demonstration) must be visually subordinate — callout labels, not body copy — otherwise it reads as documentation, not design.
- **Pricing section requires trust infrastructure above it:** Pricing placed too high on the page (before proof of value) fails the Confirm job step. The job map mandates: Define → Locate → Prepare → Confirm order.

---

## MVP Definition

This is a demo, not a product launch. "MVP" here means: minimum viable demo that proves JTBD + AI produces intentional design decisions.

### Launch With (v1 — the demo)

- [x] JTBD-structured page flow (sections ordered by job step, not org hierarchy)
- [x] Outcome-based hero headline (replaces "Discover the MTAM difference")
- [x] Problem-first framing section (Struggle Stack applied)
- [x] Anti-gatekeeping manifesto block (identity job addressed explicitly)
- [x] What's included / course outcome list (outcome language, not feature count)
- [x] Guest educator grid (name + specialization + photo placeholder)
- [x] Outcome-based testimonials (CSS-modeled: what changed, not just sentiment)
- [x] Pricing section with value comparison framing
- [x] JTBD annotation layer (subtle callout labels per section)
- [x] Footer (minimal: Terms, Contact, Copyright)

### Add After Validation (if demo leads to real project)

- [ ] Working sign-up flow — add when platform is being built, not demoed
- [ ] Video content previews — add when hosting infrastructure is in place
- [ ] Mobile-responsive breakpoints — add before any public launch
- [ ] Real founder/educator photos — replace placeholders before going live

### Future Consideration (real product, not demo)

- [ ] Interactive pricing calculator — only if A/B testing shows it improves conversion
- [ ] Dynamic FAQ accordion — only if customer support volume warrants it
- [ ] Instagram feed integration — only if brand social presence is consistent

---

## Feature Prioritization Matrix

| Feature | User Value (Demo) | Implementation Cost | Priority |
|---------|-------------------|---------------------|----------|
| JTBD-structured page flow (section order) | HIGH — core demo argument | LOW — structural decision | P1 |
| Outcome-based hero headline | HIGH — first impression | LOW — copywriting | P1 |
| Problem-first framing / Struggle Stack section | HIGH — emotional job | LOW — copywriting + layout | P1 |
| Anti-gatekeeping manifesto block | HIGH — identity job differentiator | LOW — copy block | P1 |
| Course topics with outcome language | HIGH — Locate job step | LOW — copy + icon grid | P1 |
| Guest educator grid | MEDIUM — Locate job step | MEDIUM — grid layout + placeholder images | P1 |
| Outcome-based testimonials | HIGH — Prepare job step | LOW — card layout + copy | P1 |
| Pricing with value comparison | HIGH — Confirm job step | LOW — 3-column card layout | P1 |
| JTBD annotation layer | HIGH — demo-specific differentiator | MEDIUM — requires overlay/callout system | P1 |
| Working pricing CTAs (anchor links) | MEDIUM — fake interactivity | LOW — href="#pricing" | P2 |
| Founder identity section | MEDIUM — trust signal | LOW — photo + bio copy | P1 |
| Footer | LOW — expected, not differentiating | LOW | P2 |

**Priority key:**
- P1: Must have for launch (demo)
- P2: Should have, add when possible
- P3: Nice to have, future consideration

---

## Competitor Feature Analysis

Research covered: morethanamethod.com (primary), NBR Education (nbr.education), Bespoke Hair Education, Harper Ellis Hair, Behind the Chair University.

| Feature | MTAM (current) | NBR Education | Bespoke Hair Ed | JTBD-Redesigned MTAM |
|---------|----------------|---------------|-----------------|----------------------|
| Page section order | Platform-centric (hero → founders → features → educators → testimonials → pricing) | Method-centric (hero → before/after → video → courses) | Service-centric (nav → services → testimonials → CTA) | Job-step-centric (Define → Locate → Prepare → Confirm → Execute) |
| Hero messaging | Vanity ("Discover the MTAM difference") | Method authority ("Luxury hair extensions training") | Service descriptor ("Online Tutorials + Private Workshops") | Outcome-based ("Build the confidence to work across any extension system") |
| Problem acknowledgment | Partial (benefits list addresses problems indirectly) | None (method-promotion focused) | None (service catalog) | Explicit Struggle Stack section — names the pain before selling the solution |
| Educator presentation | Carousel with Instagram links | Team page separate | Founder bio only | Grid with specialization labels tied to problem types |
| Testimonials format | Sentiment-based quotes | Transformation stories (anecdotal) | Professional endorsements | Outcome statements (CSS-modeled: specific results, not feelings) |
| Pricing framing | Feature-count parity ("215+ videos") | Not shown on homepage | Not shown | Effort-reduction framing ("replaces $2,500+ per-method certifications") |
| JTBD annotation | None | None | None | Visible callout layer showing framework decisions |
| Identity/social job | Implicit in "anti-gatekeeping" copy | Not addressed | Not addressed | Explicit manifesto block |

---

## JTBD Framework Mapping Per Section

This table is the JTBD decision log referenced in PROJECT.md requirements. It maps each homepage section to the specific JTBD framework that governs its design.

| Page Section | Primary Job Step | JTBD Framework Applied | Design Decision Driven By Framework |
|-------------|-----------------|------------------------|--------------------------------------|
| Hero | Define | Outcome-Based Messaging Strategy + Four-Dimensional Job Analysis | Headline leads with functional outcome, not platform name or tagline |
| Struggle Stack / Problem framing | Define → Locate | Struggle Stack Framework + JTBD Core Framework (push factors) | Names push factors (what made them look) before revealing solution |
| Anti-gatekeeping manifesto | Define | Four-Dimensional Job Analysis (identity + social job) | Addresses identity job: "I want to be seen as technique-agnostic and credible" |
| What you'll master (course outcomes) | Locate | JTBD for IA + Customer Success Language Model | Content organized around learner's job outcomes, not platform's catalog hierarchy |
| Guest educator grid | Locate | Top Task Analysis + JTBD for IA | Educators labeled by specialization (problem type) not just name/credentials |
| Founder identity | Prepare | JTBD Core Framework (trust-building before confirmation) | Founder story told as "why I built this to solve my own problem" — struggle-origin narrative |
| Testimonials | Prepare | Customer Success Statement (CSS) Modeling | Quotes structured around what changed in practice, not just satisfaction ratings |
| Pricing + value comparison | Confirm | Effort-Focused Market Sizing + Outcome-Based Competitive Matrix | Price anchored against effort-to-alternative, not just feature count |
| Primary CTA | Execute | JTBD for Integrated Marketing Strategy | CTA language mirrors the final job step: "Start learning" not "Subscribe now" |
| JTBD annotation layer | (meta — demo-specific) | JTBD Anti-Vanity Framework | Callouts prove each element exists to serve a job, not for visual appeal |

---

## Sources

- Live fetch of morethanamethod.com homepage (2026-03-30) — verified current site structure and pricing
- NBR Education (nbr.education) — competitor analysis, structural comparison
- Bespoke Hair Education (bespokehaireducation.com) — competitor testimonial and section patterns
- Harper Ellis Hair education page — competitor CTA and course presentation patterns
- Elite Beauty Society: "The Top Hair Education Platforms to Watch & Learn From"
- WebSearch: hair extension education platform trends 2025 (Platform Hair Extensions, Donna Bella, AQUA Hair Extensions)
- JTBD Foundational Frameworks file (local) — Job Map, ODI, Four-Dimensional Analysis, CSS Modeling
- JTBD Marketing Frameworks file (local) — Struggle Stack, Outcome-Based Messaging, Customer Success Language Model
- JTBD Design Team Frameworks file (local) — JTBD Anti-Vanity, JTBD for IA, Outcome-Driven Design Thinking

---

*Feature research for: Hair extension education platform homepage (JTBD-driven redesign demo)*
*Researched: 2026-03-30*
