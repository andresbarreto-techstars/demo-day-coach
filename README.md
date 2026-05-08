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

Pick the option that matches your comfort level. All three end up at the same place — Demo Day Coach loaded into Claude.

| If you... | Use |
|---|---|
| just want to download a zip and click upload | [Option A — One-click zip](#option-a--one-click-zip-no-terminal-no-git) |
| are comfortable in the terminal and use Claude Code | [Option B — Claude Code plugin](#option-b--claude-code-plugin) |
| want to clone the repo and copy folders manually | [Option C — Manual git install](#option-c--manual-git-install) |

---

### Option A — One-click zip (no terminal, no git)

The easiest way. You'll download one zip file and upload it to Claude. No command line, no GitHub account, no git.

**Step 1 — Download the skill**

Go to the [latest release](https://github.com/andresbarreto-techstars/demo-day-coach/releases/latest) and download `demo-day-coach.zip`.

Direct link (always points to the most recent build): https://github.com/andresbarreto-techstars/demo-day-coach/releases/latest/download/demo-day-coach.zip

**Step 2 — Upload it to Claude**

Where you upload depends on which Claude product you're using:

<details>
<summary><b>Claude.ai (web)</b></summary>

1. Go to [claude.ai](https://claude.ai) and sign in.
2. Click your profile (bottom-left or top-right depending on the layout) → **Settings**.
3. Open **Capabilities** → **Skills** (the menu may also call it **Custom skills**).
4. Click **Add skill** (or **Upload skill** / **Create skill** / the **+** button).
5. Drag `demo-day-coach.zip` onto the upload area, or click to browse and select it.
6. Wait for the green checkmark / "uploaded" confirmation.

The skill is now available in any new conversation. To trigger it, just ask Claude something like *"help me with my demo day pitch."*

</details>

<details>
<summary><b>Claude desktop app / Cowork</b></summary>

1. Open the Claude desktop app.
2. Open **Settings** (cog icon).
3. Go to **Plugins & Skills** (or **Capabilities**).
4. Click **Add custom skill** / **Upload skill** / the **+** button.
5. Drag `demo-day-coach.zip` onto the upload area, or click to browse and select it.
6. Confirm when it appears in your installed skills list.

The skill is now available in any new conversation. To trigger it, just ask Claude something like *"help me with my demo day pitch."*

</details>

**Step 3 — Update later**

When the skill gets updated, just come back to the [latest release page](https://github.com/andresbarreto-techstars/demo-day-coach/releases/latest), download the new `demo-day-coach.zip`, and re-upload it the same way. Claude replaces the old version.

> **Don't see a Skills / Plugins section in your settings?** Custom skill upload may not be available in every Claude plan or product yet. If that's you, try Option B or Option C, or check Anthropic's [help docs](https://support.claude.com) for the current way to add custom skills.

---

### Option A.5 — Manual zip from this repo (fallback if Releases is empty)

If the Releases page hasn't been built yet, or you prefer to grab files directly from the repo, follow this path. Slightly more steps than Option A but no command line.

1. On the repo's [main page](https://github.com/andresbarreto-techstars/demo-day-coach), click the green **Code** button.
2. Click **Download ZIP** at the bottom of the dropdown. This downloads the whole repo as `demo-day-coach-main.zip`.
3. Open the downloaded zip (double-click on Mac/Windows). You'll get a folder called `demo-day-coach-main`.
4. Inside that folder, find `skills/demo-day-coach/`. **This** is the skill — not the parent folder.
5. Compress just that `demo-day-coach` folder:
   - **Mac:** right-click `demo-day-coach` → **Compress "demo-day-coach"**. You'll get `demo-day-coach.zip`.
   - **Windows:** right-click `demo-day-coach` → **Send to** → **Compressed (zipped) folder**. You'll get `demo-day-coach.zip`.
6. Upload that `demo-day-coach.zip` to Claude using the steps in Option A → Step 2.

---

### Option B — Claude Code plugin

If you use [Claude Code](https://docs.claude.com/en/docs/claude-code), this is the cleanest path. The plugin auto-updates from this repo.

```
/plugin marketplace add andresbarreto-techstars/demo-day-coach
/plugin install demo-day-coach@demo-day-coach
```

To pick up the latest version later:

```
/plugin marketplace update demo-day-coach
```

---

### Option C — Manual git install

For terminal users who prefer dropping the skill folder directly into their Claude skills directory.

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
├── .github/workflows/
│   └── release.yml                  ← auto-publishes the zip to Releases
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
