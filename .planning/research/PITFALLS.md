# Pitfalls Research

**Domain:** JTBD-driven homepage demo — single HTML file for business presentation
**Researched:** 2026-03-30
**Confidence:** HIGH (domain-specific; informed by JTBD reference materials and demo presentation patterns)

---

## Critical Pitfalls

### Pitfall 1: Vanity Design Overrides JTBD Rationale

**What goes wrong:**
The page looks polished and modern, but the design decisions were made aesthetically rather than job-driven. The demo fails its core mission: proving that AI + JTBD produces *intentional* design. If an audience member asks "why is this section here?" and the answer is "it looks good," the demo collapses. The Anti-Vanity Framework from the JTBD reference explicitly targets this: every element must support a functional or emotional job, or it must be cut.

**Why it happens:**
Designers and AI generation tools default to visual conventions ("hero with CTA, testimonials, features grid") because they've seen those patterns succeed aesthetically. Without a forcing mechanism, JTBD rationale gets bolted on after-the-fact rather than driving structure from the start. The result is a conventionally beautiful page with JTBD labels slapped on top — the opposite of what the demo must prove.

**How to avoid:**
Apply the Anti-Vanity Framework as the *first* step, not a post-build audit. Before placing any section on the page, require a one-sentence JTBD justification in the format: "This section exists because [job step] requires the visitor to [functional/emotional/social outcome]." If the justification can't be written, the section doesn't get built. The JTBD decision notes deliverable enforces this discipline.

**Warning signs:**
- Section ideas come from "what MTAM's competitors have" rather than job map steps
- Sections ordered for visual balance ("it needs something here") instead of job progression
- Copy starts with product features instead of customer outcomes
- The phrase "it just makes sense" appears in any design rationale without a JTBD reference

**Phase to address:**
Architecture/structure phase — before a single line of HTML is written, the section list must be derived from the job map (Define > Locate > Prepare > Confirm > Execute) and locked.

---

### Pitfall 2: Feature Language Masquerading as Outcome Language

**What goes wrong:**
Headlines and copy describe what MTAM offers ("300+ technique videos," "live Q&A sessions," "certification tracks") instead of what the stylist achieves. This is the most common JTBD copy failure. The Outcome-Based Messaging Strategy and Customer Success Language Model both address this directly: outcome language describes *progress the customer makes*, not capabilities the product provides. A demo using feature language will look indistinguishable from a non-JTBD site, undermining the entire presentation argument.

**Why it happens:**
Feature language is faster to write — it comes directly from the product. Outcome language requires the extra step of asking "so what does that enable for the customer?" Under time pressure, the shortcut is taken. AI generation tools also default to feature descriptions unless explicitly constrained.

**How to avoid:**
Run every headline and subheadline through the Four-Dimensional Job Analysis lens before finalizing copy. Functional job copy sounds like: "Go from uncertain technique choices to confident client consultations." Emotional job copy sounds like: "Learn without the judgment you've already experienced elsewhere." Social job copy sounds like: "Become the stylist clients recommend when someone asks who does the best extensions." If the copy could appear unchanged on the product spec sheet, it's feature language.

**Warning signs:**
- Any headline containing a number ("200+ videos")
- Any headline starting with "Access" or "Get" followed by a product noun
- Copy that describes the platform before it describes the stylist's transformation
- Absence of the words "you," "your," or direct second-person address in hero section

**Phase to address:**
Content/copy phase — requires explicit pass through Desired Outcome Statement Construction before writing begins, then a second pass using the Customer Success Language Model to transform those statements into emotionally resonant copy.

---

### Pitfall 3: Job Map Applied to Navigation, Not Page Structure

**What goes wrong:**
The JTBD Job Map (Define > Locate > Prepare > Confirm > Execute) gets applied as a *labeling exercise* — section headers are renamed with job map terminology, but the underlying page structure wasn't actually derived from job progression logic. The result is sections that say "Locate" but contain information relevant to "Confirm." This is a structural credibility failure: audience members familiar with JTBD will see through it immediately.

**Why it happens:**
It's easier to relabel an existing conventional homepage structure (hero, features, testimonials, pricing, CTA) than to rebuild it from the job map outward. The job map labels get applied as a veneer. The JTBD for IA framework in the design reference specifically warns against this: navigation and structure must be built around how customers approach the job, not retrofitted onto existing org or product hierarchy.

**How to avoid:**
Derive the section sequence from the job map *before* any layout decisions. The question for each section is: "At which job step does a hair stylist need this information to make progress?" A stylist in the Define step needs to understand what problem MTAM solves for them. A stylist in the Locate step needs to evaluate whether MTAM has the specific techniques they need. A stylist in the Confirm step needs social proof from peers, not founders. Each job step generates a page section requirement; sections don't come first and get labeled afterward.

**Warning signs:**
- Page section order matches a generic SaaS homepage template
- Social proof appears early (before the visitor has located what they need)
- Pricing or enrollment CTA appears before the visitor has confirmed fit
- Job map steps are used as section *titles* rather than as structural *logic*

**Phase to address:**
Architecture/structure phase — the section map document (JTBD decision notes deliverable) must be created before HTML is written, mapping each section to its job step and justifying the sequence.

---

### Pitfall 4: Emotional and Social Jobs Left Implicit

**What goes wrong:**
The page addresses the functional job (learn extension techniques) but leaves the emotional job (feel confident, not judged) and social job (be seen as a skilled professional) as subtext. These are explicitly called out in PROJECT.md as required, and the Four-Dimensional Job Analysis framework confirms they must be surfaced as distinct, explicit design elements — not buried in small body copy no one reads during a meeting. In a presentation demo, if the audience has to hunt for the emotional/social layer, it doesn't register.

**Why it happens:**
Functional job copy is concrete and easy to write. Emotional and social job language feels "soft" or risky to commit to explicitly. Developers and AI tools default to functional descriptions. The anti-gatekeeping and empowerment messaging that defines MTAM's brand identity lives entirely in the emotional/social layer — leaving it implicit means the brand essence gets stripped out.

**How to avoid:**
Allocate a dedicated design moment to each job dimension. The emotional job ("feel confident, not judged") should appear in the hero copy — not just the tagline. The social job ("be seen as a skilled professional by clients and peers") should appear in a section specifically addressing the transformation a stylist undergoes, not just in testimonial quotes. The Functional-Social-Emotional Job Alignment framework recommends auditing whether current design over-indexes on features vs. feelings and identity — this audit must happen before the demo is considered complete.

**Warning signs:**
- Hero copy describes what MTAM teaches, not how the stylist will feel
- No explicit reference to peer perception or professional credibility
- Testimonials selected for outcome results only, not emotional transformation language
- Anti-gatekeeping messaging appears only in small print or the about section

**Phase to address:**
Content/copy phase and design review — requires explicit check against Four-Dimensional Job Analysis and Functional-Social-Emotional Job Alignment before sign-off.

---

### Pitfall 5: Demo Tells the JTBD Story Instead of Showing It

**What goes wrong:**
The page includes explanatory text like "This section was designed using JTBD principles to address the Locate job step" — essentially annotating the framework rather than demonstrating it through execution. The goal of this demo is not to explain JTBD to the audience; it's to show a page so well-structured and purposeful that the JTBD framework's impact is self-evident. The separate JTBD decision notes document handles the explanation. The page itself must stand alone as evidence.

**Why it happens:**
When a demo is built to prove a methodology, there's a temptation to make the methodology visible on the artifact itself. This treats the audience as skeptics who need explanation rather than as people who can perceive intentional design when they see it. It also signals lack of confidence in the demo's persuasive power.

**How to avoid:**
Keep all JTBD annotations in the separate decision notes document. The HTML file must function as a legitimate homepage — someone unfamiliar with JTBD should find it credibly useful and well-organized. The framework's presence should be revealed during the meeting discussion, not embedded in the page. This is the demonstration of maturity: the method disappears into excellent execution.

**Warning signs:**
- Any visible framework terminology ("job step," "desired outcome") in user-facing copy
- Section headers that read like framework labels rather than customer-facing navigation
- Callout boxes explaining design rationale on the page itself
- Copy that talks *about* MTAM's approach to education rather than *demonstrating* it

**Phase to address:**
Final review phase — requires a "strip the scaffolding" pass where all visible methodology references are moved to the decision notes document.

---

### Pitfall 6: Single HTML File Becomes a Maintenance Liability During the Meeting

**What goes wrong:**
The file works perfectly in the builder's environment but fails during the presentation: fonts don't load (CDN blocked), icons are missing (wrong CDN link), or the page renders broken because the meeting laptop has a different screen resolution, OS, or browser. A broken demo in front of an audience is worse than no demo — it signals lack of preparation and undermines the AI + JTBD argument.

**Why it happens:**
Developers test on their own machine with stable internet. CDN dependencies (Google Fonts, icon libraries, image CDNs) are assumed to work. CSS that looks fine in Chrome on a 1440px monitor renders differently in a presentation browser on a 1080p laptop. No offline testing is done.

**How to avoid:**
Before the meeting, test the file by opening it on the presentation device (or a comparable machine) with WiFi disabled. If fonts and icons still load, they're either inlined or the CDN worked and assets were cached — either is acceptable. Prefer inlining critical CSS (fonts via base64 or system font fallbacks) over relying on external CDN availability. Use widely-supported system fonts as fallbacks. Test at the presentation screen's actual resolution (typically 1920x1080 at 100% browser zoom during a screenshare or direct connection).

**Warning signs:**
- External font CDN links without fallback font stacks
- Images loaded from external URLs rather than inline SVGs or base64
- Icon libraries loaded from CDN without offline fallback
- Page tested only on developer's own machine

**Phase to address:**
Pre-delivery testing phase — explicitly add "test offline on different resolution" to the definition of done for the HTML file.

---

### Pitfall 7: The Prompt List Document Reads Like a Log, Not a Narrative

**What goes wrong:**
The prompt list deliverable (one of three required artifacts) becomes a raw dump of every prompt used, with no structure or explanation. During the meeting, when someone asks "how did you use AI to build this?", the presenter hands them a 40-item list with no context. The prompt list is a demonstration artifact — it must show *why* each prompt was structured the way it was, making the AI + JTBD workflow legible to a non-technical audience.

**Why it happens:**
The prompt list feels like documentation, so it gets treated as an afterthought. It's built by copying prompts from the build session into a document. No editorial thought goes into what makes a prompt list persuasive as a presentation artifact.

**How to avoid:**
Structure the prompt list around the job map phases. Group prompts by which job step they were serving. Add a one-sentence annotation to each prompt explaining what JTBD decision informed the prompt's structure. The prompt list should tell a story: "We defined the job first, then used that to specify the copy, then used the copy requirements to specify the design." This is the methodology made visible — in the right place.

**Warning signs:**
- Prompt list created at the end of the build session from memory
- Prompts listed without grouping or annotations
- Prompts are generic ("make this look better") rather than outcome-specific
- No connection drawn between prompts and JTBD decisions

**Phase to address:**
Documentation phase — prompts must be written down *as they are used* during the build, with annotations added in the documentation phase before the meeting.

---

## Technical Debt Patterns

Shortcuts that seem reasonable but create long-term problems.

| Shortcut | Immediate Benefit | Long-term Cost | When Acceptable |
|----------|-------------------|----------------|-----------------|
| Using external CDN for fonts | Smaller file size | Breaks without internet; fails at meeting | Never for a meeting-critical file |
| Skipping JTBD decision notes until after build | Faster build time | Annotations become rationalization, not rationale — the notes lose their evidential value | Never — notes must be built alongside the page |
| Copy-pasting competitor homepage structure then relabeling | Quick section skeleton | Directly causes Pitfall 3 (job map as veneer) | Never — defeats the demo's purpose |
| Using placeholder copy ("lorem ipsum" or generic) | Saves time during layout | Kills demo credibility in a meeting; audience reads actual copy | Never for a presentation-ready file |
| Building mobile layout too | Thoroughness | Time cost with no presentation benefit; desktop-first is specified | Defer entirely per project scope |
| Using a CSS framework (Tailwind CDN) | Rapid styling | CDN dependency; adds load-time risk for meeting | Acceptable only if offline availability is verified first |

---

## Integration Gotchas

Common mistakes when connecting to external services. (This project has no backend integrations — section adapted for this demo's specific external dependencies.)

| Dependency | Common Mistake | Correct Approach |
|------------|----------------|------------------|
| Google Fonts | Linking to CDN without testing offline | Embed font as base64 data URI in `<style>` block, or use system font stack with close visual match |
| Heroicons / Phosphor Icons (CDN) | Relying on CDN availability | Use inline SVG for all icons, or test that CDN assets are fully cached before the meeting |
| External images (Unsplash, etc.) | Hotlinking to external image URLs | Use CSS gradient placeholders or base64-encoded images for any images critical to the layout |
| Browser autofill on "demo" form fields | Autofill styles overriding demo appearance | Disable or remove form fields entirely per project scope (no functionality required) |

---

## Performance Traps

This is a static single-HTML file demo — traditional performance traps (database queries, API latency) don't apply. Relevant traps for this context:

| Trap | Symptoms | Prevention | When It Breaks |
|------|----------|------------|----------------|
| Unoptimized inline images (base64) | File size > 5MB; slow initial load on presentation laptop | Compress images before base64 encoding; prefer CSS-based visuals over photographs | Any image larger than 200KB inline |
| Excessive CSS animations | Page feels sluggish; animations stutter during screenshare | Limit animations to `transition` properties; avoid JavaScript-based animation; test during screenshare specifically | Common during screenshare due to frame rate reduction |
| Too many inline `<script>` blocks | Code conflicts; unexpected behavior | Keep all JS in a single consolidated block at bottom of `<body>` | When multiple AI generation passes each add their own script block |

---

## UX Pitfalls

| Pitfall | User Impact (Presentation Context) | Better Approach |
|---------|-------------------------------------|-----------------|
| Visual hierarchy that buries the core value proposition | Meeting attendees see design, not message — demo fails to communicate what MTAM does within 5 seconds | Primary headline must state the transformation (emotional job outcome), secondary headline adds context; nothing visual should compete with this on first load |
| Scroll-jacking or scroll-triggered animations | Presenters can't control scroll speed; demo becomes awkward to navigate | No scroll-jacking; smooth native scroll only |
| Dark text on image backgrounds without sufficient contrast | Hard to read on projected screens, which lose contrast vs. monitors | Test all text-on-image combinations at WCAG AA minimum; presentation screens are unforgiving |
| CTA buttons that look like links | Audience doesn't perceive urgency or action point during the walkthrough | CTAs must be clearly button-shaped with strong color contrast — they are the "proof" that the page drives action |
| Section length mismatched to job step importance | Execute step (the core value) gets the same visual weight as a minor Locate section | Weight sections visually proportional to their job step importance — the core job delivery gets the most space |

---

## "Looks Done But Isn't" Checklist

Items that appear complete but are missing critical pieces specific to this demo.

- [ ] **JTBD Decision Notes:** HTML page is complete, but the decision notes document hasn't been written — verify a separate, readable document maps each section to its job step with rationale
- [ ] **Prompt List:** Page is complete, but prompts weren't documented during the build — verify the prompt list exists as a separate document, not reconstructed from memory
- [ ] **Offline functionality:** Page renders correctly in the browser — verify it also renders correctly with WiFi disabled on the presentation device
- [ ] **Outcome language audit:** Copy is written — verify no headline describes a product feature; every headline describes a customer outcome or transformation
- [ ] **Three-job coverage:** Functional job language is present — verify emotional job (feel confident, not judged) and social job (be seen as a skilled professional) are *explicitly* present in the page, not just implied
- [ ] **Anti-vanity audit:** All sections are present — verify each section has a one-sentence JTBD justification in the decision notes; no section exists for aesthetic balance alone
- [ ] **Scroll test:** Layout looks good in a static screenshot — verify it flows correctly when scrolled from top to bottom without layout breaks
- [ ] **MTAM brand voice:** Copy is complete — verify the anti-gatekeeping, empowerment tone is present; page doesn't sound like generic education platform copy

---

## Recovery Strategies

When pitfalls occur despite prevention, how to recover.

| Pitfall | Recovery Cost | Recovery Steps |
|---------|---------------|----------------|
| Vanity design overrides JTBD rationale (discovered during review) | MEDIUM | Apply Anti-Vanity Framework audit: list all sections, demand one-sentence JTBD justification for each, remove or rewrite sections that fail the test; copy pass to shift feature language to outcome language |
| Feature language in copy (discovered during review) | LOW | Targeted copy pass using Desired Outcome Statement Construction — rewrite each headline using [Direction + Metric + Object + Context] format, then apply Customer Success Language Model to make it emotionally resonant |
| Job map as veneer (discovered late in build) | HIGH | Requires structural rebuild — section order and section existence must be rederived from job map; cannot be fixed with copy alone; this is why the architecture phase must precede the build phase |
| File fails offline at the meeting | HIGH (time-critical) | Immediate: open cached browser version if available; use screenshots as fallback in slide deck; long-term: rebuild with all fonts/icons inlined |
| Prompt list not documented during build | MEDIUM | Reconstruct from memory + conversation history immediately after build; annotate with intended JTBD rationale; quality will be lower than real-time documentation but still usable as a presentation artifact |
| JTBD decision notes not written | MEDIUM | Write retrospectively using the Anti-Vanity Framework process: for each section, write the job step it addresses, the functional/emotional/social job dimension it serves, and the outcome it enables |

---

## Pitfall-to-Phase Mapping

How roadmap phases should address these pitfalls.

| Pitfall | Prevention Phase | Verification |
|---------|------------------|--------------|
| Vanity design overrides JTBD rationale | Architecture phase (pre-build) | Every section in the section map has a written JTBD justification before HTML begins |
| Feature language in copy | Content/copy phase | Every headline reviewed against Outcome Statement Construction formula; no feature nouns in hero copy |
| Job map as veneer | Architecture phase (pre-build) | Section sequence derived from job map steps, not from template; sequence rationale documented |
| Emotional/social jobs left implicit | Content/copy phase + design review | Four-Dimensional Job Analysis checklist completed; emotional and social job language explicitly present on page |
| Demo tells the story instead of showing it | Final review phase | All framework terminology removed from user-facing copy; moved to decision notes document |
| Single HTML file fails at meeting | Pre-delivery testing phase | File tested offline on presentation-resolution screen; all assets load without internet |
| Prompt list reads like a log | Documentation phase (during build) | Prompts written down in real-time during build with JTBD annotation; structured by job map phase |

---

## Sources

- JTBD Anti-Vanity Framework (Design Team Framework Cheat Sheet) — primary source for Pitfall 1
- Four-Dimensional Job Analysis and Functional-Social-Emotional Job Alignment (Marketing Frameworks) — primary source for Pitfall 4
- JTBD for IA (Design Team Framework Cheat Sheet; Marketing Frameworks) — primary source for Pitfall 3
- Outcome-Based Messaging Strategy + Customer Success Language Model (Marketing Frameworks) — primary source for Pitfall 2
- Job Map Framework (Foundational Frameworks; Design Team Framework Cheat Sheet) — cross-referenced for Pitfalls 1, 3, 7
- PROJECT.md — three-job requirement, deliverable list, presentation context
- Pattern: presentation demo failure modes (offline dependency, copy substitution under time pressure, annotation temptation) — domain knowledge, HIGH confidence from recurring patterns in demo/prototype build contexts

---
*Pitfalls research for: JTBD-driven homepage demo (MoreThanAMethod.com, STYSTS Chennai presentation)*
*Researched: 2026-03-30*
