# AI Tells and the Say-It-Out-Loud Test

**Read this file before producing or critiquing any pitch text.**

This is the load-bearing reference for keeping pitch language in spoken human register and out of generic AI-shaped patterns. The same filter applies to two contexts:

- **When you're producing pitch text** — never write anything that violates this filter. Catch yourself before the line hits the page.
- **When you're critiquing a founder's draft** — flag every violation, name it, and rewrite the offending section using the founder's own facts.

## The primary diagnostic

> **Would a real human say this sentence out loud?**

If the answer is no, the sentence doesn't belong in the pitch. This applies to your output and to the founder's drafts equally.

Specific failure modes the test catches:

- Abstract nouns as subjects ("the implementation requires...")
- Multi-clause sentences with three subordinate ideas
- Sentences that need a comma to parse
- Words ending in -tion / -ment / -ity as the load-bearing verb-substitutes
- Anything that reads fluently but you can't imagine saying

The fix is almost always: replace the abstract subject with a person or company doing something. Abstract sentences become concrete the moment a human is the subject.

## Banned words

These are out. Drop entirely from your output. Flag every appearance in founder drafts and rewrite.

### Generic AI tells (drop in all contexts)
- nuanced
- transformative
- synergy
- delve
- unpack
- robust
- holistic
- seamless
- game-changer
- paradigm
- revolutionize
- compounds / compounding *(in all forms — including "compounding effects" / "compounding advantages")*

### Banned as verbs
- leverage *(use "use" or the specific action — "we use X to..." not "we leverage X to...")*
- disrupt *(when applied to the founder's own company)*

### Banned as metaphor
- landscape
- journey
- navigate
- ecosystem

### Banned in context
- alignment *(banned as an abstract noun — "we have great alignment" is out; "we aligned the team on X" is fine because there's a real action and object)*
- platform *(banned when used vaguely as a self-description — "we built an AI platform" is generic; "we built software that does X for Y" is specific)*

### Specifically out for pitches
- solution
- AI-powered *(if AI is genuinely involved, describe what it actually does)*
- next-generation

## Watch-list (flag, but don't auto-rewrite)

Watch-list items are amber-flag — they hit ≥50% across founders in distinct domains, but haven't crossed the ≥66% threshold for the banned list (see "How banned items get added to this list" at the bottom of this file).

**How to handle a watch-list item in critique mode:** flag it once with a brief note ("'Here's [X]:' is a common AI-tell shape — consider rewriting"), but don't force a rewrite. Watch-list items get promoted to banned if they hit ≥66% in subsequent samples.

**How to handle a watch-list item in Claude's own output:** prefer alternatives. If the natural phrasing would land on a watch-list item, choose a different shape. The watch-list is a soft constraint on Claude's drafting and a soft flag on founder critique.

### Watch-list words

These are often hiding something the founder hasn't figured out. When you see them, ask the founder for the specific thing the word is standing in for:

- experience *("'experience' is doing too much work here. What specifically?")*
- passionate
- mission-driven
- unique value proposition
- best-in-class

### Watch-list constructions

#### Stage-direction transitions: "Here's [X]:"

Constructions that *announce* the next beat instead of just delivering it. The pattern: "Here's [the problem / the opportunity / how / why / what's interesting / the thing]:" used as a verbal section header. The spoken equivalent of an H2 in a document — real speakers don't pre-announce sections, they just go to them.

❌ *"Here's the problem: collecting this data is expensive."*
✅ *"Collecting this data is expensive."*

❌ *"Here's how it works: we generate variants, then screen them in the lab."*
✅ *"We generate variants, then screen them in the lab."*

The fix: cut the announcement, go to the content. The colon is doing the work the actual sentence should do.

**Same family** (same vestigial-document-structure pattern, different surface):
- *"This is the problem we're solving."* (label after the fact)
- *"That's the opportunity."* / *"That's where we come in."* (transitional bridge into the next section)
- *"So how do we [solve it]?"* (rhetorical setup for the next paragraph)

#### "If you're excited about [grandiose vision]" closers

The shape: *"If you're excited about how [Company] is [unlocking / shaping / transforming / building the future of] [vision-language], come find me."*

The AI version of *"thanks for your time"* — generic excitement-laundering that sounds like a closing without doing the work of one. Filters for sycophants and gives the investor nothing concrete to respond to.

❌ *"If you're excited about how RakeML is shaping the future of building intelligence, come find us after."*
✅ *"More to share — find us after."* (when on-stage solicitation isn't allowed)
✅ *"Raising $2M, $100K minimum check, closing in eight weeks. If you're a fit, find me after."* (concrete soft-then-hard close)

The fix: use the soft-ask shapes in `opening-and-closing.md` — *"if you're a fit, find me after"* / *"more to share — find me after"*. Not the vision-language version.

#### "Join us in [vision-noun]" closers

The shape: *"Join us in this journey"* / *"Join us in building [grandiose thing]"* / *"Join us in the blue ocean before everyone else wakes up."* The vision-noun is usually a metaphor (a journey, a movement, a frontier) or a vision statement, not something specific.

This is the same shape as the "If you're excited about" tell — invitation-to-vision in place of a concrete ask. The investor doesn't know what they're being invited to *do*.

❌ *"Join us in this journey by scheduling a demo and starting a pilot."*
❌ *"Join us in building the largest university in the world."*
❌ *"Join us in the blue ocean before everyone else wakes up."*
✅ *"$250K minimum check, closing in eight weeks. If you're a fit, find me after."*
✅ *"More to share — find me after."*

The fix: replace the invitation with a concrete ask (when on-stage solicitation is allowed) or a concrete soft-ask (when it isn't).

## Banned constructions

### "It's not just X, it's Y." / "Not just X, but Y."
The reveal-the-real-meaning move. AI loves this construction because it sounds insightful. It's a tell.

❌ *"This isn't just a productivity tool, it's a workflow revolution."*
✅ *"We help engineering teams cut their code review time in half."*

### "It's about more than X — it's about Y."
Sibling of the above. Same reveal-the-real-meaning move, slightly different shape. Same fate.

❌ *"This is about more than software — it's about how teams collaborate."*
✅ *"We make code review take half as long."*

### "What X is, really, is Y." / "X is really about Y."
Third sibling. The "let me tell you what this really is" frame. Out.

### Em-dashes as a rhythm device
Em-dashes for actual asides (sentences with a clause that needs to be set off) are fine. The pattern that's banned is em-dashes used as stylistic punctuation `—like this—` to create rhythm. AI does this constantly.

❌ *"Our customers — and we have over 200 of them — love the product."*
✅ *"We have over 200 customers, and they love the product."*

### Triplet cadence
AI loves triplets. *"Faster, smarter, more reliable."* / *"Discover, design, deliver."* / *"For startups, for enterprises, for everyone."*

**One triplet per section is fine** — it's a real rhetorical device humans use.
**Adjacent triplets are banned** — two "X, Y, and Z" lists in close succession.
**Escalating triplets are banned** — "we're faster, smarter, and more reliable."
**Parallel-verb triplets are banned** — "we discover, design, and deliver."

If the founder has multiple triplets in a draft, keep the strongest one and rewrite the others into sentences with different shapes.

### Throat-clearing openers
- "In today's world..."
- "Now more than ever..."
- "In an era of..."
- "Imagine a world where..."

Out. Get to what you do.

### Rhetorical question openers
- "What does it mean to X?"
- "Have you ever wondered why X?"

Out. Statements only.

### Dictionary-style openers
- "X is..." (used as an opener for a category-defining claim)

Out. Lead with the company, not the category.

### "And we're just getting started"
Banned closer. Generic forward-looking flourish. Out.

Family of closers also out:
- "The future is bright."
- "We're just scratching the surface."
- "The opportunity ahead is massive."

If you want to leave the audience with a forward-looking idea, anchor it to a specific milestone with a date.

## Spoken-language register requirements

These aren't bans — they're positive requirements. Every line of skill output needs to satisfy these.

### Contractions are required
"We're" not "we are." "It's" not "it is." "Can't" not "cannot." "Won't" not "will not."

A founder who says "we are building" out loud sounds like a press release. The contraction makes it sound like a person.

### No abstract nouns as subjects
The subject of every sentence should be a person, a company, or a concrete thing — not an abstract concept.

❌ *"Implementation requires several weeks of integration work."*
✅ *"Most teams take a few weeks to integrate us."*

The abstract version reads fine. It sounds wrong out loud.

### No multi-clause sentences with three subordinate ideas
A speaker can't deliver a sentence with three subordinate clauses without sounding rehearsed. Break it up.

❌ *"By using our platform, which integrates with existing tools, customers can streamline their workflows while reducing the time spent on manual tasks, which historically have consumed up to 40% of their day."*
✅ *"Most teams spend 40% of their day on manual work. We cut that in half."*

### No sentences that need a comma to parse
If a sentence requires a comma for the listener to follow it, the listener won't follow it. Speakers don't have commas.

If you find yourself adding a comma to make a sentence work, break it into two sentences.

### Concrete proper nouns over abstract category words
Real customer names, real numbers, real product names beat abstract category words.

❌ *"We have several enterprise customers in the financial services sector."*
✅ *"Three of the top ten US banks are paying customers."*

If the founder doesn't have permission to name customers, use stage-of-business descriptors that aren't generic ("a top-five US bank" beats "a major financial services firm").

## How to flag and rewrite (the show-and-tell pattern)

When you find a violation in a founder's draft, the response shape is:

1. **Quote the violation** — show them exactly what's wrong
2. **Name the rule briefly** — one short reason it's a tell
3. **Rewrite using their own facts** — drop-in replacement they can use verbatim

**Example:**

> *"'We're transforming the way enterprises leverage their data ecosystems'* — three banned words in one sentence (transforming, leverage, ecosystems). Try:
>
> *'We help data teams at companies like [their actual customer names] cut their reporting time from days to hours.'*"

Don't lecture about why each word is banned. The flag plus the rewrite teaches faster than explanation.

## When to surface this filter to the founder

The skill enforces this filter silently in its own output (you never produce banned words, period). When a founder's draft has violations, surface them — but don't dump the whole list. Quote the specific violations, rewrite, move on.

If a founder's draft is heavily AI-shaped (10+ tells in a short pitch), name the larger pattern instead of fixing tells one by one:

> *"This reads like a draft an AI assistant would produce — which is what makes it sound like every other pitch. The fix isn't word-by-word edits at this point. The pitch needs to come out of how you actually talk about the company, not how you think a pitch should sound. Try saying it out loud, in your own words, and we'll work from that."*

The point is to redirect the founder away from polishing AI prose and toward generating their own. Once they bring back something that came out of their mouth, the skill works with it normally.

## How banned items get added to this list

The lists above are evidence-based, not aesthetic. There are two thresholds, and items can be promoted or demoted as the corpus grows.

**Threshold for the watch-list (≥50% across distinct domains):** A pattern qualifies for the watch-list when it appears in **at least half** the founders' pitches *across distinct domains* (e.g., biotech + geopolitical AI + healthtech, not three SaaS companies). At this level the pattern is real but not yet dominant — it gets flagged in critique but not auto-rewritten, and Claude prefers alternatives in its own drafting.

**Threshold for the banned list (≥66% across distinct domains):** A pattern moves from watch-list to banned when it crosses two-thirds of founders. At this level Claude treats it as out — never produces it, always flags and rewrites it in founder drafts.

**Same structural role.** The pattern has to show up doing the same job each time (announcing a section, closing a pitch, transitioning between beats). Coincidental word reuse in different roles isn't a tell.

**Same-founder repetition doesn't count.** Multiple drafts from one founder will share their voice naturally. Count founders, not drafts.

**Specific over generic.** Ban the *construction*, not the words. *"Here's the problem"* alone is too narrow (founders sometimes legitimately say it once). *"Here's [X] :"* as a section-header transition is the actual pattern; the ban catches the family.

**Demotion when the corpus grows.** A pattern can move *down* (banned → watch-list, or watch-list → off the list entirely) if a larger sample shows it doesn't hold. This isn't a failure of the methodology — it's the methodology working. Don't lower the threshold to keep a pattern on the list.

### Corpus log

The current lists were calibrated on a corpus of 11 pitch drafts from 6 distinct founders, spanning biotech, geopolitical-AI, building-data, healthtech, edtech, and African fintech.

When new pitch samples arrive, re-run the sweep on the combined corpus and update the lists per the thresholds above. The point is to be empirical, not opinionated.
