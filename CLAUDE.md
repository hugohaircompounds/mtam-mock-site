# CLAUDE.md

This file provides guidance to Claude Code (claude.ai/code) when working with code in this repository.

## Project Overview

**LaunchBridge** — a startup-investor matching platform. The project is in early planning stages. Prior commits show a Next.js MVP was scaffolded (with Supabase, Zustand, Tailwind) but the application code was removed. The repo currently holds business strategy documents and workflow tooling.

## Repository Structure

- `JTBD/` — Jobs-to-be-Done business framework cheat sheets (Marketing, Product, Production, Operations, Developer, Data, Design, Strategy, and Foundational Frameworks). These are reference materials for applying JTBD methodology to product decisions.
- `.claude/` — GSD (Get Shit Done) project management tooling, including slash commands, agents, hooks, and workflow templates.

## GSD Workflow System

This repo uses the **Get Shit Done (GSD)** workflow system for Claude Code. Key commands:

- `/gsd:new-project` — Initialize a project (creates `.planning/` with PROJECT.md, ROADMAP.md, REQUIREMENTS.md, STATE.md, config.json)
- `/gsd:plan-phase <n>` — Plan a specific phase
- `/gsd:execute-phase <n>` — Execute a planned phase
- `/gsd:next` — Advance to the next task
- `/gsd:progress` — Show current progress
- `/gsd:help` — Full command reference

GSD hooks are configured in `.claude/settings.json` and run automatically (update checks on session start, context monitoring on tool use, prompt guard on writes).

## Tech Stack (from prior MVP, likely to be rebuilt)

- **Framework:** Next.js (App Router) with TypeScript
- **Database:** Supabase (Postgres with migrations in `supabase/migrations/`)
- **State:** Zustand
- **Styling:** Tailwind CSS
- **Auth:** Supabase Auth with demo mode

<!-- GSD:project-start source:PROJECT.md -->
## Project

**MTAM Homepage Demo — JTBD Redesign**

A demo-ready, single-page HTML redesign of the MoreThanAMethod.com homepage that demonstrates how AI combined with the Jobs-To-Be-Done framework can intentionally drive website design decisions for hair stylists. Built for a STYSTS business presentation in Chennai showing what AI can do for beauty professionals trying to build a web presence.

**Core Value:** Every section of the page exists because a JTBD framework decision put it there — the demo must visually prove that AI + JTBD produces intentional, customer-job-driven design, not just pretty layouts.

### Constraints

- **Format**: Single self-contained HTML file (all CSS/JS inline, no external dependencies except CDN fonts/icons)
- **Location**: Must be saved to `slideshows/` directory so link can be clicked during presentation
- **Complexity**: Simple enough to explain in a meeting, polished enough to impress
- **Framework**: Must demonstrably apply JTBD principles from the `/JTBD/` reference files
- **Deliverables**: HTML file + prompt list + JTBD decision notes (3 artifacts total)
<!-- GSD:project-end -->

<!-- GSD:stack-start source:research/STACK.md -->
## Technology Stack

## Recommended Stack
### Core Technologies
| Technology | Version | Purpose | Why Recommended |
|------------|---------|---------|-----------------|
| Tailwind CSS (Play CDN) | v4 (`@tailwindcss/browser@4`) | Utility-first styling without a build step | The only CSS framework that lets you write utility classes inline in HTML and have them compiled in-browser at runtime. v4 rewrites the engine in Rust — faster than v3. "Not for production" warning is irrelevant: this file is never deployed, only clicked during a presentation. Single script tag. |
| Google Fonts | current | Typography — two-font system | Free, globally cached, single `<link>` tag. No self-hosting needed. Fonts are the single biggest signal of premium design quality for the effort cost. |
| Phosphor Icons | v2.1.2 | UI icons — checkmarks, arrows, stars, course icons | 9,000+ icons in 6 weights (thin, light, regular, bold, fill, duotone). One `<link>` tag per weight. Far more expressive than Heroicons or Font Awesome for a beauty/education context. Duotone weight adds brand polish without JS. |
| GSAP + ScrollTrigger | v3.14.2 | Scroll-driven entrance animations | GSAP is now 100% free (all plugins, no paid tier) following Webflow's acquisition. ScrollTrigger adds fade-in-on-scroll with two CDN script tags. This is the professional animation library — sites that use it look noticeably more polished than sites using AOS. Total size ~100KB but loaded from CDN. |
### Supporting Libraries
| Library | Version | Purpose | When to Use |
|---------|---------|---------|-------------|
| AOS (Animate On Scroll) | v2.3.1 | Lightweight scroll reveal alternative | Use ONLY if the demo needs to work offline without CDN access. AOS is 8KB vs GSAP's 100KB. For a presentation with reliable internet, use GSAP. For an offline fallback, swap to AOS with `data-aos="fade-up"` attributes. |
| Alpine.js | v3.x.x | Minimal JS interactivity (tabs, toggles) | Only add if the demo needs any toggling behavior (e.g., FAQ accordion, pricing toggle). Adds ~4KB. For a pure scroll page, omit entirely. |
### Typography System
| Role | Font | Why |
|------|------|-----|
| Display/Hero headings | DM Serif Display | High-contrast serif. Signals luxury, editorial quality, and confidence. Contrasts sharply with sans-serif body. Fits the "professional yet approachable" brand. MTAM already uses Manrope — adding a complementary display serif elevates without breaking brand. |
| Body, UI, subheadings | Manrope | MTAM's existing body font. Geometric sans-serif, excellent legibility at small sizes, available as variable font. Using their existing font reduces cognitive dissonance in the demo. |
### CDN Load Order (Complete Head Block)
## Alternatives Considered
| Recommended | Alternative | Why Not |
|-------------|-------------|---------|
| Tailwind v4 Play CDN | Bootstrap 5 CDN | Bootstrap requires fighting component defaults; its grid is fine but Tailwind's utility approach produces more precise, intentional layouts. Bootstrap's aesthetic reads "corporate template" not "premium education brand." |
| Tailwind v4 Play CDN | Pico CSS | Pico is classless (styles semantic HTML automatically). Excellent for quick docs pages. Wrong for a presentation demo — you want to visually prove intentional design decisions, not just "dump content and it looks okay." |
| Tailwind v4 Play CDN | Inline CSS only | No build tooling means verbose, repetitive CSS in a `<style>` block. Tailwind utility classes inside HTML elements communicate design intent at a glance, which matters when explaining the demo to an audience. |
| GSAP ScrollTrigger | AOS (Animate on Scroll) | AOS is 8KB vs GSAP's ~100KB but produces noticeably lower-quality animations. For a business presentation where the goal is "impress the room," GSAP's polished easing curves and ScrollTrigger's precision are worth the load cost. Both load from CDN so file size in the HTML itself is near-zero. |
| GSAP ScrollTrigger | CSS `animation-timeline: view()` | Pure CSS scroll animations work in Chrome/Edge/Safari 18+ but Firefox does not support them without a flag as of early 2026. A presentation environment could be running any browser. GSAP works everywhere without browser flags. |
| DM Serif Display + Manrope | Playfair Display + Inter | Both pairings are valid. DM Serif Display is chosen over Playfair because it's lighter/more modern — Playfair can feel heavy. Manrope over Inter because MTAM already uses Manrope (brand continuity). |
| Phosphor Icons | Font Awesome 6 | Font Awesome free tier requires account/kit setup which adds friction. Phosphor requires zero account, is open source, and the duotone weight looks more premium for a beauty brand than Font Awesome's monoweight icons. |
| Phosphor Icons | Lucide Icons | Lucide has only stroke icons (no fill, no duotone, no weight variation). Phosphor gives 6 weights — the same icon can be thin in a feature card and filled in a CTA button, creating visual hierarchy with one library. |
## What NOT to Use
| Avoid | Why | Use Instead |
|-------|-----|-------------|
| React/Vue/Svelte | Requires a build step. A single HTML file cannot use JSX or SFC without compilation. Frameworks add complexity that produces no visible value in a static demo. | Vanilla JS + Alpine.js for any light interactivity |
| Webpack/Vite | Build tools output files — you'd need a dist/ folder, a server, or a build step. The constraint is one clickable .html file. | CDN-only approach above |
| External image hosting you don't control | Broken images during a live presentation are catastrophic. Services like Lorem Picsum are fine for staging but can go down. | Inline SVG illustrations for decorative elements; `placehold.co` for dimensioned placeholders (e.g., `https://placehold.co/800x600/1a1a1a/ffffff`); consider base64-encoding any critical images |
| CSS `animation-timeline: view()` as primary animation | Firefox flag required. Presentation environment is unknown. | GSAP ScrollTrigger |
| Bulma CSS | Classes like `is-primary` and `has-text-centered` are verbose and opinionated. The component structure imposes a layout system that fights against custom design. | Tailwind utility classes |
| Google Fonts `@import` inside CSS | `@import` inside `<style>` blocks blocks rendering. The `<link>` preconnect + stylesheet approach is 20-30% faster. | `<link>` tags with `preconnect` hints in `<head>` |
| AOS as primary animation library | Produces adequate but not polished animations. For a demo whose entire value proposition is "look what AI + JTBD can produce," "adequate" is not the bar. | GSAP ScrollTrigger |
## Stack Patterns by Variant
- Replace GSAP with AOS (AOS is 8KB, GSAP is ~100KB — AOS loads faster on slow connections)
- Replace Tailwind Play CDN with a pre-compiled Tailwind stylesheet saved inline in `<style>` tags (run `npx tailwindcss` against the final HTML before the trip)
- Consider base64-encoding any critical images inside the HTML itself
- Test the file on airplane mode before the presentation
- Add Alpine.js: `<script defer src="https://cdn.jsdelivr.net/npm/alpinejs@3.x.x/dist/cdn.min.js"></script>`
- Use `x-data`, `x-show`, `x-transition` attributes — no separate JS file needed
- Use Tailwind's `slate-900`, `zinc-100`, `white`, `black` color tokens
- Add one accent color (e.g., warm gold `#C9A84C` or dusty rose `#D4A09A`) via `@theme` block in a `<style type="text/tailwindcss">` tag
- This avoids breaking MTAM's aesthetic while giving the demo visual warmth
- Remove scroll animations entirely — they don't show in screenshots
- Use CSS `opacity`, `transform`, and `box-shadow` to bake in visual depth statically
## Version Compatibility
| Package | Compatible With | Notes |
|---------|-----------------|-------|
| `@tailwindcss/browser@4` | Modern browsers (Chrome 111+, Safari 16.4+, Firefox 128+) | v4 drops IE and old Safari support. Presentation context is presumably a modern laptop browser — this is fine. |
| `@phosphor-icons/web@2.1.2` | All browsers with CSS font-face support | Font icons work everywhere. No JS dependency. |
| `gsap@3.14.2` | All modern browsers, IE11 with degraded support | GSAP 3.x supports IE11 (though animations may be less smooth). Not a concern for a presentation laptop. |
| `aos@2.3.1` | IE10+, all modern browsers | Only relevant if AOS is chosen over GSAP. |
| Google Fonts (DM Serif Display, Manrope) | All browsers | Both fonts are variable font-compatible. `font-display: swap` is included automatically via the Google Fonts API URL. |
## Design System Baseline
## Sources
- Tailwind CSS v4 Play CDN official docs — https://tailwindcss.com/docs/installation/play-cdn (HIGH confidence — official)
- GSAP 3.14.2 on jsDelivr — https://www.jsdelivr.com/package/npm/gsap (HIGH confidence — verified from CDN package page)
- GSAP free licensing confirmed — https://gsap.com/pricing/ (HIGH confidence — official, "100% free for all users")
- Phosphor Icons v2.1.2 GitHub — https://github.com/phosphor-icons/web (HIGH confidence — official repo, version confirmed March 31 2025 release)
- AOS v2.3.1 CDN — https://michalsnik.github.io/aos/ (HIGH confidence — official site)
- CSS scroll-driven animations Firefox support — https://developer.mozilla.org/en-US/docs/Web/CSS/Guides/Scroll-driven_animations (HIGH confidence — MDN)
- Google Fonts DM Serif Display + Manrope pairing rationale — multiple sources (fontpair.co, typewolf.com, medium.com design articles) (MEDIUM confidence — community/editorial, no official spec)
- GSAP vs AOS comparison — https://kitemetric.com/blogs/trig-js-vs-aos-js-vs-scrolltrigger-choosing-the-right-scroll-animation-library (MEDIUM confidence — editorial)
- 2025 design trends (glassmorphism, gradients) — https://www.thewebfactory.us/blogs/30-best-web-design-trends-styles-for-2025/ (MEDIUM confidence — industry editorial)
<!-- GSD:stack-end -->

<!-- GSD:conventions-start source:CONVENTIONS.md -->
## Conventions

Conventions not yet established. Will populate as patterns emerge during development.
<!-- GSD:conventions-end -->

<!-- GSD:architecture-start source:ARCHITECTURE.md -->
## Architecture

Architecture not yet mapped. Follow existing patterns found in the codebase.
<!-- GSD:architecture-end -->

<!-- GSD:workflow-start source:GSD defaults -->
## GSD Workflow Enforcement

Before using Edit, Write, or other file-changing tools, start work through a GSD command so planning artifacts and execution context stay in sync.

Use these entry points:
- `/gsd:quick` for small fixes, doc updates, and ad-hoc tasks
- `/gsd:debug` for investigation and bug fixing
- `/gsd:execute-phase` for planned phase work

Do not make direct repo edits outside a GSD workflow unless the user explicitly asks to bypass it.
<!-- GSD:workflow-end -->

<!-- GSD:profile-start -->
## Developer Profile

> Profile not yet configured. Run `/gsd:profile-user` to generate your developer profile.
> This section is managed by `generate-claude-profile` -- do not edit manually.
<!-- GSD:profile-end -->
