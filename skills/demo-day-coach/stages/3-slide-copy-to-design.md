# Stage 3 — Slide Copy to Design Spec

> **Stage of `demo-day-coach`.** The umbrella's `SKILL.md` routes here once the founder has slide copy (Output B from stage 2) and is ready for the design spec handoff. Read this file when entering the design-spec stage. Other stage files: `../stages/1-pitch-coach.md`, `../stages/2-script-to-slide-copy.md`.

Take slide copy and visual specs (from `../stages/2-script-to-slide-copy.md`, or generated internally from a script) and produce a single markdown design spec the founder hands to `claude.ai/design` (or another LLM-driven slide tool) to render the actual deck. This skill stops short of rendering — `claude.ai/design` does that step better.

This is the third stage in a chain coordinated by `demo-day-coach`:

1. `../stages/1-pitch-coach.md` — produces the script (the words the founder says)
2. `../stages/2-script-to-slide-copy.md` — produces slide copy and visual specs
3. **This stage** — produces the markdown design spec for handoff
4. `claude.ai/design` (founder-driven, outside this skill) — renders the slides

Founders should not skip stages.

## The organizing principle

The slide is the **visual track** running parallel to the speaker's voice. The audience can listen *or* read — not both at the same time. Every design decision in the spec serves that principle. Brand expression serves it; brand expression does not override it.

The five rules from `../stages/2-script-to-slide-copy.md` govern the doc's contents:

1. One idea per slide.
2. The slide passes the 3-second test.
3. Words on the slide are an anchor or compression, never a duplicate or divergence.
4. No bullet points, no slide titles.
5. Legible from the back row and in a small Zoom tile.

## What this skill produces

A single markdown file in `/mnt/user-data/outputs/`: `[company-name]-live-pitch-spec.md`. The founder uploads this file to `claude.ai/design` for rendering. The doc contains:

- The five rules (so `claude.ai/design` enforces them).
- The font-size floor table.
- The list of patterns to refuse by default (header bars, animations, footers, decorative dividers, bullets).
- The list of brand expressions allowed by default.
- The per-slide design treatments table (hero number → big and centered; hero number + growth chart → tall-narrow chart; etc.).
- The "overwhelm" exception (when density is the rhetorical point).
- A `## The slides` section with the per-slide spec for the founder's specific deck — slide copy, visual spec, cue, design notes — extracted from the parent skill's output.

## What this skill does not do

- **Does not render a `.pptx`.** That step happens in `claude.ai/design`. Rendering quality there is materially better than what this skill could produce via `pptxgenjs`.
- **Does not handle brand identity.** No palette extraction, no font confirmation, no logo placement, no two-pushback on header bars. Brand identity (colors, fonts, logo, components) goes directly into `claude.ai/design`'s design system, not through this skill. If the founder uploads a brand guide or hex codes, redirect them to load it in `claude.ai/design`.
- **Does not rewrite slide copy.** The parent skill owns the words on the slides. This skill annotates with design treatments; it does not change copy.
- **Does not produce teaser decks or leave-behind decks.** Different artifacts, denser, self-contained, different rules. Out of scope.
- **Does not iterate slide-by-slide.** One pass produces the doc; the founder iterates inside `claude.ai/design`.

## How to run

### Step 1 — Determine the input

The founder may arrive with any of:

- **Output B from `../stages/2-script-to-slide-copy.md`** (a `.docx` with one slide per page, including slide copy, visual specs, cues, and design notes). The ideal input. Read it using the `docx` skill (`/mnt/skills/public/docx/SKILL.md`) and proceed to Step 2.
- **Just a script** (`.txt`, `.md`, `.docx`, or pasted in chat). Run `../stages/2-script-to-slide-copy.md`'s logic internally first to produce slide copy + visual specs. Then proceed to Step 2.
- **Both** — use Output B as the source of truth; the script is reference material.

### Step 2 — Assemble the handoff doc

1. Read `../references/live-pitch-spec-template.md` for the full template, substitution instructions, and tone guidance.
2. Substitute the company name (lowercased, hyphenated) into the filename: `[company-name]-live-pitch-spec.md`. If unknown, ask the founder once; if they skip, fall back to `live-pitch-spec.md`.
3. Render the template with the company name and today's date substituted.
4. Fill in the `## The slides` section: one numbered subsection per slide, with `Slide copy`, `Visual`, `Cue` (if relevant), and `Design notes` pulled directly from Output B or the internally-generated slide copy. Do not add fields the source didn't include. Do not paraphrase — copy the source content into the fields.
5. Save to `/mnt/user-data/outputs/[filename]`.
6. Present via `present_files`.

### Step 3 — Hand off

In one short message to the founder:

- The doc is saved and ready.
- Open `claude.ai/design`, load the brand identity into its design system, then upload this file as input.
- The doc covers the full deck — iterate on specifics inside `claude.ai/design`.

Do not narrate every section of the doc. The founder doesn't need a guided tour. The doc is for `claude.ai/design`, not for the founder to read top-to-bottom.

## Examples

### Example 1 — Founder hands over Output B from the parent skill

Founder uploads `acme-pitch-slides.docx` (from `../stages/2-script-to-slide-copy.md`) and says *"design this."*

Read the .docx, identify the slides (e.g., 12), render the template with company name "acme" and today's date, fill `## The slides` with 12 subsections containing each slide's copy + visual spec + cue + design notes from the source, save as `acme-live-pitch-spec.md`, present.

### Example 2 — Founder arrives with just a script

Founder pastes the script in chat and says *"I need slides for this — make a deck."*

Run the slide-copy logic from `../stages/2-script-to-slide-copy.md` internally (one idea per slide, the five rules, visual specs per slide). That produces ~10 slides of copy + visual spec in memory. Then render the template and fill `## The slides` with those slides. Save and present.

### Example 3 — Founder asks the skill to handle brand

Founder uploads `brand-guidelines-v3.pdf` and says *"design my deck using this brand."*

Redirect, briefly: *"Brand identity goes directly into `claude.ai/design`'s design system — that's where your colors, fonts, and logo live for the rendering step. This skill produces the design spec (rules + per-slide treatments) that tells `claude.ai/design` how to apply your brand for a live pitch. I'll generate the spec; you'll load the brand guide into `claude.ai/design`'s design system separately. Sound good?"*

Do not extract brand inputs from the PDF. Do not produce a brand spec. The PDF goes into `claude.ai/design` directly.

## When the founder asks for something out of scope

- *"Can you also write my pitch script?"* → Redirect to `../stages/1-pitch-coach.md`.
- *"Can you redo the slide copy too?"* → Redirect to `../stages/2-script-to-slide-copy.md`. This skill takes the slide copy as given.
- *"Can you make me a `.pptx` directly?"* → No. This skill produces a design spec for handoff to `claude.ai/design`. The reason is rendering quality — `claude.ai/design` produces materially better-looking decks than this skill could render via `pptxgenjs`. The founder can export a `.pptx` from `claude.ai/design` after rendering there.
- *"Can you handle my brand colors / fonts / logo?"* → No. That goes into `claude.ai/design`'s design system directly. (See Example 3.)
- *"Can you make me a teaser deck I can email to investors?"* → Different artifact. Teaser decks are denser and self-contained. Out of scope.
- *"Can you make me a leave-behind?"* → Same. Different artifact, different rules. Out of scope.
- *"Add animations / transitions / a fade-in for the big number"* → The doc encodes "no animations, no transitions" as a default refusal for `claude.ai/design`. If the founder wants them anyway, they can override inside `claude.ai/design`.

## Common failures to avoid

- **Producing a `.pptx`.** This skill does not render slides. `claude.ai/design` does that step.
- **Doing brand intake.** No palette extraction, no font confirmation, no two-pushback on header bars. Brand identity flows around this skill, not through it.
- **Padding the per-slide section with invented fields.** Stick to what's in the parent skill's output: slide copy, visual spec, cue (if relevant), design notes. Don't add a "rationale" field, a "treatment" field, a "speaker emphasis" field, etc.
- **Paraphrasing the slide copy.** Copy it verbatim from the source. The parent skill owns the words.
- **Rewriting the rules** in the template. The template is the rules. Render it as-is with substitutions, not as a starting point for your own version.
- **Producing a closing "Thank you" slide spec with email + social handles.** The closing slide holds the company name + one-line thesis or the ask. Contact info goes in the leave-behind, not the live deck.

## Why this scope

The pitch chain has three reasoning steps before the rendering step:

- The script (what the speaker says) — `../stages/1-pitch-coach.md`.
- The slide copy (what the slide says) — `../stages/2-script-to-slide-copy.md`.
- The design spec (how the slide looks) — this skill.

Each is a different kind of thinking. This skill owns the third. The rendering step — turning a design spec into actual designed slides — is a fourth kind of thinking, and it's the part this skill was previously worst at. Producing slides via `pptxgenjs` yields structurally correct but visually flat output. `claude.ai/design` has a richer design pipeline, design-system support, and renders materially better-looking decks.

So this skill's job is to produce the *thinking* in a form `claude.ai/design` can apply — the live-pitch rules, the per-slide design treatments, the per-slide content from the parent skill — and then hand off. The split mirrors how the work actually gets done well.

## References

- `../stages/2-script-to-slide-copy.md` (parent skill) — the five rules this skill inherits, and the source of slide copy + visual specs.
- `../references/live-pitch-spec-template.md` — the literal template for the handoff doc.
- `docx` skill (`/mnt/skills/public/docx/SKILL.md`) — for reading the parent skill's `.docx` output when the founder hands it over.
