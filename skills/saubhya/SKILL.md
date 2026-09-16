---
name: saubhya
description: "Create an Instagram Reel for @saubhya.np (Saubhya — premium, handpicked Nepali kurti brand). Use whenever the user asks for a 'saubhya reel', 'reel for saubhya', a Saubhya script / hook / caption / on-screen text, or any Instagram content for @saubhya.np. Loads Saubhya's brand context and her code-switched Nepali-English (Romanized) voice, writes the Reel using the instagram-unskip reach framework inside her 'everyday relatable life' territory, then hands the finished script to solo-reel-shoot to produce a phone-shootable shot list (she films solo or with one friend). Honors her hard rules: no personal backstory, no prices/discounts, no pre-packaged concept-lists — she leads the specifics. Out of scope: paid ads, non-Instagram platforms, Stories/Lives."
---

# Saubhya

> A brand-specific orchestrator for @saubhya.np Reels. It doesn't reinvent the reach framework — it loads Saubhya's real brand context and voice, routes the writing through `instagram-unskip`, enforces her hard rules, and hands the finished script to `solo-reel-shoot` so she can actually film it on her phone.

This skill is a **thin orchestrator**. The reach engineering lives in `instagram-unskip`; the shooting layer lives in `solo-reel-shoot`. This skill's job is to bring *Saubhya's* truth to both.

## When to use this skill

Use whenever the user asks for:

- "a saubhya reel", "reel for saubhya", content for @saubhya.np
- a Saubhya script, hook, caption, or on-screen text
- any Instagram Reel idea or rewrite for the kurti brand

**Do not use for:** paid ads, non-Instagram platforms (LinkedIn, TikTok, X), or Instagram Stories / Lives → out of scope.

## Step 0 — Load her context (always, first)

Before anything else, read **`saubhya-brand-context.md`** at the repo root. It is the private profile (gitignored) holding her positioning, audience, voice, reach data, benchmarks, and hard rules. Everything below is a summary — the file is the source of truth. If it's missing, say so and ask before guessing; do not invent brand facts.

Ground reach claims against `saubhya-data/` (her + 3 reference accounts' scrapes) when relevant.

## The non-negotiables (enforce every time)

These come straight from her explicit decisions. Violating any of them is a failed deliverable.

- **The page is NOT a catalog.** It's "a person who talks about things and happens to sell kurtis." ~80% relatable content, ~20% product. The kurti is the **vehicle, not the subject**.
- **Stay in the one territory she chose: everyday relatable life** — small, real moments Nepali women 18–40 live, kurti woven in. It's a *territory, not a concept list*.
- **She leads the specifics.** Do **NOT** pitch pre-packaged concept lists. Bring one idea at a time, ask before drafting, let her shape it.
- **⛔ NEVER use as content:** (1) her personal backstory — degree, origin, the scam, hard early days; (2) prices/discounts. These are private context only.
- **Voice = code-switched Nepali-English (Romanized).** Warm, genuine. Never salesy, fake-deep, or over-polished.
- **Premium register.** The brand is premium; content must FEEL it — restraint, not budget. No samey talking-head relatable-comedy skeleton, no self-deprecation as the default joke, no emoji-heavy on-screen text, **no "comment 👇" engagement-bait CTAs** (soft or no CTA). Levers: natural light, tactile fabric close-ups, calm pacing, one clean subject, quiet confidence, her taste/curation foregrounded. Full detail in `saubhya-brand-context.md` (hard rule 4).
- **🚫 Retired line:** never reuse *"it's not your body, it's the fit"* or close variants — Rohan flagged recycling it as cringe. The myth-bust frame stays; that line doesn't.
- **The test:** would a Nepali woman *not* shopping for a kurti still watch this and think "this is me"? If no, it's wrong.

## Reach levers specific to her (from her data)

- Metric is **views** (likes hidden). **Pull current numbers from `saubhya-data/saubhya_posts.json`** — `saubhya-brand-context.md` holds the last-checked snapshot; numbers copied into skill files go stale.
- **Her proven ceiling is the premium/tactile register.** Her top posts are quiet, feel-first, quality-led ("Soft enough to wear all day."; a quality-reassurance post) — not product drops, not relatable comedy. Breaking the "New drop" catalog pattern multiplies reach.
- **Kill the hashtag wall.** Her comment count is ~0 — conversation is untapped, but it must be *earned by the take* (a line people want to answer), never begged for with a "comment 👇" ask (premium rule).
- **Be "the Ekata of kurtis"** (@ekatatandukar, 85k): lead with the person not the product, first-person relatable hooks, match length to content (long talking videos are fine), product as a *soft resolution* at the end, name the product and tag the account.

## Workflow

### 1. Confirm the moment (don't pitch a list)

Ask her for the specific everyday moment / feeling she wants this Reel to be about — or react to one she brings. One idea at a time. Confirm the angle before drafting. If she's vague, offer to riff *together*, not hand her a menu.

### 2. Write the Reel via `instagram-unskip`

Once the moment is set, write the Reel using the `instagram-unskip` framework (skip-rate-down + share-rate-up, SUCCESs message design, Reel format playbook), but constrained by everything in Step 0 and the non-negotiables:

- Hook = a first-person, relatable life moment (Ekata model), not "New drop."
- Body = the moment, with the kurti present but not pitched.
- Resolution = product as a soft landing; name it, tag @saubhya.np.
- Conversation **earned by the take** — a line people naturally want to answer or argue with. Never a bolted-on "comment 👇" ask (premium rule).
- Caption in her Nepali-English voice; **no hashtag wall**.

Deliver the full script: hook, beat-by-beat, on-screen text, caption, and the `instagram-unskip` self-audit (skip-rate defense, the one shareable line, the line that earns conversation).

### 3. Hand off to `solo-reel-shoot`

Pass the finished script to `solo-reel-shoot` to produce a phone-shootable shot list. She films **solo (phone on a tripod)** or with **one friend**, budget phone + cheap clip-on mic, outdoor-lean. Don't design shots she can't film alone.

## Output

1. The confirmed moment/angle (one line).
2. The full Reel script (via `instagram-unskip`) in her voice, honoring every non-negotiable.
3. The `solo-reel-shoot` shot list so it's ready to film.

If at any step an idea drifts toward catalog-mode, backstory, or prices — stop and redirect to the everyday-relatable-life territory.
