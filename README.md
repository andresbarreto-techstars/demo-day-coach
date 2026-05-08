# Demo Day Coach

A Claude skill that guides founders end-to-end through demo day pitch and deck preparation.

**Script first. Slide copy second. Design spec third. Render last.** The single most-common founder mistake is starting with the deck — designing slides before the script is done locks in bad framing and burns days fighting it. This skill exists to break that inertia and run the chain in the right order.

## What it does

A single entry point for the entire pitch-and-deck journey. Trigger it when a founder mentions demo day, pitching investors, building or designing a pitch deck, or any step in the pitch-and-deck pipeline.

The skill coordinates a strict three-stage chain:

| Stage | Owns |
|---|---|
| 1 — Pitch coach | The pitch script — the actual words the founder says |
| 2 — Script to slide copy | Slide copy and visual specs for the live deck |
| 3 — Slide copy to design | The markdown design spec handed to `claude.ai/design` |

Out of scope: rendering the actual deck (that's `claude.ai/design`'s job), brand identity, teaser decks, leave-behinds, delivery coaching, Q&A prep.

## Install

### Option 1 — Claude Code plugin (recommended)

Add this repo as a Claude Code plugin marketplace, then install the plugin. You'll get auto-updates whenever this repo is updated.

```
/plugin marketplace add andresbarreto-techstars/demo-day-coach
/plugin install demo-day-coach@demo-day-coach
```

To pick up the latest version later:

```
/plugin marketplace update demo-day-coach
```

### Option 2 — Plain skill folder

If you'd rather install just the skill files directly, drop the `skills/demo-day-coach/` folder into your Claude skills directory.

```bash
git clone https://github.com/andresbarreto-techstars/demo-day-coach.git
cp -r demo-day-coach/skills/demo-day-coach ~/.claude/skills/
```

To update later:

```bash
cd demo-day-coach
git pull
cp -r skills/demo-day-coach ~/.claude/skills/
```

## How to use it

Once installed, just ask Claude something like:

- "Help me with my demo day pitch"
- "I have to pitch investors next week"
- "Build me a pitch deck"
- "Fix my pitch script"
- "Make my pitch sound less like AI"
- "What should go on my slides?"

The skill will diagnose where you are in the pipeline (nothing yet, scattered notes, draft script, finished script, slide copy, etc.) and route you to the right stage. It refuses to start with the deck — that's the whole point.

## Repo layout

```
demo-day-coach/
├── .claude-plugin/
│   ├── plugin.json                  ← plugin manifest
│   └── marketplace.json             ← marketplace manifest
├── skills/
│   └── demo-day-coach/
│       ├── SKILL.md                 ← umbrella / entry point
│       ├── stages/
│       │   ├── 1-pitch-coach.md
│       │   ├── 2-script-to-slide-copy.md
│       │   └── 3-slide-copy-to-design.md
│       └── references/
│           ├── ai-tells.md
│           ├── elicitation-scripts.md
│           ├── four-slot-formula.md
│           ├── linguistic-signature.md
│           ├── live-pitch-spec-template.md
│           ├── opening-and-closing.md
│           └── pushback-gradient.md
├── README.md
└── LICENSE
```

## License

MIT — see [LICENSE](LICENSE).
