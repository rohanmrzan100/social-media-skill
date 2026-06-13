---
name: instagram-unskip
description: "Fix Instagram content that isn't getting reach. Engineers Reels, carousels, and single-image posts to lower skip rate, drive shares, generate saves, and provoke comments — the behavioral signals Instagram's algorithm actually rewards. Use whenever the user wants to create, plan, script, or improve any Instagram post; says 'my reels aren't reaching,' 'fix my Instagram,' 'help me with IG,' 'why isn't my content getting views,' 'make me a carousel/reel/post,' 'write an Instagram script,' 'IG hook,' 'caption for Instagram'; or references Reels, carousels, statics, or Instagram in any creation or optimization context. Self-contained: embeds the Instagram reach hierarchy, message-design framework (SUCCESs), short-form video structures, and caption craft. For paid IG ads, defer to ad-creative. For non-Instagram platforms (LinkedIn, TikTok, X), defer to social-content. Out of scope: Stories, Lives, Broadcast Channels."
---

# Instagram Unskip

> Most Instagram posts fail at second one. Not because the content is bad because the first frame asked the viewer to invest before earning the investment. This skill engineers posts to survive that first second, then turn attention into shares.

This skill teaches Claude how to produce Instagram content that distributes Reels, carousels, and single-image posts engineered against the behavioral metrics Instagram's algorithm actually uses to decide reach. It is self-contained: the message-design framework, the platform mechanics, and the caption craft are all in this file. No external skills or references required.

## When to use this skill

Use this skill when the user wants to:

- Create a Reel, carousel, or single-image Instagram post from scratch
- Improve, rewrite, or "fix" an existing Instagram post
- Diagnose why a post isn't reaching ("my reels are flopping")
- Plan a series of Instagram posts around a topic or campaign
- Write Instagram captions
- Build hooks or first frames for Reels
- Design carousel structures or slide-by-slide content

Trigger phrases include: "Instagram post," "IG carousel," "make a reel," "reel script," "fix my Instagram," "carousel slides," "Instagram hook," "IG caption," "post on Instagram," "Instagram content," "lower skip rate," "make this more shareable."

**Do not use this skill for:**

- Paid Instagram ads → use `ad-creative`
- Non-Instagram platforms (LinkedIn, TikTok, X, etc.) → use `social-content`
- Instagram Stories, Lives, or Broadcast Channels → out of scope for v1

---

## The core insight: Instagram ranks by skip rate, not likes

Instagram's ranking has shifted. Likes and comments are now validation signals — they tell creators their content was enjoyed, but they barely move reach. What actually decides distribution is a ranked set of behavioral signals based on what viewers do in the first three seconds and after they finish watching.

In priority order:

| # | Metric | What it measures | Effect on reach |
|---|--------|-----------------|-----------------|
| 1 | **Skip Rate** | % who swipe away in the first ~3 seconds | Single biggest reach killer. High skip = suppression |
| 2 | **Share Rate** | % who send the content to someone else (DM share) | Primary virality driver |
| 3 | **Save Rate** | % who save for later | Signals lasting value, sustained reach |
| 4 | **Repost Rate** | % who reshare to their own Story | Amplifies to new audiences |
| 5 | **Comment Rate** | % who comment | Drives conversation, secondary lever |
| 6 | **Like Rate** | % who tap like | Validation only, minimal reach impact |

**Source caveat.** Specific percentage weightings sometimes quoted by creators (e.g., "skip rate is 48.7% of the algorithm") come from individual Instagram Insights dashboards, not from a published Instagram algorithm spec. Adam Mosseri, head of Instagram, has publicly confirmed retention and sends matter most. Treat the ranking as directional, not as published weights.

**Strategic implication.** Engineer for **skip-rate-down + share-rate-up** first. Saves and comments are secondary. Likes are an output, not an input — never optimize for them.

This is the spine of every decision the skill makes. When in doubt, ask: does this choice lower skip rate or raise share rate? If neither, cut it.

---

## How to engineer each metric

### 1. Skip Rate — the first 1–3 seconds

The first second is the entire test. If the viewer's thumb has already moved by the time the first verbal line lands, the rest of the post never runs. Design for three simultaneous hooks at the same moment:

```
[VISUAL HOOK] + [VERBAL HOOK] + [TEXT OVERLAY]
```

All three must hit by frame 30 (≈1 second at 30fps) for Reels, or be visible on the cover for carousels and statics.

**Tactics that work:**

- **Pattern interrupt** — visual surprise, unusual frame, unexpected motion in the first 0.5 seconds. The brain stops scrolling to process novelty.
- **No slow intros** — kill the warm-up. No "Hey guys," no logo bumper, no establishing shot. Cut straight to the strongest moment.
- **Mid-action open** — start in the middle of the scene, not the beginning. The viewer fills in the setup; you skip the setup tax.
- **Curiosity gap** — open a loop the viewer must close. "The real reason your reels aren't reaching isn't what Instagram tells you."
- **Contrarian opener** — invert the take the viewer expects. If the conventional view is X, lead with not-X. Forces the brain to keep watching to resolve the contradiction.

**By format:**

- **Reels:** verbal + visual + text overlay must all land in the first second. The visual must be in motion or visually surprising — static talking-head openers die.
- **Carousels:** slide 1 carries the entire skip-rate load. If the cover doesn't earn the swipe to slide 2, slides 3–10 are dead weight.
- **Statics:** the image is the hook. Text and composition must communicate the core idea in under a second of feed scroll.

### 2. Share Rate — the virality lever

People share for three reasons:

1. **Identity signaling** — "This is who I am." They share to publicly associate with a viewpoint, aesthetic, or community.
2. **Helping someone they know** — "You need to see this." They share because the content solves a specific person's problem.
3. **Sparking a reaction** — "Get a load of this." They share because the content is provocative, surprising, or funny.

**Tactics that work:**

- **Hyper-specific relatability** — "If you've ever [oddly specific thing], this is for you." Specificity makes the content feel personally addressed, which makes people forward it to others who fit the description.
- **"Send this to…" prompts** — explicit, named share trigger. "Send this to the founder who still thinks brand doesn't move pipeline."
- **Identity-driven content** — "This is just like me" beats "this is useful." Useful content gets saved. Identity content gets shared.
- **Controversial / hot takes** — provoke share-as-debate. People share things they want to argue about.
- **Compressed insight** — a single sticky line worth forwarding on its own. The skill's job is to write that line.

### 3. Save Rate — future value

People save when the content has reuse value they'll need later.

**Tactics that work:**

- Tips and tricks in a scannable, checklist format
- Content series — "Part 1 of 6" makes the whole set savable; viewers save to bookmark the series
- Step-by-step process — a how-to they'll return to when they need to do the thing
- Reference frameworks — diagrams, lists, or models they'd want to look up later
- Specific numbers / data — anything quotable they'll want to cite

### 4. Repost Rate — Story amplification

Reposts to Story = viewer is willing to publicly endorse the content. This requires the content to match their public identity.

**Tactics that work:**

- Emotional hooks worth broadcasting
- Identity-aspirational content — what they want to be seen as caring about
- Quotable — a single line worth screen-grabbing for a Story
- Beautifully composed visuals — design quality matters here more than for in-feed shares

### 5. Comment Rate — conversation

Comments help, but they are a secondary lever. Optimize after skip and share.

**Tactics that work:**

- Polarizing takes that invite disagreement ("Most CMOs are still measuring the wrong thing.")
- Easy-to-answer questions with low friction ("Coffee or tea? Curious which side wins here.")
- Opinion prompts — "Hot take: __. Agree or disagree?"
- Fill-in-the-blank — "The best thing about a remote team is ___"

### 6. Likes — do not optimize

Likes are a downstream output. They follow good content; they do not cause distribution. Never make creative decisions in service of like rate.

---

## The message-design layer: SUCCESs

Engineering for the metrics above gets you watched. Making the content *worth watching* requires message design. Use the SUCCESs framework (Chip & Dan Heath, *Made to Stick*) as the quality control layer.

The framework exists because of the **Curse of Knowledge**: once you know something, you can't imagine not knowing it. You speak in abstractions; your audience needs concrete details. You assume context that doesn't exist. SUCCESs is the systematic fix.

Six principles. Not a checklist where you need all six — a diagnostic. Most posts fail on one or two specific principles. Find which, fix those.

### Simple — find the core

If the audience remembers only one thing, what must it be? Write that line first. The rest of the post serves it.

This is the **Commander's Intent**: the single sentence the whole post defends. Without it, the content has no spine.

Test: can a viewer who sees only the cover slide / first three seconds repeat the core idea back in their own words?

### Unexpected — break the pattern

Get attention with surprise. Keep attention with curiosity.

- **Surprise** — violate the schema. If the audience expects X, lead with not-X.
- **Curiosity gap** — point out what they don't know, signal that they should care, then fill the gap.

Surprise for its own sake (gimmicks) backfires. The surprise must serve the core message.

### Concrete — use sensory language

Replace abstractions with specifics. "Increase customer satisfaction" is abstract. "When a guest's towel falls in the pool, replace it before they ask" is concrete.

The **Velcro theory of memory**: the more sensory hooks an idea has, the more it sticks. Abstract ideas have few hooks. Concrete ideas have many.

For Instagram, this means:

- Use specific numbers, not "many" or "a lot"
- Use named examples, not "companies do X"
- Use sensory details — what you saw, heard, felt
- Reference specific moments, not categories

### Credible — let the message prove itself

Three sources of credibility, weakest to strongest:

1. **Authorities** — experts, credentials, celebrities
2. **The message itself** — vivid details, human-scale statistics, the "Sinatra Test" (one example that establishes credibility for an entire domain)
3. **The audience** — testable claims they can verify themselves ("Try this for one week and see")

Anti-authorities often beat authorities. A 29-year-old smoker dying of emphysema persuades more than a surgeon general. Lived experience > status.

Human-scale statistics: don't say "we processed 47 million data points." Say "the dataset is 600× larger than the one used in the original study." Numbers people can't intuit are forgotten.

### Emotional — make them care

Belief without feeling produces no action. Three levers:

- **Association** — link the idea to something they already care about (identity, in-group, aspiration)
- **Self-interest (WIIFY)** — answer "What's in it for you?" but go beyond features to identity — Maslow's peak, not basement
- **Identity** — appeal to who they are or want to be: "What would someone like me do?"

**Maslow's Basement problem:** most marketing defaults to base-level appeals (save money, save time). The strongest Instagram content appeals higher — to identity, belonging, esteem, self-actualization. "Don't Mess with Texas" worked because it linked anti-littering to Texan identity, not to environmental duty.

**Semantic stretch warning:** words like "unique," "quality," "innovative," "cutting-edge" have been used so often they have no emotional power left. If a word could apply to any account in your category, it's dead.

### Stories — run a mental simulation

Stories are flight simulators for the brain. Imagining an event activates the same neural regions as experiencing it. Stories don't just inform — they prepare people to act.

Three story patterns for Instagram:

- **Challenge** — underdog overcomes obstacles. Inspires persistence, effort, courage.
- **Connection** — people bridge divides. Builds empathy, teamwork, tolerance.
- **Creativity** — someone has an insight that solves a puzzle. Inspires innovation, new thinking.

You don't need to invent stories. Spot them — in your own work, in your customers' experiences, in the data. Retell them.

### SUCCESs diagnostic

When content isn't landing, this table identifies which principle is broken:

| Symptom | Broken principle | Fix |
|---------|------------------|-----|
| "It's confusing" or "too much going on" | Simple | Find the one line. Cut everything else. |
| "People scroll past" | Unexpected | Lead with the counterintuitive take. Open a curiosity gap. |
| "They nod but forget" | Concrete | Replace abstractions with sensory specifics and named examples. |
| "They don't believe it" | Credible | Add a vivid detail, a Sinatra Test example, or a testable claim. |
| "They believe but don't care" | Emotional | Make it about one person, not the category. Appeal to identity. |
| "They care but don't act / share" | Stories | Give them a mental simulation. Tell the story. |

---

## Format playbooks

### Reels (15–30 seconds)

Default structure:

```
[0.0–1.0s]   Pattern interrupt + verbal hook + text overlay (skip-rate defense)
[1.0–3.0s]   Promise / curiosity gap (why keep watching)
[3.0–22.0s]  Payload — the actual content
[22.0–28.0s] Insight crystallization (the shareable line)
[28.0–30.0s] CTA — "Send this to…" or "Save for later"
```

**Pre-write check (before scripting):**

- Skip rate: does the first frame stop the scroll?
- Share rate: what is the single line worth forwarding?
- Save rate: is there reusable value, or is it just entertainment?
- Comment rate: is there a question or take that invites response?

**Hook formulas for Reels:**

| Type | Pattern | Example |
|------|---------|---------|
| **Curiosity** | "The real reason [outcome] isn't what you think." | "The real reason your reels aren't reaching isn't the algorithm." |
| **Contrarian** | "[Common belief] is wrong. Here's why." | "Lead scoring is killing your pipeline. Here's what to do instead." |
| **Story** | "Last week, [unexpected thing] happened." | "Last week, a $4M deal closed because of a typo." |
| **Stakes** | "If you've ever [specific painful thing]…" | "If you've ever pitched a board and watched them check their phones…" |
| **Promise** | "[Number] [things] that [outcome]:" | "3 carousel openers that doubled my share rate." |

**On-screen text rules:**

- Max 2 lines on screen at once
- 3–5 words per line
- Bold sans-serif, with outline or background plate for legibility
- Match timing to speech exactly
- Highlight 1–2 key words in a different color

**Audio rules:**

- Bad audio kills retention faster than bad video
- Use a clip-on or shotgun mic; no built-in phone audio for talking head
- Add captions — most viewers watch without sound

### Carousels (5–10 slides)

Slide-by-slide responsibility:

| Slide | Role | Metric driven |
|-------|------|---------------|
| 1 (cover) | Hook + promise of payoff | Skip rate (carries 80%+ of the load) |
| 2 | Problem / curiosity gap | Skip rate continuation |
| 3 to N-1 | Payload — one idea per slide | Save rate |
| N (last) | CTA — share, save, or comment prompt | Share / save / comment |

**Rules:**

- One idea per slide. If two ideas fit, split into two slides.
- Title hierarchy must be readable in under a second at thumb-stop distance.
- Slide 1 must work as a standalone image — it appears in feed as the post preview.
- The final slide must name the action explicitly: "Save this for your next launch," "Send to the founder you know who…", not generic "Follow for more."
- The "shareable slide" (often slide 6 or the second-to-last) is the screenshot moment — design it as a standalone graphic.

**Carousel content patterns that consistently work:**

- **Diagnostic** — symptom 1, symptom 2, symptom 3 → fix
- **Inversion** — what the audience believes vs. what is actually true
- **Framework** — name the model, explain each component, show how to apply
- **Tear-down** — analyze a real example slide by slide
- **Numbered list** — N things that [outcome], one per slide

### Statics (single image)

The hardest format. No swipe to commit the viewer. Image + first caption line do all the work.

- **Image:** communicates the core idea in under a second
- **Caption first line:** the hook (curiosity gap, contrarian, or specific stat)
- **Caption body:** the payoff
- **Caption end:** CTA tied to one metric — usually save or comment for statics

Statics are at their best for: quotes, single-frame frameworks, before/afters, and aphoristic insights. They are bad for: explanatory content (use carousel) and motion-dependent content (use Reel).

---

## Caption craft

The image earns the swipe; the caption earns the share, save, or comment. Default tone: insight-led, executive, confident. No sales-speak, no "drop a 🔥 in the comments."

**Caption structure:**

```
[Line 1] — Hook line (visible above the "...more" fold). Either:
           - A sharper version of the post's core line, or
           - A contrarian setup that the post then resolves
[Body]   — 2–4 sentences of payoff. Add something the visual doesn't already say.
           Don't echo the carousel/reel — extend it.
[Close]  — A single CTA tied to one metric. Name the action specifically.
```

**Caption length:**

- Reels: 1–3 short paragraphs. The video is the content; the caption is the bridge to action.
- Carousels: 2–4 paragraphs. The caption adds the argument the slides imply but don't state.
- Statics: 3–5 paragraphs. The caption is doing more work because the image is fixed.

**Caption rules:**

- First line must work above the fold. Most viewers never tap "...more."
- No emoji-as-decoration. One emoji as a visual anchor at most.
- No hashtag walls in the caption — put 5–10 relevant hashtags in the first comment if needed (Instagram has explicitly said hashtags barely affect reach).
- No "link in bio!" without saying what's there.
- No "follow for more" — that's not a CTA, it's a wish.

**Caption hook formulas:**

- "Most [audience] think [X]. The data says [Y]."
- "The argument inside [common framing] assumes [thing]. Usually it doesn't."
- "[Specific result] in [short timeframe]. Here's the only thing that mattered:"
- "I changed my mind on [topic]. Here's why."
- "[Counterintuitive claim]. And it's not even close."

---

## Visual direction defaults

Default aesthetic for generated artifacts: elegant, premium, restrained, with intentional negative space. Apply unless the user specifies otherwise.

**Color:**

- Neutral base: ivory, off-white, or deep charcoal
- One accent color maximum — muted gold, deep teal, or a brand-specific accent
- No gradients on text. No drop shadows. No neon highlight boxes.

**Typography:**

- Editorial pairing: serif display (Playfair, Tiempos, Canela, GT Sectra) + clean sans body (Inter, Söhne, Neue Haas Grotesk)
- Clear hierarchy — display weight for hooks, regular weight for body, all at 2–3 distinct sizes
- Letter-spacing tight on display, neutral on body

**Layout:**

- Generous margins — 8–12% of canvas per side minimum
- Asymmetric layouts. Centered everything reads as default-AI.
- 50–60% negative space on hook slides

**What to avoid:**

- Drop shadows
- Gradient text
- Emoji-heavy designs
- Auto-generated stock graphics
- "Bold yellow box behind the headline" — recognizable as commodity hook-bait carousel style
- Centered text on every slide

When the user has provided a brand kit or established visual identity, apply that and override these defaults. When in doubt, ask which brand the post is for before generating visuals.

---

## Production workflow

When asked to create or improve an Instagram post, run this sequence.

### Step 1 — Stress-test the brief

Before producing anything, push back on weak inputs. This is the highest-leverage step.

Ask yourself:

- Is the topic specific enough to be shareable, or is it generic?
- Is the angle contrarian, or does it just confirm what the audience already believes?
- Is there a single line worth forwarding, or is this a wall of "useful" content?
- Is the CTA tied to a specific metric, or is it "engage with us"?

If the brief is weak on any of these, name the weakness to the user and offer a sharper angle before producing. Generic briefs produce generic posts.

### Step 2 — Clarify what's missing

Only ask what you can't infer from the request. Likely gaps:

- Format — Reel, carousel, or static? Infer if obvious; ask if not.
- Primary metric goal — share, save, or comment? Default to share if not specified.
- Brand voice / account — apply known voice if provided; ask if ambiguous.
- Topic / angle — provided, or are you supposed to suggest?

### Step 3 — Find the core (Simple)

Write the Commander's Intent line first — the one sentence the post defends. Everything else serves it. If you can't write the core line in plain English in under 15 words, the post doesn't have a core yet.

### Step 4 — Engineer the metric stack

- **Skip rate:** design second 1 / slide 1 specifically. What's the pattern interrupt?
- **Share rate:** identify the single shareable line. Where does it sit in the post?
- **Save / comment:** if relevant, bake them into the structure (series numbering, opinion prompt).

### Step 5 — Filter through SUCCESs

Run the draft against each principle. Don't try to score 6/6 — most posts only need 3–4 firing. The diagnostic is for finding what's *missing*.

- **Simple** — is the core findable in one line?
- **Unexpected** — does the opener break the expected take?
- **Concrete** — sensory and specific, not abstract?
- **Credible** — vivid detail, anti-authority, or testable claim?
- **Emotional** — appeals to identity, not just utility?
- **Stories** — runs a mental simulation?

### Step 6 — Produce the artifact

- **Reels:** shot-by-shot script with timing, on-screen text, and verbal lines. Indicate visual direction for each beat.
- **Carousels:** each slide as title + body + visual direction.
- **Statics:** image direction + caption.

### Step 7 — Write the caption

Apply the caption rules above. First line must work above the fold. The caption extends the visual — it doesn't echo it.

### Step 8 — Self-audit before delivery

Answer four questions out loud to the user:

1. What's the skip-rate defense in second 1 / slide 1?
2. What's the single shareable line?
3. What's the CTA, and which metric does it drive?
4. Where could this be cut shorter without losing the core?

The self-audit is part of the deliverable, not a private check. It teaches the user how to evaluate the next round.

---

## Worked example

**Brief:** "Make me a carousel on why marketing automation setups leak leads."

### Without this skill (generic agency output)

> **Slide 1:** "Why Most Marketing Automation Setups Leak Leads"
> **Slides 2–6:** Five reasons — no lead scoring, disconnected CRM, generic emails, no A/B testing, ignoring intent
> **Slide 7:** "Follow for more marketing tips!"
> **Caption:** "Marketing automation can be a game-changer, but most companies leave money on the table. Save this post and follow for more! #marketing #automation #leadgen"

Problems: cover restates the brief verbatim (no skip-rate defense), five equal tips with no Commander's Intent, no shareable line, generic CTA, caption echoes the visual.

### With this skill applied

**Step 1 — Stress-test:** The original framing ("why marketing automation setups leak leads") is generic agency-tip shape. Sharper angle: invert the assumption. The automation usually isn't broken — the sales handoff is.

**Step 2 — Commander's Intent:** *Fix the handoff, not the funnel.*

**Step 3 — Carousel:**

> **Slide 1 (cover):**
> Headline: *Your marketing automation isn't broken.*
> Subhead: *Your sales handoff is.*
> Visual: ivory background, deep charcoal serif headline, left-aligned, muted gold hairline rule, 60%+ negative space.
>
> **Slide 2 (curiosity gap):**
> Headline: *You're not losing leads in the funnel.*
> Subhead: *You're losing them in the gap between marketing and sales.*
> Visual: two minimal funnel outlines with a literal vertical gap between them, single gold accent line.
>
> **Slide 3 (symptom 1):**
> Title: *Symptom 1 — Hot leads going stale*
> Body: *MQL status hits at 11:42pm. Sales sees it 36 hours later. By then, your competitor has already replied to the same person.*
>
> **Slide 4 (symptom 2):**
> Title: *Symptom 2 — Marketing scores ≠ what sales closes*
> Body: *Your model rewards email opens. Your reps close on demo requests. Two different definitions of "qualified," one broken handoff.*
>
> **Slide 5 (symptom 3):**
> Title: *Symptom 3 — No round-trip data*
> Body: *Sales doesn't tell marketing why deals were lost. Marketing keeps producing the same broken MQLs. The loop never closes.*
>
> **Slide 6 (shareable slide):**
> Headline: *Fix the handoff, not the funnel.*
> Subhead: *A 30-second SLA between MQL and first sales touch beats any lead-scoring model.*
> Visual: full bleed, headline dominates. This is the screenshot moment.
>
> **Slide 7 (CTA):**
> Headline: *Send this to your sales lead.*
> Subhead: *Then book 30 minutes to map the handoff.*

**Caption:**

> The argument inside most marketing automation reviews assumes the automation is broken. Usually it isn't — the handoff is. A 30-second SLA between MQL and first sales touch will outperform another round of scoring tweaks.
>
> Save this if your funnel looks healthy but your close rate doesn't.

**Self-audit (delivered with the post):**

- Skip-rate defense (slide 1): contrarian inversion of the brief's own framing. Earns the swipe.
- Shareable line: "Fix the handoff, not the funnel." Slide 6 is screenshot-ready.
- CTA metric: share rate — slide 7 names a specific recipient ("your sales lead").
- Save trigger: diagnostic structure is reusable as a checklist.
- Cuts possible: slides 4 + 5 could merge for a 6-slide version, but the three-symptom rhythm does persuasion work — recommend keeping seven.

---

## Common failure modes to watch for

- **Cover slide that restates the brief.** "Why marketing automation setups leak leads" as the cover is a death sentence. Invert, narrow, or sharpen.
- **Five equal-weight tips.** No Commander's Intent. The viewer remembers nothing.
- **"Follow for more" CTA.** Not a CTA. Wishes are not metrics.
- **Caption that echoes the visual.** The caption must add the argument the visual implies but doesn't state.
- **Centered-text-on-yellow-box carousel aesthetic.** Reads as commodity hook-bait. The user's audience pattern-matches it to low-quality content and skips.
- **Talking-head opener.** No motion in the first 0.5 seconds = high skip rate.
- **Optimizing for likes.** Likes don't drive reach. Stop.

---

## Out of scope

- Paid Instagram ads → use `ad-creative`
- LinkedIn, TikTok, X, YouTube, other platforms → use `social-content`
- Instagram Stories, Lives, Broadcast Channels — not covered in v1
- Generating finished video files — this skill produces scripts, shot lists, on-screen text, and visual direction; rendering is done in CapCut, Premiere, Final Cut, or similar
- Scheduling and analytics — covered by tools like Later, Buffer, Metricool
