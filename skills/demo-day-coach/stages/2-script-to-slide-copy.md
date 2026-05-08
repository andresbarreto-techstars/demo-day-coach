# Stage 2 — Pitch Script to Slide Copy

> **Stage of `demo-day-coach`.** The umbrella's `SKILL.md` routes here once the founder has a finished script and is ready for slide copy. Read this file when entering the slide-copy stage. Other stage files: `../stages/1-pitch-coach.md`, `../stages/3-slide-copy-to-design.md`.

Take a finished pitch script and produce slide copy and visual specs for the slides that will accompany it on stage or on Zoom. The slides are the visual track running alongside the spoken track — they support what the founder is saying, never compete with it or replace it.

## The organizing principle

A presentation slide is **the visual channel**, parallel to the speaker's voice. The audience can listen *or* read — not both at the same time. If the slide makes them choose, the slide has failed.

A useful mental image: the graphic over a late-night talk show host's shoulder. The host says "the new tariff package" and a single image of the document slides into frame. The graphic doesn't speak. It anchors what's being said. When the host moves on, the graphic moves on.

That is the shape of every slide this skill produces: an anchor for what the founder is saying *at that moment* — never a duplicate, never a divergence, never a substitute.

## What this skill does and doesn't do

**Produces:** Slide copy (the words on the slide, if any) and visual specs (what should appear and how it should behave) for a live presentation pitch.

**Does not produce:** Slide designs. Teaser decks (decks emailed cold to investors). Leave-behind decks (decks left after a meeting). Those are different artifacts — readers consume them without a speaker, so they need to be denser and self-contained. This skill is for slides that exist *with* a live speaker.

**Does not edit the script.** The founder's script is taken as gospel. Script feedback lives in stage 1 (`../stages/1-pitch-coach.md`). If the founder asks this stage to also fix their script, route them back to stage 1.

## The five rules

These five rules govern every slide. They aren't five different rules; they're five different angles on the same principle — that the slide is the visual channel running parallel to the speaker's voice.

### Rule 1 — One idea per slide

Every slide carries exactly one idea. If the script section makes two points, that's two slides. If it makes seven, that's seven. There is no upper limit on the number of slides; a 5-minute pitch can have 4 slides or 40. Slide count auto-scales with content because each slide is light.

This means: never combine two ideas onto one slide for "efficiency." Splitting always works and usually works better.

### Rule 2 — The slide passes the 3-second test

The audience must comprehend the slide in **about 3 seconds** and then return their attention to the speaker. If the slide can't be understood at a glance, it competes with the speaker for attention and the speaker loses.

Practical implications:
- The slide carries a single visual focus point.
- Anything that requires reading or studying — a paragraph, a complex chart, a screenshot of a UI, a busy diagram — fails the 3-second test and should be reworked or replaced.
- A chart is allowed only if it shows one trend, with the conclusion baked into a short caption (e.g., "5× growth in 6 months" written next to the line). The audience should not have to interpret the chart.
- A diagram is allowed only with ≤4 elements.
- A screenshot is allowed only when zoomed to a single element with that element labeled — never a full-app UI.

### Rule 3 — Words on the slide are an anchor or a compression, never a duplicate or a divergence

Three categories of slide text, three different rules:

| Type | Example | Rule |
|---|---|---|
| **Compression** of what the speaker is saying — the most quotable phrase, distilled | Speaker says: *"This is the moment that mobile internet became real."* Slide says: **"Mobile internet, 2007."** | **Allowed.** The slide gives the audience a memory hook. |
| **Anchor** for the moment — a single number, name, or label that lets the slide announce its topic without competing | Speaker says: *"The first thing I want to talk about today…"* Slide says: **"1"** | **Allowed.** The slide declares the moment without speaking. |
| **Duplication** — the speaker's exact sentence written on the slide | Speaker says and slide says: *"Our revenue grew 5× in six months."* | **Forbidden.** Forces the audience to choose between reading and listening. The cognitive science is clear: matching text alongside narration and graphics actively *reduces* comprehension compared to narration and graphics alone. |
| **Divergence** — the slide says something different from what the speaker is saying | Speaker discusses traction; slide shows team bios | **Forbidden.** Splits attention; the audience cannot follow either thread. |

**Default to the lowest necessary word count.** The hierarchy, from most preferred to least:
1. **Zero words** — a single image, number, or visual carries the idea.
2. **One word, one number, or one short label** — when a category, name, or anchor is needed.
3. **A short phrase** — when a compression of the speaker's idea earns its place.
4. **A short caption** — when paired with a chart or visual that needs interpretation locked in.

There is no fixed word ceiling. The constraint is legibility (Rule 5) and the principle that every word must earn its place. If a word can be cut without breaking the slide, cut it.

### Rule 4 — No bullet points, no slide titles

**No bullets.** Bullets flatten reasoning into parallel-looking fragments and invite the speaker to read them. If the script lists three items, produce three slides — one item per slide. Three crisp slides beat one slide with three bullets, every time.

**No slide titles.** The slide content is the slide. A title bar at the top eats real estate, adds noise, and sets up the audience to read the title before listening to the speaker. The exception is so rare it's not worth defining.

### Rule 5 — Legible from the back row and in a small Zoom tile

The slide must be readable by someone in the back of a 500-person room or by someone watching the pitch in a thumbnail-sized Zoom tile. This sets a font-size floor (roughly 30pt minimum, 40pt+ preferred for short text), which in turn caps how many words can plausibly fit on a slide while remaining legible.

This skill doesn't design the slide, but it does include the legibility constraint in the visual spec so that whoever lays out the slide (the founder, a designer, or `claude.ai/design`) respects the floor.

## How to run the skill

### Step 1 — Get the script

Ask the founder for the pitch script. Accept it pasted in chat or as an upload (`.txt`, `.md`, `.docx`). If they upload a `.docx`, read it with the standard file-reading approach.

If the founder hasn't provided the script and asks the skill to "make slides for my pitch" without one, ask for the script first. Don't write a script — that's stage 1's job (`../stages/1-pitch-coach.md`).

### Step 2 — Segment the script

Read the full script. Break it into **slide segments** — the granularity is *one idea per slide*. A segment may be a sentence, several sentences, or a paragraph; what matters is that one segment = one idea = one slide.

Common segment boundaries:
- A new topic ("Now let me show you the traction.")
- A new claim ("We've grown 5× in six months.")
- A new entity introduced ("Meet our co-founder, Sarah.")
- A pivot in argument ("But here's the problem…")
- A new number, named example, or comparison.

When unsure, split rather than combine.

### Step 3 — For each segment, design the slide

For each segment, decide:

1. **What is the one idea?** Say it in 5–10 words to yourself before writing slide copy.
2. **Does the idea need a visual at all?** Some moments — a story, a personal anecdote, a transition — are stronger with a black slide or a held image and no new content. Don't force a slide change every 6 seconds.
3. **What is the lowest-density treatment that works?** Run through the hierarchy: zero words → one word/number → short phrase → short caption. Pick the lowest tier that lets the slide carry the idea.
4. **What is the visual?** A photo, a chart, a number, a logo, a sketch, a single product shot, a side-by-side comparison, a held image from the prior slide. Specify what is shown.
5. **When does the slide appear?** Mark the exact word or phrase in the script where the slide should change. This is the *cue*.

### Step 4 — Produce the two output documents

Produce **both** of these as `.docx` files in `/mnt/user-data/outputs/`. Use the `docx` skill in `/mnt/skills/public/docx/SKILL.md` for the actual file generation.

#### Output A — Script-aligned table (for the founder's rehearsal)

A table that puts the script and the slides side by side, so the founder can rehearse with both in view at once.

| Column | Content |
|---|---|
| **#** | Slide number |
| **Script segment** | The exact words from the script that this slide covers, with the cue word/phrase **bolded** |
| **Slide copy** | The exact words to appear on the slide, or `[no text]` if the slide is image-only |
| **Visual** | Description of what is shown (image, chart, number, product shot, etc.) |
| **Cue** | The specific word or phrase in the script that triggers the slide change |
| **Notes** | Anything the founder or designer needs to know — e.g., "hold image from previous slide," "chart conclusion goes in caption," "minimum 40pt for readability" |

#### Output B — Slide-per-page (for handoff to claude.ai/design)

A document where **each slide gets its own page**. This is what gets uploaded to `claude.ai/design` (or handed to a designer) to produce the actual slides.

For each slide, the page contains:

```
SLIDE [N]

Slide copy:        [the words on the slide, or "no text"]

Visual:            [what is shown]

Cue:               [exact word/phrase in the script that triggers this slide]

Speaker says:      [the script segment]

Design notes:      [legibility floor, layout direction if any, color/contrast 
                    notes, "hold from previous slide" if applicable]
```

One slide per page. Page break between slides. This format is readable directly by `claude.ai/design`, which accepts `.docx` uploads and will use this structure to generate the actual slides.

## Examples

### Example 1 — A traction moment

**Script segment:**
> *"Six months ago we had a hundred users. Today we have **fifty thousand**, and we're adding two thousand a week."*

**One idea:** Explosive growth.

**Slide treatment:** A line chart, large, with a single trend going sharply up. Y-axis labeled "Users." Caption next to the line: **"500× in 6 months."**

**Cue:** When the speaker says "fifty thousand."

**Why:** The audience grasps the magnitude visually in a glance. The caption locks in the takeaway so they don't have to do the math. The speaker's words ("fifty thousand," "two thousand a week") and the slide's caption ("500× in 6 months") complement rather than duplicate — the slide compresses the trajectory into one figure.

### Example 2 — The "first thing"

**Script segment:**
> *"The **first thing** I want to talk about today is the problem we're solving."*

**One idea:** This is the first beat of three.

**Slide treatment:** Just the numeral **"1"** filling most of the slide.

**Cue:** When the speaker says "first thing."

**Why:** The speaker is going to do the talking; the slide does not need to. The numeral acts as a structural marker — the audience now knows where they are in the talk.

### Example 3 — A founder story

**Script segment:**
> *"My co-founder and I started this company because we lived this problem. We were running a logistics business in Lagos, and every Friday afternoon we'd lose two hours hunting down which truck had which shipment."*

**One idea:** The founders lived the problem.

**Slide treatment:** A single photo — the two founders standing in a warehouse or near trucks, ideally taken from their actual logistics days, otherwise representative. **No words.**

**Cue:** When the speaker says "started this company."

**Why:** A personal story is carried by the speaker's voice. Words on the slide here would steal attention from the human moment. A photo anchors the audience in the founders' world without doing any of the talking.

### Example 4 — The ask

**Script segment:**
> *"We're raising **three million dollars** to grow the team to fifteen people and reach a million users by end of next year."*

**One idea:** $3M ask.

**Slide treatment:** A single line of text, large: **"Raising $3M."**

**Cue:** When the speaker says "three million dollars."

**Why:** The number is what investors will remember and write down. Putting it on the slide as the sole element makes it stick. The supporting details (team size, user target) stay in the spoken track — they're context, not the takeaway.

## Common failures to avoid

- **Bullet lists of features.** Split into separate slides, one feature per slide, each as a single image or short phrase.
- **Title + body text on the same slide.** Drop the title; the content is the slide.
- **A screenshot of the product.** Almost always fails the 3-second test. If the product needs to be shown, zoom to one element with one label, or use a 3–4 step illustrated workflow across multiple slides.
- **A chart with multiple lines, axes, and legends.** Reduce to one trend with the conclusion as a caption. If multiple data dimensions matter, use multiple chart slides, each showing one dimension.
- **Putting the speaker's full sentence on the slide.** Compress to the most quotable phrase, or drop to image-only.
- **A "thank you" slide at the end with the team's email addresses, social handles, and logo.** The closing slide should hold the single most important thing the audience should walk out remembering — usually the company name + the one-line thesis, or just the ask. Contact info goes in the leave-behind, which is a different artifact.
- **Forcing a slide change every few seconds.** It's fine to hold an image while the speaker talks for 30+ seconds. Slide changes are a tool, not an obligation.

## When the founder asks for something out of scope

- *"Can you also fix my script?"* → Route back to stage 1 (`../stages/1-pitch-coach.md`). This stage produces slides for the script as written.
- *"Can you make me a teaser deck I can email to investors?"* → Explain that a teaser deck is a different artifact with different rules — readers consume it without a speaker, so it needs to be self-contained and denser. This skill produces presentation slides only.
- *"Can you make me a leave-behind?"* → Same as teaser. Different artifact, different rules.
- *"Can you design the actual slides?"* → This skill produces the *copy* and *visual specs*. To turn those into actual slides, hand Output B to `claude.ai/design`, a designer, or your own slide tool. The slide-per-page format is built for that handoff.

## Why these rules

The rules above stand on a single observation about how human attention works:

**The audience can process one stream of information at a time.** When the slide and the speaker compete, the audience must choose, and whichever wins, the other is wasted. So the slide and the speaker must run in parallel without competing — the slide carries the visual track, the speaker carries everything else.

Everything else follows from this:

- **One idea per slide** — because two ideas force the audience to decide which one to track.
- **3-second comprehension** — because anything longer pulls attention off the speaker for too long.
- **Compression and anchors only, never duplication or divergence** — because matching text duplicates the spoken channel (and the cognitive science shows this actively reduces comprehension), while different text creates two competing channels.
- **No bullets, no titles** — because bullets fragment reasoning into parallel-looking pieces that invite the speaker to read them, and titles set up the audience to read before listening.
- **Legibility floor** — because a slide that can't be read in the back row or in a small Zoom tile is just noise.

When in doubt, ask: *Does this slide help the audience listen, or does it pull them away?* That is the only test that matters.
