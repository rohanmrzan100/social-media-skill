---
name: hook-machine
description: "Engineer hooks the data-driven way (Kallaway's 'Hook Machine' method), using your OWN scraped performance data instead of a paid tool. Don't ask AI to invent hooks from a blank page — that regresses to generic 'Are you tired of…' slop. Instead, mine a corpus of real winners vs. losers, extract why the winners worked, build a niche-specific scoring rubric, and critique/rewrite drafts against it. Consult whenever the user writes or sharpens a hook, opening line, or on-screen title for a Reel/short; asks for hook options on a topic; wants their draft hook scored or rewritten; or asks how to pick hooks from data. Replaces Sandcastles.ai with the repo's existing Apify pipeline (saubhya-data/refresh.sh) + scraped JSON. Pairs with instagram-unskip (single-post reach), fandom-funnel (audience-over-time strategy), and saubhya. Out of scope: full script body, production/shooting (solo-reel-shoot)."
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
2. **Split winners vs. losers by a natural breakpoint.** Sort posts by `videoViewCount`/`videoPlayCount`; find where views *cliff*, don't just average. (For Saubhya: pull the current numbers from `saubhya-data/saubhya_posts.json` — never trust numbers copied into skill files; they go stale. `saubhya-brand-context.md` holds the last-checked snapshot.) Label above/below.
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
- **Relatability gate.** A desire-based hook dies the instant the viewer decides the person/character isn't *like them*. Score every hook: does the subject read as a peer, or as someone with an **unfair advantage** (money, time, talent, special access)? Peer ⇒ stop; unattainable ⇒ scroll. The closer the character to the viewer, the stronger the pull.
- **Constraint-free framing.** State the dream outcome, then make the method read as **simple, low-resource, repeatable**. "Took a month off and still grew 11k" wins because the *how* sounds effortless. If the hook implies you need cash/credentials/luck, it converts desire into "not for me." Treat any implied unfair advantage as a **loser signal**.

**Saubhya-derived patterns (re-derive from the live data; `saubhya-brand-context.md` is the source of truth):**
- Her current ceiling posts are **quiet, premium, feel-first** ("Soft enough to wear all day."; a quality-reassurance post) — not product drops and not relatable comedy. *Message/POV and tactile hooks beat catalog hooks by an order of magnitude.*
- A **contrarian/myth-bust opener** (name a belief → overturn it) is a proven winner signal in her data — make it deliberate (Frame 6), don't wait for it to happen by accident. ⚠️ But the specific line **"it's not your body, it's the fit" is RETIRED** (Rohan flagged recycling it as cringe) — reuse the *frame*, never that line or a paraphrase of it.
- **First-person relatable moment** (Ekata model) outperforms "New drop" — but it must pass the **premium-register gate** (brand context, hard rule 4): no comedy skeleton, no "comment 👇" bait.
- Breaking the catalog pattern multiplies reach. Treat "New …", "Available now", price-led openers as **loser signals** to avoid.

> Re-derive the data-driven half of the rubric whenever the corpus is refreshed — patterns drift.

---

## Desire-based frames (structures to fill, not blank-page invention)

Five grammatical frames for the same move — *lead with the dream outcome a relatable peer reached via a constraint-free method.* These are scaffolds you fill **from the corpus and the rubric above**, not prompts to invent hooks from nothing — that would violate the core lesson. Use them when a draft is stuck or you need angle variety on one topic.

1. **About Me (looking back)** — *"I [did simple thing] and still [outcome]."* Recounts a result via a repeatable method. e.g. "Took a break from posting for a month and still grew 11k."
2. **If I (looking forward)** — *"If I were starting from scratch, here's exactly what I'd do to [outcome] in [N simple steps]."* Hypothetical step-by-step path.
3. **To You (direct address)** — *"If you want [desire], this one trick makes it easy."* Viewer is the character; a simple method for their problem.
4. **Can You? (question)** — *"Is it possible to [outcome] in [tight constraint]?"* Invites the viewer to imagine achieving it.
5. **He/She Just Did (third-party proof)** — *"This [relatable person] [achieved outcome] by [simple method]."* Social proof via a peer, not a celebrity.
6. **Contrarian / Myth-Bust (name the belief, then break it)** — *"Most [peers] think [common belief] — actually [reframe]."* Lead with a take a chunk of the audience quietly holds, then overturn it. Does **double duty**: it's a peer-POV scroll-stop *and* a comment engine — people self-tag ("omg this is me"), agree, or argue, and that conversation is the reach lever. This frame is proven in Saubhya's own data — her early myth-bust post out-reached every catalog post around it. Treat it as a deliberate move, not a lucky one-off. ⚠️ That post's line ("it's not your body, it's the fit") is **retired** — build a fresh belief→reframe each time; never reuse or paraphrase the old line. Guardrails: the contrarian take must be **about a belief/feeling**, never a swipe at the customer, a competitor, or anything off-brand — and it still honors her non-negotiables (no backstory, no prices, no concept-lists). The comment-volume side of this lever is `instagram-unskip`'s comment-rate tactic; this frame is the *hook* form of it.

**Saubhya translation:** the *funnel/lead-gen* origin of these frames does **not** apply to her brand. The transferable part is the relatability + constraint-free principle inside her "everyday relatable life" territory — and frames 1, 3, 5, 6 adapt cleanly (her proven myth-bust winner was a *Contrarian/Myth-Bust* + *To You* move — the frame transfers; the retired line doesn't). Still honor her non-negotiables: no backstory, no prices, no concept-list menus.

---

## How this composes with the other skills

- **`instagram-unskip`** owns single-post reach, including hook craft generally. This skill is the **data-grounded hook pass**: it picks/sharpens the specific hook using the account's real winners, then hands back to unskip for the rest of the post.
- **`fandom-funnel`** is the strategy layer (which person/stage the piece serves). A good hook still has to advance someone — check both.
- **`saubhya`** — when scripting her Reels, run this on `saubhya-data` for the hook, and **honor her non-negotiables**: no backstory, no prices, no concept-list menus, one idea at a time. Loser signals above (catalog/price openers) are already aligned with her rules.
- **`solo-reel-shoot`** — production layer, out of scope here.

## One caution

Treat the **named tool (Sandcastles.ai), the MCP setup, and any exact numbers** as the author's heuristics and self-promotion, **not laws**. The durable, transferable ideas are: **AI-as-analyst-not-generator, winners-vs-losers from your own data, a rubric you can audit, and critiquing drafts over generating blind.** Lead with those.
