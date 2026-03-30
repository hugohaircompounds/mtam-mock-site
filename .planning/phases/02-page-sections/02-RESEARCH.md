# Phase 2: Page Sections — Research

**Researched:** 2026-03-30
**Domain:** JTBD-structured HTML section content — messaging, layout, animation, real content
**Confidence:** HIGH

---

<phase_requirements>
## Phase Requirements

| ID | Description | Research Support |
|----|-------------|------------------|
| HERO-01 | Hero section with outcome-based headline addressing the functional job | Functional job language patterns + Job Map Define zone findings |
| HERO-02 | Subheadline addressing the emotional job (confidence, no judgment) | Four-Dimensional Job Analysis + Functional-Social-Emotional Alignment findings |
| HERO-03 | Primary CTA button above the fold | Customer Success Language Model: "Start Learning" confirmed, job-completion framing |
| HERO-04 | Problem-first framing section naming specific stylist struggles (Struggle Stack) | Struggle Stack framework + identity barrier layer documented |
| HERO-05 | Anti-gatekeeping manifesto block addressing identity/social job | Social/identity job patterns + MTAM brand voice documented |
| CONT-01 | Course topics list using outcome language (not feature counts) | Real MTAM content catalog + Outcome-Based Messaging Strategy findings |
| CONT-02 | Guest educator grid with name + specialization label + placeholder image | Real educator names and specializations verified from morethanamethod.com |
| CONT-03 | Founder identity section with struggle-origin narrative | Founder data (Christine Woods + Alex Denaro) + struggle-origin narrative pattern |
| TRST-01 | Outcome-based testimonials structured around practice changes | CSS (Customer Success Statement) Modeling → testimonial structure pattern |
| TRST-02 | Pricing section with 3 tiers (monthly/quarterly/annual) | Real verified pricing from morethanamethod.com/join |
| TRST-03 | Value comparison framing anchored against per-method certification costs | Industry cert cost data + value comparison framing pattern |
| CONV-01 | Final CTA section with job-completion language ("Start learning" not "Subscribe") | Customer Success Language Model + CONV-01 confirmed label |
| CONV-02 | Footer with minimal navigation (Terms, Contact, Copyright) | Standard footer pattern — no JTBD complexity required |
</phase_requirements>

---

## Summary

Phase 2 adds all content to the scaffold built in Phase 1. The HTML file already has the correct CDN stack, design tokens, and 5 job-map zone placeholder comments in order (DEFINE, LOCATE, PREPARE, CONFIRM, EXECUTE). The task is replacing those comments with real section HTML while enforcing three rules simultaneously: job-map zone ordering, outcome-based language in every headline, and three-dimensional job coverage (functional, emotional, social/identity).

The most important research finding is that MTAM's brand is built on a specific identity claim — anti-gatekeeping, technique-agnostic, "the why behind the method" — and this claim must appear as section content, not just as a tone note. The Struggle Stack and anti-gatekeeping manifesto (HERO-04, HERO-05) must lead with named identity frustrations *before* any solution is introduced. This is the JTBD Define zone: the visitor confirms their goal and struggle before the platform offers anything.

Real MTAM content data is now verified: pricing tiers ($249.99/mo, $549.99/qtr, $1,250/yr), educator names and specializations (Christine Woods, Alex Denaro, Haley Evans, Yovanka Loria, Stella Komi, Krista Bartik, Jaye Edwards, and others), and the correct platform content description (350+ on-demand videos, monthly guest masterclasses, weekly live coaching, private community).

**Primary recommendation:** Build Phase 2 as a single plan with sections in strict job-map zone order. Remove the token verification block first, then insert each zone's HTML in sequence (DEFINE through EXECUTE). Apply GSAP ScrollTrigger entrance animations last, in a single script block at the bottom of the body.

---

## Standard Stack

The stack is fully locked from Phase 1. No new dependencies are added in Phase 2. All additions are pure HTML/CSS content using the existing CDN assets.

### Confirmed Stack (from Phase 1, no changes)

| Asset | Version | CDN URL | Status |
|-------|---------|---------|--------|
| Tailwind v4 Play CDN | `@tailwindcss/browser@4` | `cdn.jsdelivr.net/npm/@tailwindcss/browser@4` | Loaded in `<head>` |
| GSAP Core | `gsap@3.14.2` | `cdn.jsdelivr.net/npm/gsap@3.14.2/dist/gsap.min.js` | Loaded in `<head>` |
| GSAP ScrollTrigger | `gsap@3.14.2` | `cdn.jsdelivr.net/npm/gsap@3.14.2/dist/ScrollTrigger.min.js` | Loaded, plugin registered |
| Phosphor Icons | `@phosphor-icons/web@2.1.2` | Both regular and fill weights loaded | Available via `ph` and `ph-fill` classes |
| Google Fonts | current | DM Serif Display + Manrope (400, 600) | Loaded |

**No new CDN dependencies.** Phase 2 adds zero new `<script>` or `<link>` tags.

### Tailwind Utility Classes Available (from Phase 1 @theme)

All token-based utilities are already compiled and ready:
- Backgrounds: `bg-brand-bg`, `bg-brand-surface`, `bg-brand-border`, `bg-brand-accent`, `bg-brand-accent-hover`
- Text: `text-brand-text`, `text-brand-muted`, `text-brand-accent`
- Borders: `border-brand-border`, `border-brand-accent`
- Fonts: `font-display`, `font-body`
- Tailwind standard utilities all available (flex, grid, max-w, padding, etc.)

---

## Architecture Patterns

### Overall Section Structure

```
<body>
  <!-- Token verification block REMOVED (first action in Phase 2) -->

  <!-- JOB MAP: DEFINE -->
  <section id="hero">          <!-- HERO-01, HERO-02, HERO-03 -->
  <section id="struggle">      <!-- HERO-04: Struggle Stack -->
  <section id="manifesto">     <!-- HERO-05: Anti-gatekeeping -->

  <!-- JOB MAP: LOCATE -->
  <section id="topics">        <!-- CONT-01: Course topics -->
  <section id="educators">     <!-- CONT-02: Educator grid -->
  <section id="founders">      <!-- CONT-03: Founder story -->

  <!-- JOB MAP: PREPARE (reserved in v1, no content section) -->
  <!-- comment retained, no HTML section added -->

  <!-- JOB MAP: CONFIRM -->
  <section id="testimonials">  <!-- TRST-01: Testimonials -->
  <section id="pricing">       <!-- TRST-02, TRST-03: Pricing + value comparison -->

  <!-- JOB MAP: EXECUTE -->
  <section id="cta">           <!-- CONV-01: Final CTA -->
  <footer id="footer">         <!-- CONV-02: Footer -->

  <script> GSAP animations </script>
</body>
```

### Section Container Pattern

Every section uses the same container shell for consistency:

```html
<section id="{id}" class="py-[96px] bg-brand-bg">
  <div class="max-w-[1200px] mx-auto px-8">
    <!-- section content -->
  </div>
</section>
```

For alternate-surface sections (CONFIRM zone), use `bg-brand-surface` instead of `bg-brand-bg`.

### Pattern 1: Stagger-Reveal Animation (standard entrance)

For cards, grid items, list items — anything with multiple siblings:

```javascript
// Source: GSAP ScrollTrigger official docs + community verified pattern
gsap.fromTo(".section-animate",
  { opacity: 0, y: 40 },
  {
    opacity: 1, y: 0,
    duration: 0.8,
    stagger: 0.15,
    ease: "power2.out",
    scrollTrigger: {
      trigger: ".section-animate",
      start: "top 75%",
      toggleActions: "play none none none"
    }
  }
);
```

**When to use:** Educator grid cards, course topic items, testimonial cards, pricing tier cards.

### Pattern 2: Single Element Reveal (section headings, hero text)

```javascript
// Source: GSAP ScrollTrigger official docs
gsap.fromTo("#hero h1",
  { opacity: 0, y: 24 },
  {
    opacity: 1, y: 0,
    duration: 1.0,
    ease: "power2.out",
    scrollTrigger: {
      trigger: "#hero",
      start: "top 80%",
      toggleActions: "play none none none"
    }
  }
);
```

**When to use:** Hero headline (HERO-01), section headings, standalone manifesto blocks.

### Pattern 3: Hero — No ScrollTrigger (fires immediately on page load)

The hero is visible on load, not on scroll. Use a `DOMContentLoaded` tween without a scrollTrigger:

```javascript
document.addEventListener('DOMContentLoaded', () => {
  gsap.registerPlugin(ScrollTrigger);

  // Hero fires immediately, no trigger
  gsap.fromTo("#hero .hero-content",
    { opacity: 0, y: 32 },
    { opacity: 1, y: 0, duration: 1.0, ease: "power3.out", delay: 0.2 }
  );

  // All scroll-based animations follow...
});
```

### Anti-Patterns to Avoid

- **Hardcoded hex in class attributes:** Never write `bg-[#C9A84C]` — always `bg-brand-accent`
- **Font sizes outside the 4 declared sizes:** Only `text-[14px]`, `text-[16px]`, `text-[36px]`, `text-[56px]`
- **Font weights outside 400/600:** Never add `font-bold` (700) or `font-medium` (500)
- **Feature-count language in headlines:** Never "Access 350+ videos" — always outcome-first ("Build the skills that...")
- **Solution-first content in DEFINE zone:** The struggle and identity sections must name the problem before mentioning MTAM
- **Mismatched zone ordering:** PREPARE is reserved — do not insert content sections between LOCATE and CONFIRM

---

## JTBD Zone Content Specifications

This section is the primary research output for the planner. Each zone maps requirements to specific content.

### Zone 1: DEFINE (Define the goal and confirm the struggle)

**Purpose:** Visitor confirms this platform is for someone like them, facing their specific struggles.

**Framework applied:** Job Map Framework (Define step) + Four-Dimensional Job Analysis + Struggle Stack

**Sections:** hero, struggle, manifesto

---

#### HERO-01: Outcome-Based Hero Headline

The functional job for a hair stylist visiting MTAM is: *"Become skilled enough in extension techniques to confidently serve any client."*

The headline must describe what the stylist achieves (the outcome), not what the platform contains (the feature). The Outcome-Based Messaging Strategy framework states: take the unmet outcome, translate it into benefit-led copy that resolves it.

**Forbidden patterns (from ROADMAP success criteria):**
- "Access 350+ videos" — feature count
- "Get our extension course" — "Get + product noun"
- "Join MTAM" — identity/affiliation language with no outcome

**Approved pattern structure:** `[Result the stylist achieves] + [emotional qualifier or social context]`

**Recommended headline options (HIGH confidence — derived directly from JTBD outcome formula):**

Primary: `"Build extension skills that make clients request you by name"`
Alternative A: `"Master the techniques — without the gatekeeping"`
Alternative B: `"Learn hair extensions on your terms. No method loyalty required."`

**Planner should choose ONE.** Primary is recommended because it hits the functional job (build skills), the social job (client recognition = professional reputation), and the anti-gatekeeping brand in a single line.

---

#### HERO-02: Emotional Job Subheadline

The emotional jobs for the stylist are: *feel confident*, *not feel judged*, *feel like they belong* in professional education.

**Recommended subheadline:**
`"Straightforward extension education without the rigid rules, brand loyalty requirements, or judgment. Christine and Alex teach you the why — so you can make the decisions."`

This hits: confidence (no rules), emotional safety (no judgment), and functional outcome (make decisions = stylist agency).

---

#### HERO-03: CTA Button Copy

Confirmed from Phase 1 UI-SPEC and ROADMAP: `"Start Learning"` is the correct label. This is job-completion language (executing the job) not subscription language ("Subscribe," "Join," "Sign Up").

CTA placement: above the fold, immediately below the subheadline. Style: `bg-brand-accent text-brand-bg font-body font-semibold`.

---

#### HERO-04: Struggle Stack Section

**Framework applied:** Struggle Stack (Marketing Frameworks #13)

The Struggle Stack layers: Situational → Emotional → Functional → Time/Resource → Identity barriers.

**MTAM-specific struggle layers to name explicitly (before any solution content):**

| Layer | Specific Struggle to Name |
|-------|--------------------------|
| Situational | "You learned one method from one educator and now you can't serve clients who don't fit that method" |
| Emotional | "The education world feels like a velvet rope — expensive certifications, brand loyalty, and insider access" |
| Functional | "You know HOW to place extensions but not WHY certain techniques work for certain hair types" |
| Time/Resource | "Multi-day in-person certifications cost $2,000–$5,000+ per method — and you'd need 5 certifications to serve all clients" |
| Identity | "You're a working professional who should be able to learn without pledging loyalty to a brand or a founder's specific aesthetic" |

**Content approach:** Short punchy statements in a vertical "stack" layout (numbered or with accent line separators). Each statement names the struggle directly in second-person ("You..."). No solution content appears in this section.

**Headline for the section:** `"Sound familiar?"` or `"You're not the only one who's been here."`

---

#### HERO-05: Anti-Gatekeeping Manifesto Block

**Framework applied:** Four-Dimensional Job Analysis — Identity dimension (Framework #17 in Marketing Frameworks)

The identity job: *"Be seen as a skilled, independent professional who chose their technique based on merit, not brand loyalty."*

MTAM's founders Christine and Alex explicitly built the platform on this principle: teaching the "why" behind techniques so stylists can choose freely. This is the anti-gatekeeping position.

**Manifesto structure (named identity frustrations FIRST, philosophy second):**

```
Named frustrations (identity barriers):
- "Certifications that teach one brand's tools, not universal technique"
- "Educators who can't explain why — only how"
- "The unspoken rule that choosing one method means abandoning all others"

The MTAM position (philosophy, not pitch):
"We built MTAM on one belief: a skilled stylist understands the principles,
not just the steps. When you understand why a technique works,
you can adapt it for any client, any hair type, any situation.
That's not a method. That's mastery."
```

**Design treatment:** Full-width surface-colored section (`bg-brand-surface`), large DM Serif Display pull-quote centered, accent line decoration above.

---

### Zone 2: LOCATE (Gather the resources needed)

**Purpose:** Visitor locates the specific content, people, and origin story that makes MTAM the right source for them.

**Framework applied:** JTBD for IA (Information Architecture) — content organized by what the stylist needs to locate, not by platform structure.

**Sections:** topics (CONT-01), educator grid (CONT-02), founders (CONT-03)

---

#### CONT-01: Course Topics (Outcome Language)

**Framework applied:** Outcome-Based Messaging Strategy — rewrite feature descriptions into benefit-led copy.

**Real MTAM content areas (verified from morethanamethod.com):** The platform covers beaded rows, K-tips, V-light application, extension blend cutting, color work (lived-in blonding, color correction, brunette blonding, wrap highlighting), scalp science, business topics, social media.

**Outcome-language transformation:**

| Feature-count version (NEVER USE) | Outcome-language version (USE THIS) |
|------------------------------------|--------------------------------------|
| "Beaded rows courses" | "Master beaded row placement that stays secure and comfortable through client's entire wear cycle" |
| "K-tip videos" | "Build confidence applying K-tips across different hair textures and densities" |
| "Color education" | "Create the blonding results clients screenshot and bring in — without guessing at developer" |
| "Scalp science" | "Understand scalp health well enough to prevent damage and extend client appointment intervals" |
| "Business content" | "Price your extension services to reflect your actual skill level, not the industry average" |
| "Social media content" | "Build a client-attracting portfolio without hiring a photographer" |
| "Guest educator masterclasses" | "Learn the same techniques taught by the stylists behind the work you save on Instagram" |

**Layout recommendation:** 2-column or 3-column card grid. Each card: icon (Phosphor) + outcome headline + 1-sentence elaboration. Use `ph-check` (fill) as the icon to convey achievement/completion.

---

#### CONT-02: Educator Grid

**Verified educator data from morethanamethod.com/pages/mtam-guest-educators:**

| Name | Role/Specialization | Badge Label |
|------|--------------------|----|
| Christine Woods | Beaded rows, K-tips, color, social media | Founder + Lead Educator |
| Alex Denaro | K-tips, business topics | Co-Founder + Educator |
| Haley Evans | Beaded rows | Guest Educator |
| Yovanka Loria | Beaded rows + curls | Guest Educator |
| Stella Komi | V-light application | Guest Educator |
| Krista Bartik | Lived-in blonding | Guest Educator |
| Jaye Edwards | Color correction | Guest Educator |
| Anianne Rivera | Social media for stylists | Guest Educator |

**Layout:** 4-column grid at desktop. Each card: `bg-brand-surface rounded-[16px] p-6`, placeholder image block (`bg-brand-border` rectangle, ratio ~1:1 or 4:3), name in Manrope semibold, specialization in Manrope muted.

**Image placeholder pattern:**
```html
<div class="bg-brand-border rounded-[16px] w-full aspect-square mb-4 flex items-center justify-center">
  <i class="ph ph-user text-brand-muted text-[48px]"></i>
</div>
```

---

#### CONT-03: Founder Identity Section

**Framework applied:** JTBD Core Framework — the "struggle-origin narrative" establishes credibility by showing founders faced the same job.

**Content:** Christine Woods and Alex Denaro built MTAM because they experienced the same gatekeeping frustrations their students describe. The platform exists because of a belief that stylists deserve to understand technique principles, not just brand-specific steps.

**Copy approach:**
- Start with their own struggle ("Christine spent years being told there was one right way...")
- The inflection point ("...until she realized the 'right way' was just the method's way, not the technique's truth")
- The founding decision ("MTAM exists because every stylist deserves the why")

**Design treatment:** 2-column at desktop — left column: founders photo placeholder (large, `bg-brand-surface`), right column: heading + narrative paragraphs + small accent line divider. Not a hero — understated, editorial, personal.

---

### Zone 3: PREPARE (reserved — no content in v1)

Keep the placeholder comment. Do not add an HTML section. The PREPARE step maps to things like "set up your learning environment," "ensure your tools are ready" — out of scope for v1.

---

### Zone 4: CONFIRM (Verify this is the right decision before committing)

**Purpose:** Visitor verifies their decision — social proof and pricing confirm it's worth committing.

**Framework applied:** Customer Success Statement (CSS) Modeling for testimonials; Value Model Development for pricing framing.

**Sections:** testimonials (TRST-01), pricing (TRST-02, TRST-03)

---

#### TRST-01: Outcome-Based Testimonials

**Framework applied:** CSS Modeling — testimonials structured around practice changes, not platform compliments.

The CSS format: `[Action completed] + [Object] + [Context or Condition]`

**Anti-pattern (vanity testimonial — NEVER USE):**
*"MTAM is amazing! Christine is so inspiring! Best investment!"*

**Outcome-structured testimonial pattern (USE THIS):**
*"After six months in MTAM, I stopped turning away curly extension clients. Yovanka's beaded row technique for curls was the exact gap in my training I didn't know how to name."*

**Three recommended testimonial structures (planner should write these as realistic fabrications):**

1. **Practice change:** "I used to book installs 6 weeks apart because I wasn't confident in my removal process. After MTAM's scalp science modules, I extended that to 10 weeks and clients noticed the difference in their hair health."

2. **Identity shift:** "I had been method-certified twice and still felt like I was guessing. MTAM was the first education that made me feel like a technician instead of just a follower of steps."

3. **Business outcome:** "My extension pricing was based on what the salon down the street charged. After Alex's business modules, I raised my rates 40% and filled my books faster."

**Design:** 3-column testimonial cards at desktop. Each card: `bg-brand-surface rounded-[16px] p-6 border border-brand-border`. Top: star icons (`ph-fill ph-star text-brand-accent`). Quote in Manrope 16px/400. Attribution (first name, city) in Manrope 14px/muted.

---

#### TRST-02 + TRST-03: Pricing with Value Comparison

**Verified pricing data (from morethanamethod.com/join, confirmed 2026-03-30):**

| Tier | Price | Breakdown | Label |
|------|-------|-----------|-------|
| Monthly | $249.99/mo | $249.99/month | Explore |
| Quarterly | $549.99/qtr | ~$183/month | Commit |
| Annual | $1,250/year | ~$104/month | Master |

**Value comparison framing (TRST-03) — per-method certification anchor:**

The comparison must be anchored against what stylists currently pay for single-method certification. Industry data:
- In-person extension certification: typically $500–$2,500+ per method
- Multiple methods needed to serve all clients: 3–5 certifications = $1,500–$12,500+
- MTAM annual plan covers all methods, ongoing: $1,250/year

**Recommended framing language:**
`"One certification for one method typically costs $500–$2,500. MTAM gives you every method, every month, for less than $105."`

This is not "cheaper" language — it is VALUE COMPARISON language anchored to the opportunity cost of the alternative. The JTBD framework calls this "effort-focused market sizing" — measuring against the time, cost, and complexity the customer currently bears.

**Pricing section layout:**
- Headline: `"Stop paying per method. Learn all of them."` (outcome-based, anti-gatekeeping)
- 3 cards side by side: Monthly / Quarterly / Annual
- Middle card (Quarterly) gets "Most Popular" accent badge or border
- Value comparison call-out below the cards: small accent-colored callout box with the certification cost comparison

**Per-card content:**
```
[Tier name]
[Price large display]
[Monthly equiv if not monthly]
[Bullet list: same 5 benefits on all 3 cards]
[CTA button: "Start Learning"]
[Savings callout if applicable: "Save $X vs. monthly"]
```

All 3 tiers share the same feature list (they all give full access — the only difference is billing period and savings). This is correct for MTAM's actual offering.

---

### Zone 5: EXECUTE (Commit and take action)

**Purpose:** Visitor commits — they've confirmed the decision, now they act.

**Framework applied:** Customer Success Language Model — convert outcome statements into emotionally resonant CTAs.

**Sections:** final CTA (CONV-01), footer (CONV-02)

---

#### CONV-01: Final CTA Section

**Job-completion language rule:** The CTA must describe starting the job, not making a transaction. "Start Learning" executes the job. "Subscribe" makes a transaction. "Join" signals community. "Sign Up" signals admin.

**Confirmed CTA label:** `"Start Learning"` (established in Phase 1, confirmed in ROADMAP success criteria)

**Section structure:**
- Section heading (DM Serif Display, 56px): A single outcome statement or question that creates finality — `"Your next client shouldn't wait for you to find another course."` or `"The only technique that matters is the one that works for your client."`
- One sentence body: `"Start learning today. Cancel anytime."`
- Single prominent CTA button: `"Start Learning"` — large, `bg-brand-accent`, full-weight presence

**Design:** Center-aligned, full-width, `bg-brand-surface` for contrast after the pricing section. No icons, no lists — just the headline, one sentence, and the button. Maximum visual weight on the single action.

---

#### CONV-02: Footer

Minimal — three links only: Terms of Service, Contact, Copyright notice. No JTBD complexity required.

```html
<footer class="bg-brand-bg border-t border-brand-border py-8">
  <div class="max-w-[1200px] mx-auto px-8 flex items-center justify-between">
    <p class="font-body text-[14px] text-brand-muted">© 2024 MoreThanAMethod. All rights reserved.</p>
    <nav class="flex gap-8">
      <a href="#" class="font-body text-[14px] text-brand-muted hover:text-brand-text transition-colors">Terms</a>
      <a href="#" class="font-body text-[14px] text-brand-muted hover:text-brand-text transition-colors">Contact</a>
    </nav>
  </div>
</footer>
```

---

## Don't Hand-Roll

| Problem | Don't Build | Use Instead | Why |
|---------|-------------|-------------|-----|
| Scroll-driven fade-in animations | Custom CSS `animation-timeline: view()` | GSAP ScrollTrigger (already loaded) | Firefox requires a flag for CSS scroll-driven animations; GSAP works everywhere. ScrollTrigger is already registered. |
| Pricing toggle (monthly/annual switch) | Alpine.js `x-data` with JS toggle | Static 3-card layout | Requirements explicitly say scroll-only, no interactivity. A toggle is interactivity. Use static 3-column layout. |
| Image carousel/slider for testimonials | Any carousel library | 3-column grid, static | Out of scope (no interactivity). Static grid is more presentation-friendly — no clicking required for audience. |
| Custom icon font | SVG icons or hand-drawn | Phosphor Icons (already loaded) | Icons already available. `ph-check`, `ph-star`, `ph-user`, `ph-graduation-cap`, `ph-lightning`, `ph-users` cover all needed icons. |
| Responsive breakpoints | Media queries | None needed | Desktop-first for presentation screen. Mobile responsiveness is explicitly out of scope (v2 requirement RESP-01). |
| Smooth scroll anchor navigation | JS scroll handler | `scroll-behavior: smooth` (already on html element) | Already applied in Phase 1. |

**Key insight:** Every interactive pattern tempts over-building. This is a presentation demo shown on one screen to one audience. Static, beautiful, and predictable wins over interactive and risky.

---

## Common Pitfalls

### Pitfall 1: Solution Language in the DEFINE Zone
**What goes wrong:** A section that is supposed to name a struggle slips into mentioning MTAM or "our platform" before the struggle is fully acknowledged.
**Why it happens:** Copywriters instinctively pivot to the solution. The JTBD framework explicitly separates Define (confirm the goal/struggle) from Locate (find the resources).
**How to avoid:** Apply a hard rule — no brand name, no product noun, no price mention appears until the LOCATE zone. The DEFINE zone (hero, struggle, manifesto) names only the stylist and their situation.
**Warning signs:** Any sentence starting with "MTAM offers..." or "With our platform..." appearing in the hero or struggle sections.

### Pitfall 2: Feature-Count Headlines
**What goes wrong:** A section heading reads "350+ on-demand videos" or "12 guest educators."
**Why it happens:** Feature counts feel concrete and credible. But JTBD research shows customers don't hire products for feature counts — they hire for outcomes.
**How to avoid:** Rewrite any headline that contains a number + noun (quantity framing) into the result the student achieves. "350+ videos" → "Every technique you'll need to serve extension clients confidently." Test: would the headline still make sense if the number changed? If yes, the number isn't the value.
**Warning signs:** Any headline containing "+" (plus sign indicating quantity) or phrasing like "access to," "get," "includes."

### Pitfall 3: Testimonial Compliments Instead of CSS
**What goes wrong:** Testimonials read as platform endorsements ("Love MTAM!") rather than outcome descriptions.
**Why it happens:** Generic testimonial copy is easy to write. Outcome-structured testimonials require the writer to think from the student's job perspective.
**How to avoid:** Use the CSS format: what changed about their practice, their clients, their income, their confidence — in specific terms. Each testimonial should pass this test: "Could a competitor platform use this exact quote?" If yes, it's too generic.
**Warning signs:** Testimonials containing "amazing," "love," "best investment" without a specific practice change attached.

### Pitfall 4: Pricing Framing as Price-Point Listing
**What goes wrong:** The pricing section just lists $249/mo, $549/qtr, $1,250/yr with no anchoring.
**Why it happens:** Prices are the obvious content for a pricing section.
**How to avoid:** Anchor every price against the cost of the alternative: per-method certification ($500–$2,500+). The JTBD Value Model Development framework says: express value in measurable terms tied to the outcome cost of the current solution. The current solution (getting certified per-method) is expensive, time-consuming, and limits technique flexibility. MTAM is the better hire for the job.
**Warning signs:** Pricing section with no comparison reference, or comparison phrased as "cheaper than" (discount language) rather than "serves the whole job better than" (value language).

### Pitfall 5: Misusing Tailwind Arbitrary Values
**What goes wrong:** Arbitrary value hex colors appear in class attributes: `bg-[#C9A84C]`, `text-[#9ca3af]`.
**Why it happens:** Tailwind v4 allows arbitrary values; easy to reach for them under time pressure.
**How to avoid:** Always use the token utilities: `bg-brand-accent`, `text-brand-muted`. The @theme block already maps every needed color to a token. If a color isn't in the token system, it shouldn't be in the design.
**Warning signs:** Any class containing `[#` pattern.

### Pitfall 6: Hardcoding Font Sizes Outside the 4-Size System
**What goes wrong:** A section needs a "slightly larger" heading and gets `text-[24px]` or `text-[48px]`.
**Why it happens:** 36px feels too small for some headings, 56px feels too large.
**How to avoid:** Strictly enforce the 4 declared sizes: 14, 16, 36, 56. Use weight (400 vs 600) and color (text-brand-text vs text-brand-accent) to create hierarchy within those sizes, not new sizes.
**Warning signs:** Any text-[] class with a value other than 14px, 16px, 36px, 56px.

### Pitfall 7: Token Verification Block Not Removed
**What goes wrong:** Phase 2 sections are inserted after the token verification block, leaving it visible on the page.
**Why it happens:** It's easier to append sections than to surgically remove the verification block.
**How to avoid:** Make token verification block removal the FIRST action in Phase 2, before any section is added. The block is wrapped in `<!-- Phase 1: Token Verification Block (remove in Phase 2) -->` comment.
**Warning signs:** The page shows "Token Verification" heading above the hero.

---

## Code Examples

### Standard Section Shell

```html
<!-- Source: Phase 1 UI-SPEC container pattern, extended for Phase 2 -->
<section id="hero" class="py-[96px] bg-brand-bg">
  <div class="max-w-[1200px] mx-auto px-8">
    <!-- content here -->
  </div>
</section>
```

### Hero Headline + Sub + CTA

```html
<!-- Source: HERO-01, HERO-02, HERO-03 — outcome-based language + job-completion CTA -->
<div class="hero-content max-w-[800px]">
  <h1 class="font-display text-[56px] leading-[1.1] text-brand-text mb-6">
    Build extension skills that make clients request you by name
  </h1>
  <p class="font-body text-[16px] leading-[1.6] text-brand-muted mb-8 max-w-[560px]">
    Straightforward extension education without rigid rules, brand loyalty requirements, or judgment.
    Christine and Alex teach you the why — so you can make the decisions.
  </p>
  <button class="bg-brand-accent text-brand-bg font-body font-semibold text-[16px] px-8 py-4 rounded-[16px] cursor-pointer transition-colors duration-200 hover:bg-brand-accent-hover">
    Start Learning
  </button>
</div>
```

### Accent Section Divider

```html
<!-- Source: Phase 1 UI-SPEC accent usage: "section divider lines" -->
<div class="h-[2px] bg-brand-accent w-16 mb-8"></div>
```

### Educator Card

```html
<!-- Source: CONT-02 — educator grid card pattern -->
<div class="bg-brand-surface rounded-[16px] p-6 educator-card">
  <div class="bg-brand-border rounded-[16px] w-full aspect-square mb-4 flex items-center justify-center">
    <i class="ph ph-user text-brand-muted text-[48px]"></i>
  </div>
  <h3 class="font-body text-[16px] font-semibold text-brand-text">Haley Evans</h3>
  <p class="font-body text-[14px] text-brand-muted mt-1">Beaded rows techniques</p>
  <span class="inline-block mt-2 font-body text-[14px] text-brand-accent">Guest Educator</span>
</div>
```

### Testimonial Card

```html
<!-- Source: TRST-01 — CSS-modeled testimonial (practice change structure) -->
<div class="bg-brand-surface rounded-[16px] p-6 border border-brand-border testimonial-card">
  <div class="flex gap-1 mb-4">
    <i class="ph-fill ph-star text-brand-accent text-[16px]"></i>
    <i class="ph-fill ph-star text-brand-accent text-[16px]"></i>
    <i class="ph-fill ph-star text-brand-accent text-[16px]"></i>
    <i class="ph-fill ph-star text-brand-accent text-[16px]"></i>
    <i class="ph-fill ph-star text-brand-accent text-[16px]"></i>
  </div>
  <p class="font-body text-[16px] leading-[1.6] text-brand-text mb-4">
    "After six months in MTAM, I stopped turning away curly extension clients.
    Yovanka's beaded row technique for curls was the exact gap in my training
    I didn't know how to name."
  </p>
  <p class="font-body text-[14px] text-brand-muted">— Marisa, Atlanta</p>
</div>
```

### Pricing Card

```html
<!-- Source: TRST-02 — pricing tier card -->
<div class="bg-brand-surface rounded-[16px] p-8 border border-brand-border pricing-card">
  <h3 class="font-body text-[16px] font-semibold text-brand-text mb-2">Annual</h3>
  <div class="mb-2">
    <span class="font-display text-[56px] leading-[1.1] text-brand-text">$1,250</span>
    <span class="font-body text-[14px] text-brand-muted">/year</span>
  </div>
  <p class="font-body text-[14px] text-brand-accent mb-6">~$104/month — save $1,740 vs. monthly</p>
  <ul class="space-y-3 mb-8">
    <li class="flex items-start gap-3 font-body text-[14px] text-brand-text">
      <i class="ph-fill ph-check-circle text-brand-accent text-[16px] mt-[2px] shrink-0"></i>
      350+ on-demand extension trainings
    </li>
    <!-- additional list items -->
  </ul>
  <button class="w-full bg-brand-accent text-brand-bg font-body font-semibold text-[16px] py-4 rounded-[16px] cursor-pointer transition-colors duration-200 hover:bg-brand-accent-hover">
    Start Learning
  </button>
</div>
```

### GSAP ScrollTrigger Initialization Block

```javascript
// Source: GSAP ScrollTrigger official docs — section reveal patterns
// Place at end of <body>, replacing the Phase 1 console.log stub
document.addEventListener('DOMContentLoaded', () => {
  gsap.registerPlugin(ScrollTrigger);

  // Hero: fire on load, no scroll trigger
  gsap.fromTo(".hero-content",
    { opacity: 0, y: 32 },
    { opacity: 1, y: 0, duration: 1.0, ease: "power3.out", delay: 0.2 }
  );

  // Section headings: single reveal
  document.querySelectorAll(".section-heading").forEach(el => {
    gsap.fromTo(el,
      { opacity: 0, y: 24 },
      {
        opacity: 1, y: 0, duration: 0.8, ease: "power2.out",
        scrollTrigger: { trigger: el, start: "top 80%", toggleActions: "play none none none" }
      }
    );
  });

  // Cards and grid items: staggered reveal
  ["#educators .educator-card", "#topics .topic-card", ".testimonial-card", ".pricing-card"].forEach(selector => {
    gsap.fromTo(selector,
      { opacity: 0, y: 40 },
      {
        opacity: 1, y: 0, duration: 0.8, stagger: 0.15, ease: "power2.out",
        scrollTrigger: { trigger: selector, start: "top 75%", toggleActions: "play none none none" }
      }
    );
  });
});
```

---

## State of the Art

| Old Approach | Current Approach | When Changed | Impact |
|--------------|------------------|--------------|--------|
| `animation-timeline: view()` (CSS) | GSAP ScrollTrigger | Firefox support gap as of early 2026 | CSS scroll-driven animations require flag in Firefox; GSAP works everywhere — already in use |
| Feature-count homepage copy ("350+ videos") | Outcome-based messaging ("Build skills that...") | JTBD methodology, ongoing | Significant: outcome copy addresses what the visitor is hiring the platform to do |
| Single-method certification model | Multi-method subscription | Industry shift 2020–2024 | Enables the value comparison framing in TRST-03 |
| Tailwind v3 utility approach | Tailwind v4 @theme token system | Tailwind v4 released early 2025 | @theme means tokens auto-generate utilities; @utility required for font families (not auto-generated) |

---

## Open Questions

1. **Are placeholder images acceptable for educator cards, or should `placehold.co` be used?**
   - What we know: REQUIREMENTS.md says "placeholder imagery acceptable." Phase 1 UI-SPEC shows `bg-brand-border` with a Phosphor user icon as the pattern.
   - What's unclear: Does the presentation audience expect actual faces?
   - Recommendation: Use the Phase 1 pattern (`bg-brand-border` + `ph-user` icon). Keep it design-system-native. A `placehold.co` image introduces external dependency risk during the presentation.

2. **Should the hero include a background decorative element (subtle gradient, texture)?**
   - What we know: The design system is near-black with warm gold accent. The Phase 1 research noted glassmorphism and gradients as 2025 design trends.
   - What's unclear: Would a subtle radial gradient (`bg-brand-accent` at ~5% opacity as a circle behind the hero text) improve visual warmth?
   - Recommendation: Planner should decide. A single radial gradient adds warmth without adding dependencies. If chosen, use `style="background: radial-gradient(ellipse at 60% 50%, rgba(201,168,76,0.08), transparent 70%)"` inline on the hero section.

3. **How many testimonials?**
   - What we know: TRST-01 requires "outcome-based testimonials" (plural). The 3-column layout at desktop handles 3 naturally.
   - Recommendation: 3 testimonials, one per column, each representing a different outcome type (practice change, identity shift, business outcome).

4. **GSAP animation scope — which sections should be animated?**
   - What we know: GSAP ScrollTrigger is initialized. The stack decision locked GSAP as the animation library.
   - What's unclear: Animating everything can feel busy on a presentation screen.
   - Recommendation: Animate the hero (load-in), section headings (single reveal), and card grids (stagger reveal). Do NOT animate the manifesto block or pricing section — they should feel stable and authoritative, not performative.

---

## Environment Availability

Step 2.6: SKIPPED — Phase 2 is pure HTML content additions. No external tools, CLIs, runtimes, databases, or new CDN dependencies beyond what Phase 1 already established.

---

## Validation Architecture

`nyquist_validation` is set to `false` in `.planning/config.json`. Validation Architecture section omitted.

---

## Sources

### Primary (HIGH confidence)
- morethanamethod.com/join — verified pricing tiers ($249.99/mo, $549.99/qtr, $1,250/yr) fetched 2026-03-30
- morethanamethod.com/pages/mtam-guest-educators — verified educator names and specializations fetched 2026-03-30
- JTBD/Foundational Frameworks-20260330121422.md — Job Map Framework, CSS Modeling, ODI
- JTBD/Marketing Frameworks-20260330121414.md — Struggle Stack, Four-Dimensional Job Analysis, Outcome-Based Messaging Strategy, Customer Success Language Model
- JTBD/Design Team Framework Cheat Sheet-20260330121518.md — JTBD Anti-Vanity Framework, JTBD for IA, Job Step Mapping for UX
- .planning/phases/01-foundation/01-UI-SPEC.md — token system, spacing, typography constraints (locked from Phase 1)
- slideshows/mtam-homepage-demo.html — existing HTML structure confirmed

### Secondary (MEDIUM confidence)
- GSAP ScrollTrigger official docs (gsap.com/docs/v3/Plugins/ScrollTrigger/) — fade-in pattern with `fromTo`, `stagger`, `start: "top 75%"` — verified against multiple forum examples
- WebSearch: morethanamethod.com Google Play + Instagram — confirms Christine Woods founder, 350+ videos, anti-gatekeeping positioning (MEDIUM — search summary, not direct page fetch)

### Tertiary (LOW confidence)
- Industry certification cost range ($500–$2,500+ per method) — inferred from general hair extension industry knowledge and the MTAM value proposition framing on their site; no single authoritative price source. Treat as illustrative range, not cited fact.

---

## Project Constraints (from CLAUDE.md)

| Constraint | Implication for Phase 2 |
|------------|------------------------|
| Single self-contained HTML file — all CSS/JS inline, CDN-only | No new CDN dependencies. No separate .css or .js files. All section HTML goes into `slideshows/mtam-homepage-demo.html`. |
| Saved to `slideshows/` directory | File path unchanged from Phase 1. |
| No React/Vue/Svelte, no Webpack/Vite | Already enforced. Pure HTML + Tailwind utilities + vanilla GSAP. |
| No `@import` inside any `<style>` block | Already enforced in Phase 1. Do not add any new `<style>` blocks with `@import`. |
| No hardcoded hex in class attributes | All color references via token utilities (`bg-brand-accent`, not `bg-[#C9A84C]`). |
| Typography: 4 sizes only (14, 16, 36, 56px), 2 weights only (400, 600) | Enforced in all section HTML examples above. |
| GSAP ScrollTrigger for animations (not CSS animation-timeline) | GSAP is already loaded and registered. No CSS scroll animations. |
| Phosphor Icons for all icons | Use `ph` (regular) and `ph-fill` (fill) weight classes. |
| Desktop-first, scroll-only, no functional interactivity | Static layouts only. No tabs, toggles, accordions, or pricing calculators. |
| Must demonstrably apply JTBD principles | Every section maps to a named JTBD framework decision (documented in this research file, planner carries forward). |
| CDN dependency = venue internet required | Documented existing blocker in STATE.md. Phase 2 does not worsen this risk (no new CDN assets). |

---

## Metadata

**Confidence breakdown:**
- Standard stack: HIGH — locked from Phase 1, no new dependencies
- JTBD zone content: HIGH — derived directly from JTBD framework files in repo + verified MTAM data
- Educator data: HIGH — fetched directly from morethanamethod.com/pages/mtam-guest-educators 2026-03-30
- Pricing data: HIGH — fetched directly from morethanamethod.com/join 2026-03-30
- GSAP animation patterns: HIGH — official GSAP docs + community-verified; ScrollTrigger already functioning in Phase 1
- Outcome language patterns: HIGH — derived from JTBD Marketing Frameworks files in repo
- Certification cost comparison: LOW — range based on general industry knowledge, no authoritative single source

**Research date:** 2026-03-30
**Valid until:** 2026-04-30 for MTAM pricing (can change); JTBD framework content and tech stack are stable indefinitely.
