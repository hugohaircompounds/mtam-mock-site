# Phase 1: Foundation - Research

**Researched:** 2026-03-30
**Domain:** Static HTML file scaffolding — CDN stack loading, CSS design tokens, desktop layout baseline
**Confidence:** HIGH

---

## Summary

Phase 1 is a pure scaffold phase: create a single `.html` file at `slideshows/mtam-homepage-demo.html` with all CDN assets loaded, brand design tokens defined in `:root` and `@theme`, and a visible token verification block that proves the system works. No section content is built. The file must open by double-click with zero console errors.

The technical domain is well-understood and low-risk. All four CDN packages have been verified live against jsDelivr as of 2026-03-30. The only meaningful pitfall is Tailwind v4's `@theme` color naming convention — custom color token names in `@theme` map directly to class names, so `--color-brand-accent` generates `bg-brand-accent`, `text-brand-accent`, etc. This is consistent with the UI-SPEC's naming scheme and requires no correction.

The `slideshows/` directory does not yet exist and must be created before the file can be saved there. This is a one-step file system operation, not a blocker.

**Primary recommendation:** Follow the UI-SPEC CDN load order exactly, define tokens in both `:root` (for vanilla CSS `var()` usage) and a `<style type="text/tailwindcss">` `@theme` block (for Tailwind utilities), then render a token demo block in `<body>` that is removed in Phase 2.

---

<phase_requirements>
## Phase Requirements

| ID | Description | Research Support |
|----|-------------|------------------|
| STRC-01 | Page sections follow JTBD Job Map order: Define > Locate > Prepare > Confirm > Execute | Scaffold only in Phase 1 — section structure placeholder comments establish the order; actual sections built in Phase 2 |
| STRC-02 | Single self-contained HTML file with all CSS/JS inline (CDN-loaded fonts/icons only) | Verified: Tailwind v4 Play CDN, GSAP, Phosphor Icons, Google Fonts all load via CDN tags only — no local assets required |
| STRC-03 | File saved to `slideshows/` directory | Directory does not yet exist — must be created; file path is `slideshows/mtam-homepage-demo.html` |
| STRC-04 | Desktop-first layout optimized for presentation screen viewing | UI-SPEC specifies `max-w-[1200px] mx-auto px-8`, `overflow-x: hidden` on body, target 1440x900px |
| DSGN-01 | Polished, presentation-ready visual design with modern typography | Design token block with all fonts, colors, and spacing applied — visually verifies the system before Phase 2 content |
| DSGN-02 | MTAM brand essence retained (professional, approachable, empowerment-focused) | Token colors (#0f0f0f near-black, #C9A84C warm gold) and DM Serif Display + Manrope pairing established in scaffold |
| DSGN-03 | Smooth scroll behavior and visual hierarchy supporting job progression | `scroll-behavior: smooth` on `<html>` applied in scaffold; GSAP ScrollTrigger initialized for Phase 2 animation hooks |
| DSGN-04 | Black/white base aesthetic with warm accent color | Token system defines `--color-bg: #0f0f0f`, `--color-accent: #C9A84C` — verified visually in token demo block |
</phase_requirements>

---

## Project Constraints (from CLAUDE.md)

### Required Conventions
- Single self-contained HTML file — all CSS/JS inline, CDN-loaded fonts/icons only (no build step)
- File must be saved to `slideshows/` directory so it can be clicked during a presentation
- Must demonstrably apply JTBD principles
- No React, Vue, Svelte, Webpack, or Vite
- No `@import` inside `<style>` blocks — use `<link>` tags with `preconnect` hints

### Required Stack (locked — do not substitute)
- Tailwind CSS: `@tailwindcss/browser@4` (Play CDN)
- Icons: `@phosphor-icons/web@2.1.2` (regular + fill weights)
- Animation: `gsap@3.14.2` + `ScrollTrigger`
- Fonts: DM Serif Display (display) + Manrope 400/600 (body/UI) via Google Fonts

### Forbidden Patterns
- `CSS animation-timeline: view()` — Firefox incompatibility
- `Google Fonts @import` inside CSS — use `<link>` preconnect instead
- AOS as primary animation (adequate, not polished — use GSAP)
- Bootstrap, Pico, Bulma as CSS framework alternatives
- Any external image hosting you don't control during presentation
- Any `<link>` or `<script>` pointing to assets that could 404 during the presentation (prefer pinned CDN versions)

### CDN Load Order (mandatory — do not reorder)
1. Google Fonts preconnect + stylesheet
2. Phosphor Icons CSS (regular weight, then fill weight)
3. Tailwind v4 Play CDN script
4. `<style type="text/tailwindcss">` with `@theme` block
5. GSAP core script
6. GSAP ScrollTrigger script

---

## Standard Stack

### Core (all versions verified live against jsDelivr 2026-03-30)

| Library | Version | CDN URL | Status |
|---------|---------|---------|--------|
| @tailwindcss/browser | `@4` (resolves to 4.2.2 latest) | `https://cdn.jsdelivr.net/npm/@tailwindcss/browser@4` | HTTP 200 verified |
| gsap | 3.14.2 (latest) | `https://cdn.jsdelivr.net/npm/gsap@3.14.2/dist/gsap.min.js` | HTTP 200 verified |
| gsap ScrollTrigger | 3.14.2 | `https://cdn.jsdelivr.net/npm/gsap@3.14.2/dist/ScrollTrigger.min.js` | HTTP 200 verified |
| @phosphor-icons/web (regular) | 2.1.2 (latest) | `https://cdn.jsdelivr.net/npm/@phosphor-icons/web@2.1.2/src/regular/style.css` | HTTP 200 verified |
| @phosphor-icons/web (fill) | 2.1.2 (latest) | `https://cdn.jsdelivr.net/npm/@phosphor-icons/web@2.1.2/src/fill/style.css` | HTTP 200 verified |
| Google Fonts | current | `https://fonts.googleapis.com/css2?family=DM+Serif+Display:ital@0;1&family=Manrope:wght@400;600&display=swap` | Service active |

**Version note:** The UI-SPEC references `@tailwindcss/browser@4` as a floating tag. jsDelivr resolves `@4` to the latest v4.x release (currently 4.2.2). The floating tag is acceptable for a presentation demo — it will always pull the latest v4. If version stability is required, pin to `@tailwindcss/browser@4.2.2`.

**Installation:** No npm install. All dependencies are CDN-only. The HTML file IS the installation.

---

## Architecture Patterns

### Recommended File Structure

```
slideshows/
└── mtam-homepage-demo.html    ← the entire deliverable

(Directory must be created — does not exist yet)
```

### HTML Document Skeleton

The complete scaffold has this internal structure:

```html
<!doctype html>
<html lang="en" style="scroll-behavior: smooth;">
<head>
  <meta charset="UTF-8">
  <meta name="viewport" content="width=device-width, initial-scale=1.0">
  <title>MoreThanAMethod — Learn Hair Extension Techniques That Build Your Career</title>
  <meta name="description" content="Education for hair stylists who are done guessing. JTBD-designed curriculum for technique mastery and client confidence.">

  <!-- 1. Fonts -->
  <link rel="preconnect" href="https://fonts.googleapis.com">
  <link rel="preconnect" href="https://fonts.gstatic.com" crossorigin>
  <link href="https://fonts.googleapis.com/css2?family=DM+Serif+Display:ital@0;1&family=Manrope:wght@400;600&display=swap" rel="stylesheet">

  <!-- 2. Icons -->
  <link rel="stylesheet" href="https://cdn.jsdelivr.net/npm/@phosphor-icons/web@2.1.2/src/regular/style.css">
  <link rel="stylesheet" href="https://cdn.jsdelivr.net/npm/@phosphor-icons/web@2.1.2/src/fill/style.css">

  <!-- 3. Tailwind v4 Play CDN -->
  <script src="https://cdn.jsdelivr.net/npm/@tailwindcss/browser@4"></script>

  <!-- 4. @theme extension (must follow Tailwind script) -->
  <style type="text/tailwindcss">
    @theme {
      --color-brand-bg:           #0f0f0f;
      --color-brand-surface:      #1a1a1a;
      --color-brand-border:       #2a2a2a;
      --color-brand-text:         #f5f5f5;
      --color-brand-muted:        #9ca3af;
      --color-brand-accent:       #C9A84C;
      --color-brand-accent-hover: #b8953e;
      --font-display: 'DM Serif Display', serif;
      --font-body:    'Manrope', sans-serif;
      --radius-card:  16px;
    }
  </style>

  <!-- 5-6. GSAP -->
  <script src="https://cdn.jsdelivr.net/npm/gsap@3.14.2/dist/gsap.min.js"></script>
  <script src="https://cdn.jsdelivr.net/npm/gsap@3.14.2/dist/ScrollTrigger.min.js"></script>
</head>
<body style="background-color: var(--color-brand-bg, #0f0f0f); overflow-x: hidden;">

  <!-- TOKEN VERIFICATION BLOCK (removed in Phase 2) -->
  <!-- SECTION PLACEHOLDER COMMENTS in JTBD Job Map order -->

  <script>
    document.addEventListener('DOMContentLoaded', () => {
      gsap.registerPlugin(ScrollTrigger);
    });
  </script>
</body>
</html>
```

### Pattern 1: Dual Token System (`:root` + `@theme`)

**What:** Define every brand token twice — once in a `:root` block for vanilla CSS `var()` usage, once in a Tailwind `@theme` block to generate Tailwind utility classes.

**When to use:** Always in this project. The two systems coexist and complement each other. `:root` variables work in inline `style` attributes and regular `<style>` CSS. `@theme` generates utility classes like `bg-brand-accent` and `text-brand-muted`.

**Example:**
```html
<!-- Source: Tailwind v4 official docs — https://tailwindcss.com/docs/installation/play-cdn -->
<style>
  :root {
    --color-bg:     #0f0f0f;
    --color-accent: #C9A84C;
    --font-display: 'DM Serif Display', serif;
    --font-body:    'Manrope', sans-serif;
    --radius-card:  16px;
    --shadow-card:  0 4px 32px rgba(0, 0, 0, 0.4);
  }
</style>

<style type="text/tailwindcss">
  @theme {
    --color-brand-bg:     #0f0f0f;
    --color-brand-accent: #C9A84C;
  }
  /* Generates: bg-brand-bg, bg-brand-accent, text-brand-accent, etc. */
</style>
```

### Pattern 2: Token Verification Block

**What:** A visible HTML section inside `<body>` that renders swatches for every color token, both font families, and a sample of the spacing scale. It has no content value — its sole purpose is to confirm the token system works before Phase 2 begins. It is explicitly removed in Phase 2.

**When to use:** Phase 1 only. Satisfies success criterion 2 ("changing one token updates the whole page").

**Example:**
```html
<!-- TOKEN VERIFICATION BLOCK — remove in Phase 2 -->
<section style="padding: 64px 32px; background-color: var(--color-bg);">
  <div class="max-w-[1200px] mx-auto">
    <h2 style="font-family: var(--font-display); font-size: 36px; color: var(--color-text-primary);">
      Token Verification
    </h2>
    <!-- Color swatches, font samples, spacing demo -->
  </div>
</section>
```

### Pattern 3: JTBD Job Map Section Placeholder Comments

**What:** Comment markers in `<body>` for each Job Map stage in order. Phase 2 replaces these comments with actual section HTML.

**Example:**
```html
<!-- JOB MAP: DEFINE — Hero, Struggle Stack, Anti-gatekeeping manifesto -->
<!-- JOB MAP: LOCATE — Course topics, Educator grid, Founder identity -->
<!-- JOB MAP: PREPARE — (not used) -->
<!-- JOB MAP: CONFIRM — Testimonials, Pricing, Value comparison -->
<!-- JOB MAP: EXECUTE — Final CTA, Footer -->
```

This satisfies STRC-01 at the scaffold level — the order is established before any content is written, which STATE.md flags as "HIGH recovery cost if violated."

### Anti-Patterns to Avoid

- **Mixing token naming conventions:** Do not use both `--color-accent` in `:root` and `--color-brand-accent` in `@theme` for different values. Keep hex values identical in both systems.
- **Using arbitrary hex values in class attributes:** `class="bg-[#C9A84C]"` is a Tailwind escape hatch that bypasses the token system. Use `class="bg-brand-accent"` instead so changing the token propagates everywhere.
- **Tailwind `@import` inside `<style type="text/tailwindcss">`:** The Tailwind browser bundle handles compilation — adding `@import "tailwindcss"` causes errors. Only use `@theme`, `@layer`, or `@utility` directives inside the typed style block.
- **Loading GSAP before Tailwind:** GSAP scripts can be deferred but must come after Tailwind to avoid a race condition where GSAP fires before Tailwind finishes compiling classes.
- **Hardcoding `font-family` in Tailwind classes:** Tailwind v4 does not generate `font-display` or `font-body` utilities from `@theme` font tokens by default. Use `style="font-family: var(--font-display)"` or create a `@utility` rule for it.

---

## Don't Hand-Roll

| Problem | Don't Build | Use Instead | Why |
|---------|-------------|-------------|-----|
| CSS utility classes | Custom `<style>` block with `.card`, `.btn` etc. | Tailwind utilities | Tailwind generates hundreds of pre-tested utilities; hand-rolling duplicates the work and diverges from the token system |
| Scroll animations | `window.addEventListener('scroll', ...)` | GSAP ScrollTrigger | Scroll math, threshold detection, and mobile performance are all solved by ScrollTrigger; hand-rolling creates stuttering bugs |
| Icon rendering | Inline SVG markup for every icon | Phosphor Icons font | Icon fonts render at any size and color with a single CSS class; inline SVG duplicates bytes and requires manual color updates |
| Font loading | Self-hosted font files in the HTML | Google Fonts CDN link | Browser cache sharing, globally distributed CDN, `font-display: swap` included automatically |

**Key insight:** Every hand-rolled solution in this domain adds bytes to the single HTML file, diverges from the token system, and introduces bugs that have already been solved. The CDN stack IS the answer — the scaffold phase's job is to load it correctly, not add to it.

---

## Common Pitfalls

### Pitfall 1: Font utilities not generated from @theme font tokens
**What goes wrong:** Defining `--font-display: 'DM Serif Display', serif` in `@theme` does NOT automatically generate a `font-display` utility class in Tailwind v4. Attempting to use `class="font-display"` produces no styling.
**Why it happens:** Tailwind v4 generates utilities for `--color-*`, `--spacing-*`, `--radius-*`, and `--shadow-*` namespaces by default. Font tokens in `--font-*` generate utilities only if explicitly configured.
**How to avoid:** Use inline `style="font-family: var(--font-display)"` on elements that need the display font, or add a `@utility font-display { font-family: var(--font-display); }` block inside the `<style type="text/tailwindcss">` tag.
**Warning signs:** `font-display` class applied to an element but font does not change from browser default.

### Pitfall 2: Tailwind v4 `@theme` color names become utility class names verbatim
**What goes wrong:** `--color-brand-accent` in `@theme` generates `bg-brand-accent`, `text-brand-accent` — NOT `bg-accent` or `text-brand`. The full token name after `--color-` is the class name.
**Why it happens:** Tailwind v4 maps `--color-{name}` directly to `{name}` in utility classes. There is no stripping of prefixes.
**How to avoid:** This is the correct behavior — the UI-SPEC uses `brand-accent`, `brand-bg`, etc. as the class names intentionally. Be consistent: always use the full `brand-*` prefix in class attributes.
**Warning signs:** Background or text color not applying when using short names like `bg-accent`.

### Pitfall 3: slideshows/ directory does not exist
**What goes wrong:** Attempting to save the file to `slideshows/mtam-homepage-demo.html` fails because the directory has not been created.
**Why it happens:** The directory is specified in requirements but was never created in the repo.
**How to avoid:** Create the directory as the first step in execution. In a task plan, this must be Wave 0 / Task 1 before any file writing.
**Warning signs:** File save fails, or file is accidentally saved to the project root.

### Pitfall 4: Tailwind Play CDN console warning treated as error
**What goes wrong:** The Tailwind Play CDN prints a console warning: "cdn.tailwindcss.com should not be used in production." This is surfaced in DevTools and may cause confusion during verification.
**Why it happens:** Tailwind deliberately warns about production CDN usage. The warning is informational, not an error.
**How to avoid:** Document this as expected behavior. The Phase 1 success criterion says "no console errors" — this warning is not an error (it appears as a `warn`, not an `error`). Note it in the plan's verification step.
**Warning signs:** Checking console for errors and flagging this warning as a failure.

### Pitfall 5: GSAP ScrollTrigger not registered before Phase 2 animations
**What goes wrong:** GSAP loads but ScrollTrigger-based animations in Phase 2 silently fail or throw errors because `gsap.registerPlugin(ScrollTrigger)` was never called.
**Why it happens:** ScrollTrigger is a plugin — it must be explicitly registered before use.
**How to avoid:** Include `gsap.registerPlugin(ScrollTrigger)` inside the `DOMContentLoaded` listener in Phase 1's inline script block. Phase 2 can then add animations without re-registering.
**Warning signs:** Phase 2 `.scrollTrigger` options on animations have no effect; console may show "ScrollTrigger is not defined."

### Pitfall 6: `overflow-x: hidden` on `<body>` applied too late
**What goes wrong:** Without `overflow-x: hidden`, some Tailwind utility classes (especially negative margins or full-width elements) cause horizontal scroll on the presentation screen.
**Why it happens:** Default browser behavior allows content to overflow the viewport horizontally.
**How to avoid:** Apply `overflow-x: hidden` to `<body>` inline in Phase 1, before any section content is added in Phase 2.
**Warning signs:** Horizontal scrollbar appears in browser on the scaffold page.

---

## Code Examples

### Complete Head Block (verified against official sources)
```html
<!-- Source: Tailwind official docs https://tailwindcss.com/docs/installation/play-cdn -->
<!-- Source: jsDelivr package pages (all URLs HTTP 200 verified 2026-03-30) -->

<!-- Fonts -->
<link rel="preconnect" href="https://fonts.googleapis.com">
<link rel="preconnect" href="https://fonts.gstatic.com" crossorigin>
<link href="https://fonts.googleapis.com/css2?family=DM+Serif+Display:ital@0;1&family=Manrope:wght@400;600&display=swap" rel="stylesheet">

<!-- Icons: Phosphor 2.1.2 — regular + fill only (2 weights) -->
<link rel="stylesheet" href="https://cdn.jsdelivr.net/npm/@phosphor-icons/web@2.1.2/src/regular/style.css">
<link rel="stylesheet" href="https://cdn.jsdelivr.net/npm/@phosphor-icons/web@2.1.2/src/fill/style.css">

<!-- Tailwind v4 Play CDN (compiles in-browser, scans DOM for classes) -->
<script src="https://cdn.jsdelivr.net/npm/@tailwindcss/browser@4"></script>

<!-- @theme block — must follow Tailwind script, must use type="text/tailwindcss" -->
<style type="text/tailwindcss">
  @theme {
    --color-brand-bg:           #0f0f0f;
    --color-brand-surface:      #1a1a1a;
    --color-brand-border:       #2a2a2a;
    --color-brand-text:         #f5f5f5;
    --color-brand-muted:        #9ca3af;
    --color-brand-accent:       #C9A84C;
    --color-brand-accent-hover: #b8953e;
    --font-display: 'DM Serif Display', serif;
    --font-body:    'Manrope', sans-serif;
    --radius-card:  16px;
  }

  /* Font utility classes (not auto-generated from --font-* tokens) */
  @utility font-display {
    font-family: var(--font-display);
  }
  @utility font-body {
    font-family: var(--font-body);
  }
</style>

<!-- GSAP + ScrollTrigger -->
<script src="https://cdn.jsdelivr.net/npm/gsap@3.14.2/dist/gsap.min.js"></script>
<script src="https://cdn.jsdelivr.net/npm/gsap@3.14.2/dist/ScrollTrigger.min.js"></script>
```

### GSAP Initialization Pattern
```html
<!-- Source: GSAP ScrollTrigger docs https://gsap.com/docs/v3/Plugins/ScrollTrigger/ -->
<!-- Place at end of <body>, after all content -->
<script>
  document.addEventListener('DOMContentLoaded', () => {
    gsap.registerPlugin(ScrollTrigger);
    // Phase 2 animations added here
  });
</script>
```

### `:root` CSS Custom Properties Block
```css
/* Source: UI-SPEC.md (approved 2026-03-30) */
/* Place inside a <style> tag in <head>, before Tailwind script */
:root {
  /* Surfaces */
  --color-bg:           #0f0f0f;
  --color-surface:      #1a1a1a;
  --color-border:       #2a2a2a;

  /* Text */
  --color-text-primary: #f5f5f5;
  --color-text-muted:   #9ca3af;

  /* Accent */
  --color-accent:       #C9A84C;
  --color-accent-hover: #b8953e;

  /* Typography */
  --font-display: 'DM Serif Display', serif;
  --font-body:    'Manrope', sans-serif;

  /* Elevation */
  --radius-card:  16px;
  --shadow-card:  0 4px 32px rgba(0, 0, 0, 0.4);
  --shadow-deep:  0 8px 48px rgba(0, 0, 0, 0.6);
}
```

### Phosphor Icon Usage Pattern
```html
<!-- Regular weight icon -->
<i class="ph ph-arrow-right"></i>

<!-- Fill weight icon (requires fill CSS loaded) -->
<i class="ph-fill ph-star"></i>

<!-- Sized via font-size -->
<i class="ph ph-check" style="font-size: 24px; color: var(--color-accent);"></i>
```

---

## State of the Art

| Old Approach | Current Approach | When Changed | Impact |
|--------------|------------------|--------------|--------|
| Tailwind config file (`tailwind.config.js`) | `@theme` block in CSS | Tailwind v4 (Jan 2025) | No JS config file needed; theme defined in CSS |
| `theme.extend.colors` in JS config | `--color-*` variables in `@theme` | Tailwind v4 | CSS-first token definition |
| GSAP paid plugins (ScrollTrigger) | All plugins free | Post Webflow acquisition 2023 | No license needed, CDN-loadable |
| Phosphor Icons npm install | Phosphor web font via CDN link | v2.x | Zero JS, no build step |

**Deprecated/outdated:**
- `tailwind.config.js` with `theme.extend`: Still valid for build-tool projects, but wrong for this project — use `@theme` in `<style type="text/tailwindcss">`.
- GSAP "Business Green" / "Shockingly Green" license tiers: Eliminated — all plugins are now free.

---

## Open Questions

1. **Venue internet reliability**
   - What we know: The presentation is in Chennai; CDN dependency is the only delivery risk.
   - What's unclear: Whether the venue has reliable enough internet for 5 CDN requests (fonts, icons, Tailwind, GSAP x2).
   - Recommendation: Document the offline fallback plan in the phase execution notes. If internet is uncertain, the AOS + pre-compiled Tailwind variant from CLAUDE.md is the fallback strategy. This is a human decision, not a code decision.

2. **Tailwind v4 floating tag vs. pinned version**
   - What we know: `@tailwindcss/browser@4` currently resolves to 4.2.2. The UI-SPEC uses the floating `@4` tag.
   - What's unclear: Whether a future 4.x minor release before the presentation date could introduce breaking changes.
   - Recommendation: Use the floating `@4` tag in development. Before the final presentation delivery (Phase 3), consider pinning to `@tailwindcss/browser@4.2.2` for stability.

---

## Environment Availability

This phase is purely CDN + static file creation. No local tools beyond a text editor and browser are required.

| Dependency | Required By | Available | Version | Fallback |
|------------|------------|-----------|---------|----------|
| Browser (Chrome/Edge/Safari) | Opening file to verify | Assumed available on presentation device | Any modern | Firefox also works |
| Internet connection | CDN asset loading | Assumed available at venue | — | AOS + pre-compiled CSS offline variant |
| `slideshows/` directory | File save location | Does not exist — must be created | — | Create directory as Task 1 |

**Missing dependencies with no fallback:**
- None. All CDN packages verified HTTP 200. Directory creation is a trivial task.

**Missing dependencies with fallback:**
- Internet at venue: fallback is the offline variant documented in CLAUDE.md (AOS + pre-compiled Tailwind).

---

## Sources

### Primary (HIGH confidence)
- Tailwind CSS official docs — https://tailwindcss.com/docs/installation/play-cdn — `@tailwindcss/browser@4` script tag, `@theme` syntax
- Tailwind CSS @theme docs — https://tailwindcss.com/docs/theme — color token → utility class mapping
- jsDelivr package API — https://data.jsdelivr.com/v1/packages/npm/@tailwindcss/browser — version 4.2.2 confirmed latest
- jsDelivr package API — https://data.jsdelivr.com/v1/packages/npm/gsap — version 3.14.2 confirmed latest
- jsDelivr package API — https://data.jsdelivr.com/v1/packages/npm/@phosphor-icons/web — version 2.1.2 confirmed latest
- Live CDN URL verification — all 6 CDN URLs returned HTTP 200 (2026-03-30)
- UI-SPEC.md (01-UI-SPEC.md) — approved 2026-03-30 — all token values, CDN load order, typography, layout baseline

### Secondary (MEDIUM confidence)
- GSAP free licensing — https://gsap.com/pricing/ — confirmed 100% free post-Webflow acquisition
- Phosphor Icons GitHub — https://github.com/phosphor-icons/web — v2.1.2 web font CSS path structure confirmed

---

## Metadata

**Confidence breakdown:**
- Standard stack: HIGH — all CDN URLs verified live, versions confirmed against jsDelivr API
- Architecture: HIGH — based on approved UI-SPEC.md and official Tailwind v4 docs
- Pitfalls: HIGH for CDN/token pitfalls (verified via official docs); MEDIUM for Tailwind font utility pitfall (requires testing to confirm `@utility` syntax works in `@tailwindcss/browser@4`)

**Research date:** 2026-03-30
**Valid until:** 2026-04-30 (stable ecosystem — CDN versions unlikely to change before presentation)
