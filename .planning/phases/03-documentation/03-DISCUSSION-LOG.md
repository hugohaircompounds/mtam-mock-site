# Phase 3: Documentation - Discussion Log

> **Audit trail only.** Do not use as input to planning, research, or execution agents.
> Decisions are captured in CONTEXT.md — this log preserves the alternatives considered.

**Date:** 2026-03-31
**Phase:** 03-documentation
**Areas discussed:** Prompt List Depth & Style, JTBD Decision Notes Structure, Document Format & Location, Offline Test Strategy

---

## Prompt List Depth & Style

| Option | Description | Selected |
|--------|-------------|----------|
| Curated summaries | Clean, readable bullets capturing intent without raw verbatim text. Polished for business audience. | ✓ |
| Verbatim prompts | Copy-paste exact prompts used. Authentic but rough. | |
| Reconstructed showcase | Rewritten as idealized examples optimized to impress. | |

**User's choice:** Curated summaries

| Option | Description | Selected |
|--------|-------------|----------|
| By build phase | Group under Phase 1, Phase 2, Phase 3. | |
| By page section | Group under Hero, Struggle, Educators, etc. | |
| By JTBD stage | Group under Define > Locate > Confirm > Execute. | |

**User's choice:** Other — "The prompt list should represent what a newbie at Claude/vibe coding should do when designing a website for their hair salon. Foundation and Documentation shouldn't be included."

| Option | Description | Selected |
|--------|-------------|----------|
| Conversational | Written like talking to a friend. Approachable for AI newcomers. | ✓ |
| Instructional | Step-by-step tutorial tone. More structured. | |
| Copy-paste ready | Just the prompts with brief labels. Minimal framing. | |

**User's choice:** Conversational

| Option | Description | Selected |
|--------|-------------|----------|
| Generalized | "Your salon name" / "your services" — audience pictures their own business. | ✓ |
| MTAM-specific | Keep MTAM references — shows exactly what built the demo. | |
| Both | MTAM example first, then "Replace with your own..." | |

**User's choice:** Generalized

**Notes:** The prompt list is a teaching tool for the audience, not a retrospective build log. It should function as a template a newbie could follow.

---

## JTBD Decision Notes Structure

| Option | Description | Selected |
|--------|-------------|----------|
| Table mapping | Page Section / JTBD Stage / Framework Used / Why This Section Exists. Quick to scan. | ✓ |
| Narrative walkthrough | Paragraph-style top-to-bottom explanation. More persuasive. | |
| Annotated screenshot | Numbered callouts on a screenshot linked to a legend. Most visual. | |

**User's choice:** Table mapping

| Option | Description | Selected |
|--------|-------------|----------|
| Framework name + principle | E.g., "Job Map Framework — Define stage: name the struggle before offering a solution." | ✓ |
| Just the JTBD stage | E.g., "Define > Locate > Confirm" — simpler. | |
| You decide | Claude picks the right detail level per section. | |

**User's choice:** Framework name + principle

| Option | Description | Selected |
|--------|-------------|----------|
| MTAM-specific | Explains THIS demo's decisions. Audience points at a section and reads why. | ✓ |
| Generalized template | "Your hero section should..." — reusable checklist. | |

**User's choice:** MTAM-specific

---

## Document Format & Location

| Option | Description | Selected |
|--------|-------------|----------|
| Markdown | .md files — clean, readable, renders on GitHub. | ✓ |
| HTML pages | Styled HTML matching demo aesthetic. | |
| Plain text | .txt — zero formatting. | |

**User's choice:** Markdown

| Option | Description | Selected |
|--------|-------------|----------|
| slideshows/ | Same folder as HTML demo. All deliverables in one place. | ✓ |
| docs/ subfolder | Separate directory. | |
| Project root | Top-level alongside CLAUDE.md. | |

**User's choice:** slideshows/

---

## Offline Test Strategy

| Option | Description | Selected |
|--------|-------------|----------|
| Assume WiFi available | CDN dependencies are fine. Just verify page renders. | ✓ |
| Must work offline | Inline/base64 critical assets. No CDN dependency. | |
| Hybrid fallback | Keep CDN with graceful degradation. | |

**User's choice:** Assume WiFi available

| Option | Description | Selected |
|--------|-------------|----------|
| Chrome on Windows laptop | Most common. Full compatibility. | ✓ |
| Don't know yet | Test Chrome + Edge baseline. | |
| Safari on Mac | Verify Safari-specific rendering. | |

**User's choice:** Chrome on Windows laptop

---

## Claude's Discretion

- File naming conventions for the two .md deliverables
- Exact number of prompts in the prompt list
- Which JTBD frameworks to reference per section in decision notes

## Deferred Ideas

None — discussion stayed within phase scope.
