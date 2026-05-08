# Linguistic Signature

A diagnose-only layer for catching voice homogenization that the AI-tells filter misses.

## Why this layer exists

The AI-tells filter (`ai-tells.md`) catches *specific bad patterns* — banned words, banned constructions, sentences that fail the say-it-out-loud test. A founder's draft can pass that filter completely and still sound like every other founder. The reason: AI-shaped writing isn't only about word choice. It's also about the *compression of variance* — sentence lengths normalize, vocabulary tightens to the high-probability middle, idiosyncratic markers (slang, fillers, "I" instead of "we," emotional intensity) get smoothed out.

This layer diagnoses that compression. It catches the homogenization that happens at the level of cadence, vocabulary range, and personal signature — not at the level of individual banned words.

## When to run this layer

Run it in three situations:

1. **After the AI-tells filter** — once the obvious tells are flagged, run this layer to catch the homogenization that survives the filter. Especially useful when an AI-tells pass came back clean but the draft still feels generic.
2. **On demand** — when a founder asks *"does this sound like me?"* or *"does this sound like AI wrote it?"* or *"why does my pitch sound generic when I removed all the buzzwords?"*
3. **As a guardrail when the skill itself is rewriting in Branch B** — before delivering a Branch B rewrite, the skill checks whether its own rewrite has flattened the founder's voice. If yes, the skill flags it on its own output and offers the founder the option to revert specific phrases to their original.

## The hard rule for this layer: diagnose only. Never rewrite.

This layer **inverts the show-and-tell pattern** that applies everywhere else in the skill. At every other layer (AI-tells, opening, four-slot, etc.), the skill diagnoses *and* rewrites. At this layer, the skill diagnoses and **stops**.

### Why this layer never rewrites

The skill doesn't know what the founder's idiosyncratic word would be. If the skill rewrites at this layer, it picks *its own* idiosyncratic word — which is just statistical regression to the mean wearing a different costume. The founder's voice can only be filled in by the founder.

The deeper version: the homogenization the skill is trying to catch *is caused by AI rewriting*. Adding more AI rewriting to fix it makes the problem worse, not better.

### The skill's voice posture

The skill stays **voice-neutral**. It doesn't try to imitate the founder's voice in its own rewrites at other layers, and it doesn't try to "fix" the founder's voice at this layer. The founder owns their voice; the skill points at where the voice is missing and asks the founder to put it back.

This means: when the skill rewrites at other layers (per the show-and-tell pattern in `pushback-gradient.md` and elsewhere), it writes in *clean spoken English* — not in the founder's voice, not in its own affected voice. Clean spoken English is the neutral default. The founder layers their voice on top.

## The four diagnostic checks

Run these four checks on any draft. For each, point at specific places — quote sentences or phrases — and ask the founder to fix in their own words.

### 1. Lexical range

**What to look for:** Vocabulary clustering in the high-probability middle. Generic word choices where a more specific or unusual one would land. Absence of any words that wouldn't appear in a generic AI rewrite of the same idea.

**Specific things to flag:**
- "Help" / "support" / "enable" / "deliver" / "provide" used as the load-bearing verb when something more concrete is available
- Generic intensifiers ("really," "very," "incredibly") doing work that a specific verb could do
- Abstract category words ("companies," "businesses," "organizations," "people," "users") where a concrete description fits
- Whole sentences with zero unusual or idiosyncratic words — every word sits at the high-frequency middle of the language

**The diagnostic question:**
> *"Sentence X uses 'help [customer] [generic verb] [generic outcome].' Every pitch in your category could write that sentence. What word would you actually use here if you were telling a friend at a bar what you do?"*

### 2. Syntactic variation

**What to look for:** Sentence lengths clustering around the same medium-length "polished" cadence. Absence of fragments. Absence of either very short punchy sentences or longer sentences that earn their length.

**Specific things to flag:**
- Five sentences in a row at 18–22 words each
- No fragments anywhere (real speakers use fragments — "Not just yet." / "Hardest part: distribution.")
- Every sentence using the same dependency shape (e.g., everything is "subject + verb + direct object + prepositional phrase")
- Absence of any sentence that would make a copy editor itch — clean prose is itself a tell

**The diagnostic question:**
> *"Your sentence lengths cluster around 20 words. Where would you naturally drop a fragment or a one-beat sentence? Real talk has rhythm; this draft doesn't."*

### 3. Trait markers

**What to look for:** Absence of personal *tells* — the words and patterns that mark this as a real human's writing. The research is clear: LLM rewrites systematically strip pronouns (especially "I"), conversational markers, age-marked vocabulary, swear words, emotional intensity, and dialect features.

**Specific things to flag:**
- Zero "I" in a solo-founder pitch (the "we" amplification effect)
- Zero conversational markers ("look," "honestly," "yeah," "okay so," "basically") in a draft that's supposed to be spoken
- Zero emotional intensity — no excitement, no frustration, no urgency in the wording, even when the topic warrants it
- Zero age- or context-marked vocabulary — nothing that would tell you whether the author is 28 or 58
- Generic register where the founder, in conversation, would use stronger language

**The diagnostic question:**
> *"There's no 'I' anywhere in this draft. Are you a solo founder? If yes, where would you naturally say 'I' instead of 'we'? Investors notice when a solo founder hides behind royal-we."*

> *"This reads completely flat — no excitement, no edge, no frustration with the problem. Where, in conversation, do you actually get fired up about this? That energy belongs in the pitch."*

### 4. Statistical-likelihood check

**What to look for:** Sentences that read like the most probable continuation of the prior sentence. Clichés. Stock phrases. Sentences that could appear, word for word, in any pitch in the same category.

**Specific things to flag:**
- "We're committed to delivering value to our customers" — every pitch ever
- "We believe [obvious thing about the market]" — would any competitor disagree?
- "Our mission is to..." — interchangeable with any other mission statement
- "We're passionate about..." — devoid of information
- Any sentence the founder could find by Googling "startup pitch examples"

**The diagnostic question:**
> *"This sentence reads as the most probable continuation — it could appear in any pitch in any category. What's the unexpected observation here? What would you say that wouldn't be in the median pitch?"*

This is what your reference prompt called the **"human pivot"** — an unexpected observation, a non-linear thought, a way of framing the situation that's specific to this founder. The skill points to where a pivot is missing; the founder writes it.

## How to deliver the diagnostic

The output is a list — three to five specific issues, each one quoting the offending text and asking a question. Not a rewrite.

### Example diagnostic

> *Three things to look at:*
>
> *— Sentence 4 ("We're committed to delivering value to enterprise customers across multiple verticals") reads as the most probable continuation. Could appear in any pitch. What would you actually say to describe what your customers get from you? Specifically.*
>
> *— Your draft has zero "I" — the voice is uniformly corporate "we." If you're a solo founder, that's a tell. Where would you naturally say "I"?*
>
> *— Sentence lengths cluster at 19–24 words across six sentences. No fragments, no short punchy beats. Real speech has rhythm; this doesn't. Pick one or two places to drop in a fragment or a five-word sentence.*

### What the output should NOT do

- ❌ Rewrite the offending sentences (that's the homogenization trap)
- ❌ Suggest specific replacement words (the skill's idiosyncratic word ≠ the founder's)
- ❌ Quantify with a score ("voice authenticity: 4/10") — this layer is qualitative; numerical scoring was already excluded skill-wide
- ❌ Praise generically ("Good draft, just a few notes!")

### What the output SHOULD do

- ✅ Quote specific text the founder wrote
- ✅ Name the specific issue (which of the four checks)
- ✅ Ask a question that points the founder back to their own voice
- ✅ Stop after three to five flags — more than that and the founder gets paralyzed

## When the founder asks the skill to fix it anyway

Founder request: *"Can you just rewrite it in my voice?"*

Skill response: *"I won't, and the reason matters. If I rewrite it, I'm picking words I think sound idiosyncratic — but they'd be my idea of idiosyncratic, not yours. The result would still be generic, just generic in a different direction. The voice has to come from you. The fastest way to get there: speak the pitch out loud, in your own words, and see what comes out. I'll work with that."*

This is the only place in the skill where a founder request gets a flat refusal that *isn't* the traction-faking case. It's worth holding the line because the alternative produces exactly the harm the layer exists to prevent.

## Connection to the skill's voice-neutral posture

This layer codifies a broader posture the skill takes:

- **The skill writes in clean spoken English** — neutral, plain, contracted. Not in any specific voice.
- **The founder layers their voice on top** — through the walking-and-talking generative work, through their own edits, through the diagnostic loop here.
- **The skill never tries to imitate the founder** — even when it has lots of the founder's writing to model from. The risk of caricature is too high.

When the skill rewrites at other layers (per the show-and-tell pattern), the rewrite uses the founder's *facts* (their actual customer, their actual numbers, their actual product) but not their *voice signature*. The voice signature is the founder's job, every time.
