---
name: hook-machine
description: "Engineer hooks the data-driven way (Kallaway's 'Hook Machine' method), using your OWN scraped performance data instead of a paid tool. Don't ask AI to invent hooks from a blank page — that regresses to generic 'Are you tired of…' slop. Instead, mine a corpus of real winners vs. losers, extract why the winners worked, build a niche-specific scoring rubric, and critique/rewrite drafts against it. Consult whenever the user writes or sharpens a hook, opening line, or on-screen title for a Reel/short; asks for hook options on a topic; wants their draft hook scored or rewritten; or asks how to pick hooks from data. Replaces Sandcastles.ai with the repo's existing Apify pipeline (saubhya-data/refresh.sh) + scraped JSON. Pairs with instagram-unskip (single-post reach), fandom-funnel (audience-over-time strategy), reels-scripting and saubhya. Out of scope: full script body, production/shooting (solo-reel-shoot)."
---

# Hook Machine — data-driven hooks from your own corpus

> The hook is the highest-leverage line you write; it decides skip vs. stop. **Do not generate hooks blind.** AI writing hooks from nothing regresses to the mean of the internet — formulaic, generic, forgettable. The move is to use AI as an **analyst over a corpus of proven hooks**, derive a rubric grounded in *your* real numbers, then score and rewrite drafts against it.

Source: Kallaway, *"How To Create Irresistible Hooks With Claude."* His version sells a SaaS (Sandcastles.ai + an MCP plugin) as the data layer. **You don't need it** — this repo already has the same data pipeline. This skill captures the *method*, tool-agnostic, and points it at the data you already own.

## When to consult this skill

- Writing or sharpening any **hook / opening line / on-screen title** for a Reel or short.
- The user wants **hook options** on a topic, or a **draft hook scored or rewritten**.
- "How do I pick a hook from data?" / "why do my hooks get skipped?"
- Any time `instagram-unskip` or `saubhya` is producing the first 1–2 seconds of a piece — run this as the hook pass.

**Do not use for:** the full script body or production/shooting → `solo-reel-shoot`.

## The core lesson (read first, every time)

**Generator → Analyst.** AI's value here is pattern-extraction over a corpus you supply, not invention. The workflow is: gather proven hooks → split winners vs. losers → extract *why* → build a rubric → critique your drafts against it. The single most powerful step is **pasting your own draft for a graded rewrite**, not asking for fresh hooks.

---

## You already have the "Sandcastles" — here's the swap

| Sandcastles role | This repo's equivalent |
|---|---|
| Scrape top videos + metrics from your account + competitors | **`saubhya-data/refresh.sh`** — Apify scrape of the brand + 3 reference accounts, 50 posts each, dated snapshots in `saubhya-data/history/` |
| Store the corpus | **`saubhya-data/*_posts.json`** — already on disk |
| MCP plugin so the model can read the data | Not needed — **Claude reads the local JSON directly** |
| First-pass analysis | **`saubhya-data/analyze.py`** — already sorts by views and surfaces top captions |

The scraped JSON carries every field the method needs:
`videoPlayCount` / `videoViewCount` (winner/loser signal), `caption` (**the hook is line 1**), `commentsCount`, `videoDuration`, `hashtags`, `latestComments`, `likesCount`, `timestamp`.

For **any other account**, the method is identical: scrape it via Apify into the same JSON shape, then run the steps below. Nothing about this is Saubhya-specific except the filenames.

---

## The method (run on real data, not vibes)

1. **Refresh the corpus** (optional if recent): `bash saubhya-data/refresh.sh`. Apify is the data pipe. Skip if the JSON is current — don't re-scrape needlessly.
2. **Split winners vs. losers by a natural breakpoint.** Sort posts by `videoViewCount`/`videoPlayCount`; find where views *cliff*, don't just average. (For Saubhya: median ~567, ceiling ~6,300 — the cliff is well above median.) Label above/below.
3. **Extract the hooks.** Pull line 1 of `caption` for every winner and every loser. The hook is the unit of analysis, not the whole caption.
4. **Meta-analyze why winners won.** Compare winner vs. loser hooks for: framing (first-person moment vs. "New drop" catalog), specificity (concrete outcome vs. vague branding), trigger words, length, the curiosity gap. Output *patterns*, not "here are more like these."
5. **Build the rubric** = universal principles **+** patterns derived from this account's own data. Keep it explicit so it can be reused and audited.
6. **Generate and — more importantly — critique.** Offer options for a topic, but the real power move is scoring the user's *own draft* against the rubric and rewriting it. Iterate tight: "cut syllable count," "kill the jargon," "add a concrete number."

---

## The rubric (starting set — extend with each account's data)

**Universal (survive any niche):**
- **Specificity beats abstraction.** Concrete outcome/number > vague branding. (Same as `instagram-unskip`'s "concrete" lever.)
- **No throat-clearing.** The hook starts *on* the idea — no "Hey guys," no windup.
- **One curiosity gap.** Open a loop the viewer needs closed; don't answer it in line 1.
- **Write to one person** (Audience of One — see `fandom-funnel`), not a stadium.

**Saubhya-derived patterns (from her real winners):**
- Her ceiling post (6,312 views) was a **message — "it's not your body, it's the fit"** — not a product drop. *Message/POV hooks beat catalog hooks.*
- **First-person relatable moment** (Ekata model) outperforms "New drop."
- Breaking the catalog pattern ≈ doubles reach. Treat "New …", "Available now", price-led openers as **loser signals** to avoid.

> Re-derive the data-driven half of the rubric whenever the corpus is refreshed — patterns drift.

---

## How this composes with the other skills

- **`instagram-unskip`** owns single-post reach, including hook craft generally. This skill is the **data-grounded hook pass**: it picks/sharpens the specific hook using the account's real winners, then hands back to unskip for the rest of the post.
- **`fandom-funnel`** is the strategy layer (which person/stage the piece serves). A good hook still has to advance someone — check both.
- **`reels-scripting`** already uses Apify + Gemini for *reference-Reel* analysis; this skill uses the same Apify data for *hook-pattern* analysis. Complementary, not duplicate.
- **`saubhya`** — when scripting her Reels, run this on `saubhya-data` for the hook, and **honor her non-negotiables**: no backstory, no prices, no concept-list menus, one idea at a time. Loser signals above (catalog/price openers) are already aligned with her rules.
- **`solo-reel-shoot`** — production layer, out of scope here.

## One caution

Treat the **named tool (Sandcastles.ai), the MCP setup, and any exact numbers** as the author's heuristics and self-promotion, **not laws**. The durable, transferable ideas are: **AI-as-analyst-not-generator, winners-vs-losers from your own data, a rubric you can audit, and critiquing drafts over generating blind.** Lead with those.
