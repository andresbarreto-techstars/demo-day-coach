# Live Pitch Slide Design Spec — Template

This is the template the `slide-copy-to-design` skill renders into a markdown file for the founder to hand off to `claude.ai/design` (or another LLM-driven slide tool that will design the slides).

## How to use this template

When generating the file:

1. Replace `[FOUNDER-COMPANY]` with the company name throughout. If unknown, ask the founder once. If they skip, fall back to `live-pitch-spec.md` as the filename and `[Your Company]` as the inline placeholder.
2. Replace `[GENERATED DATE]` with today's date in YYYY-MM-DD format.
3. Render the `## The slides` section by reading the parent skill's `.docx` output (or the slide copy generated internally if the founder arrived with only a script). One subsection per slide, with `Slide copy`, `Visual`, `Cue` (if present in source), and `Design notes`. Pull from the source verbatim — do not paraphrase, do not invent additional fields.
4. Save to `/mnt/user-data/outputs/[founder-company]-live-pitch-spec.md` (lowercased, hyphenated company name).
5. Present via `present_files`.

The template below is the literal content to write, with substitutions applied. Do not add commentary, source attribution, or skill-internal language. The file is written for the LLM running in the destination tool, not for the founder to read top-to-bottom.

---

## TEMPLATE STARTS HERE

```markdown
# [FOUNDER-COMPANY] — Live Pitch Slide Design Spec

This file contains the design rules and per-slide specifications for the [FOUNDER-COMPANY] live pitch deck. It is written for an LLM (e.g., the model running `claude.ai/design`) that will design the slides.

The rules below describe **how to design a live pitch deck** — slides the speaker presents in person or on a video call, where the speaker is doing the talking and the slide is the visual track running parallel to their voice. They do not describe what the brand is. If a design system is already loaded in this tool — colors, typography, logo, layout primitives — defer to it for brand identity. These rules tell you how to apply that brand identity for the live-pitch case.

These rules are different from the rules for a leave-behind deck or a teaser deck. Do not apply this file to those artifacts.

Generated: [GENERATED DATE]

---

## The organizing principle

The slide is the **visual track** running parallel to the speaker's voice. The audience can listen *or* read — not both at the same time. Every design decision serves that principle. Brand expression serves it; brand expression does not override it.

When in doubt, ask: *Does this design choice help the audience listen, or does it pull them away?* That is the only test that matters.

---

## The five rules

These are the rules every slide must satisfy. They are not preferences.

1. **One idea per slide.** If a slide has more than one idea, split it into multiple slides. There is no upper limit on slide count — slide count follows from idea count.
2. **The slide passes the 3-second test.** A first-time viewer, glancing at the slide for three seconds, comprehends what it is about. If they need to read or study, the slide has failed.
3. **Words on the slide are an anchor or compression of what the speaker is saying — never a duplicate, and never a divergence.** Do not put the speaker's full sentence on the slide. Compress to a phrase, a number, or an image. Never put text on the slide that says something different from what the speaker is saying at that moment.
4. **No bullet points. No slide titles.** Bulleted lists fail the 3-second test. Slide titles eat real estate and pull attention upward before the speaker begins. Section dividers, if used, are a single numeral or word, not a title-with-subtitle.
5. **Legible from the back row of a 500-person room and in a small Zoom tile.** Both contexts. If text fails either, it fails the rule.

---

## Layout rules

### Light vs. dark backgrounds

Light background, dark text by default. It holds intensity in lit rooms and on Zoom, which is where most pitches happen.

Dark background, light text is allowed only for confirmed dark, large-hall presentation environments (Demo Day, conference keynote). If the environment is unknown, default to light.

A deck commits to one and stays there. If using a sandwich structure (dark for opening + closing, light for content), do that intentionally — do not mix arbitrarily.

### Text positioning

Position key text in the upper half of the slide where possible. Back-row audience members have unobstructed sightlines to the top of the screen; the bottom is often blocked by heads or the speaker.

### Whitespace

Whitespace is active, not leftover. A slide with one element and a lot of empty space is doing the right thing — it is amplifying the one element through restraint. Do not fill empty space with decoration.

### Color

One dominant color, one accent, neutrals. Even if the brand has six colors, use one for dominance, one for emphasis, and neutrals (background, text) for everything else. Demote the rest of the palette to "available but rarely used."

Color guides the eye; it does not decorate. A brand-colored accent on the one number that matters is doing work. A brand-colored stripe at the bottom of every slide is not.

---

## The font-size floor — non-negotiable

Every text element must clear these minimums. Anything below the absolute floor either gets resized up or gets cut.

| Element | Absolute floor | Working minimum |
|---|---|---|
| Hero numbers / display moments | 80pt | 100pt+ |
| Short phrases (full-slide focal text) | 50pt | 60pt |
| Body text on slides with multiple text elements | 30pt | 40pt |
| Chart caption (the "conclusion in plain words") | 36pt | 40pt+ |
| Chart axis labels (only if values matter) | 24pt | 28pt |
| Diagram labels | 28pt | 40pt |
| Slide numbers (corner) | 14pt | 16pt |
| Logo lockup text (if any text in the lockup) | 12pt | 14pt |

**The absolute floor is the refusal line.** If a layout would force any text below the absolute floor for that element, resize up first; if that breaks the layout, cut the text rather than rendering it small. Small text on a slide is the same as no text — except that it adds visual noise without adding information.

**The working minimum is the design target.** Default to the working minimum; drop to the absolute floor only when the layout requires it.

---

## Per-slide design treatments

For each slide, match the slide copy spec to the appropriate treatment.

| Slide copy spec | Design treatment |
|---|---|
| `[no text]` | Image-only slide. Single image, full-bleed or centered with whitespace. |
| `[single number, e.g., "$3M"]` | Number in display font, 100pt+, brand-colored or accent-colored, vertically centered, slight upper-half bias. |
| `[hero number + growth chart]` | See "The hero-number-plus-growth-chart layout" below. |
| `[short phrase, e.g., "Mobile internet, 2007"]` | Phrase in display font, 50–70pt, upper half of slide, white space below. |
| `Visual: [chart description]` | Single-trend chart, large, with the conclusion as a caption *on* the chart in display font (not under it as a footnote). Y-axis labels minimal but ≥24pt if shown; legend omitted unless essential. Caption ≥40pt. |
| `Visual: [diagram with ≤4 elements]` | Diagram large, brand colors used to guide the eye to the key element, ≥40pt labels. |
| `Visual: [photo]` | Photo full-bleed or near full-bleed. No caption unless the spec includes one. |
| `Design notes: hold from previous slide` | Same slide, no change. Duplicate the previous slide so the speaker can advance the cue without changing the visual. |

---

## The hero-number-plus-growth-chart layout

When a slide pairs a hero number with a growth chart:

- **The chart's bounding box should be roughly 80–90% of slide height and no more than 30–35% of slide width** — tall and narrow.
- **The hero number sits in the remaining space** (display font, 100pt+) with a short label below it (e.g., "ARR" or "users") at 32–40pt.
- **Chart on the left, number on the right** is the conventional reading order (eye reads chart → lands on number) but either side works as long as the chart is tall and narrow.
- **Do not** plot the chart wide and short to "fill" the slide. A line plotted in a tall-narrow box reads as dramatically steeper than the same data in a wide-short box. Wide-short is the layout that makes growth look unimpressive. The negative space around a tall-narrow chart is the slide working correctly.
- **Y-axis** can drop labels entirely if the chart is purely directional. If values matter, keep them at 24pt minimum.

---

## What to refuse by default

Do not produce these unless explicitly requested:

- **Animations.** Build animations, fade-ins, slide transitions, parallax effects. The speaker carries the pitch; slide motion competes for attention.
- **Slide transitions** between slides.
- **Header bars** with logo + tagline. A header bar is a title bar, which Rule 4 forbids.
- **Footers** with URL, social handles, confidentiality notices. Slide numbers in a small corner are allowed; multi-element footers are not.
- **Decorative graphics, gradients, patterns** behind content.
- **Section dividers with title + subtitle + decorative element.** A single numeral or word does this job better.
- **Bullet lists.**
- **Accent lines under titles.** (There are no titles.)
- **Icons in colored circles** as section markers.
- **Two-column layouts with text + illustration** that force text density.

---

## Allowed brand expressions

These are allowed by default:

- **Small persistent logo in a corner** (typically bottom-right, ≤8% of slide width).
- **Slide numbers in a corner.** Optional. Skip for short decks; useful for longer ones.
- **Brand-colored accent** on a single key element per slide — a bar, a dot, the underline of one number. Single accent, not multiple.
- **Brand typeface** for headings and large standalone numbers. Substitute a similar-character readable font for any text below display size if the brand typeface fails the legibility floor.
- **Brand background color** instead of white or black, only if contrast with text passes the back-row test.

---

## The "overwhelm" exception

When the moment in the pitch is meant to **convey the size or messiness of a problem** — many competitors, many fragmented services, many manual steps the user currently performs — density is allowed and even desirable. The slide is doing the rhetorical work of the moment.

How to recognize the overwhelm moment: the script segment uses words like "fragmented," "scattered," "every," "all of these," "imagine doing this for…"

How to design it: pack the slide with many small elements, brand-neutral, so the *aggregate* is the takeaway. The 3-second test still applies — the audience comprehends *"there is a lot here"* in 3 seconds; they don't have to read each item. Do not caption it.

This is the only allowed exception to "one focal point per slide." Use it once or twice in a deck at most.

---

## Common failures to avoid

- Filling whitespace with decoration. Empty space is the slide working correctly.
- Treating the brand color as the dominant background. Brand color is accent, not field.
- Putting the speaker's full sentence on the slide. Compress or drop to image-only.
- Plotting the growth chart wide and short. Always tall and narrow.
- Adding a "Thank you" closing slide with email + social handles. The closing slide holds the single most important thing the audience walks out remembering — the company name + one-line thesis, or the ask. Contact info goes in the leave-behind, not the live deck.
- Adding fields to a slide that aren't in the spec. The spec is the spec. If the source says "Slide copy: $3M" and "Visual: tall narrow growth chart," do not add a subtitle, a caption, or a sub-bullet "explaining" the number.

---

## The slides

[For each slide in the source, render a numbered subsection with the fields below. Pull content verbatim from the parent skill's output — do not paraphrase, do not add fields the source didn't include. If a field is empty in the source, omit it.]

### Slide 1
- **Slide copy:** [content]
- **Visual:** [description]
- **Cue:** [speaker cue, if present in source]
- **Design notes:** [from source, if present]

### Slide 2
- **Slide copy:** [content]
- **Visual:** [description]
- **Cue:** [if present]
- **Design notes:** [if present]

[...continue for each slide in the deck...]
```

## TEMPLATE ENDS HERE

---

## Notes for the skill when generating

- **Length budget.** The rendered file should land at roughly 200–350 lines depending on slide count. Most of the variance is in the per-slide section.
- **Tone.** Imperative, terse, no apologies, no academic framing. The reader is an LLM, not a person.
- **Do not include skill-internal concepts** in the rendered output. The destination LLM doesn't need to know this file came from a skill.
- **Do not cite sources or attribute rules.** The destination LLM doesn't need to know where the rules came from to apply them.
- **Defer to the active design system on brand identity** but assert authority on design rules. The header section already does this; do not contradict it later in the file.
- **Per-slide content** comes from the parent skill's `.docx` output (one slide per page) or, if the founder arrived with only a script, from the slide-copy logic the skill ran internally. Extract: slide copy, visual spec, cue (if relevant), design notes. Do not invent fields the source didn't include.
- **No personalized addendum section.** This skill does not do brand intake; there are no substitutions, unlocks, or deck-specific brand decisions to record. The rules are the rules.
