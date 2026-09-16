---
name: meta-ads-strategy
description: "Plan and structure paid Meta (Facebook + Instagram) ad CAMPAIGNS — the media-buying layer, not the creative. Use whenever the user asks how to launch / set up / structure a Facebook or Instagram ad campaign, picks an objective, asks about budget / bid / placements / targeting / audiences / the learning phase / pixel / Conversions API / Advantage+ / Andromeda, asks 'how do I run ads', 'what budget', 'why are my ads not working', or wants a first-campaign plan. This is the PAID strategy counterpart to `ad-creative` (which owns the hooks/script/visuals): this skill owns objective, campaign/ad-set structure, placements, audience, budget, tracking, and how to read results — then hands the creative off to `ad-creative`. Grounded for @saubhya.np (Nepali kurti brand selling via DM, no online store) but the framework is brand-agnostic. Out of scope: the ad creative itself (→ `ad-creative`), organic posts (→ `saubhya` / `instagram-unskip`), non-Meta platforms."
---

# Meta Ads Strategy — the campaign/media-buying layer

> `ad-creative` makes the ad. **This skill decides where the money goes and what the algorithm optimizes for.** A brilliant creative pointed at the wrong objective burns budget; a mediocre creative on a clean, simple, well-targeted campaign at least learns. Get the structure right here, then send the creative brief to `ad-creative`.

This skill resolves the gap `ad-creative` explicitly leaves open: *"Out of scope: campaign/account structure, budget & bid strategy, pixel/audience setup."* That out-of-scope list is exactly this skill's job.

## When to use

- "How do I launch / set up my first Facebook or Instagram ad?"
- Choosing a campaign **objective** (the single biggest decision)
- Campaign / ad-set **structure**, **placements**, **targeting / audiences**
- **Budget** and how long to run before judging (the learning phase)
- **Tracking**: pixel, Conversions API, or just a messaging event
- "Why aren't my ads working?" / when to kill vs. scale
- A complete first-campaign plan for a brand

**Do NOT use for:**
- The ad's hook, script, on-screen text, visuals, CTA copy → **`ad-creative`**
- Organic (unpaid) posts → **`saubhya`** / **`instagram-unskip`**
- Non-Meta platforms (TikTok, LinkedIn, X, Google) → out of scope

---

## The one mental model: you optimize for ONE action

Meta optimizes each campaign for a **single action**. You cannot tell it "get me DMs *and* follows *and* awareness" — it will do the one you choose and treat the rest as exhaust. So:

1. Pick the **one action that makes money** as the objective.
2. Everything else (reach, follows, profile visits, brand awareness) comes **free as a byproduct** — you do not pay for or configure them separately.

| What the user wants | Is it an objective? | How they get it |
|---|---|---|
| DMs / messages to buy | ✅ yes (Engagement → Messaging) | make it the objective |
| Purchases on a website | ✅ yes (Sales → Conversions) | needs a store + pixel |
| Link clicks / catalog views | ✅ yes (Traffic) | needs a worthwhile destination |
| **Followers** | ❌ no objective exists | byproduct of good creative + profile visits |
| **Awareness / reach** | technically yes, but rarely the money move | every running ad already IS reach |

> If a user lists three goals (e.g. "DMs + follows + awareness"), don't run three campaigns. Pick the revenue one as primary; explain the other two are byproducts. This is the #1 beginner confusion.

## The current consensus (Meta Andromeda era, 2025–26)

Meta's ranking engine ("Andromeda") got materially smarter. The practitioner consensus — verified against r/DigitalMarketing field reports and how the platform actually behaves — is **"feed it clean signal + strong creative, then get out of the way."** Five rules:

1. **Go broad. Don't hand-target.** Detailed interest targeting is effectively dead for cold campaigns. Use **Advantage+ audience** / broad and let the algorithm find buyers. Narrow only *after* ~50 conversions of data.
2. **Simplify the structure.** `1 campaign → 1 ad set → 3–5 creatives.` **Test creatives, not audiences.** Splitting into 6 audiences starves each one of data.
3. **Creative is ~80% of the result.** "If the creative is weak, nothing helps." Native-looking beats designed-looking. (This is why `ad-creative` exists — but no structure can rescue bad creative.)
4. **Clean signal > big audience.** Andromeda rewards *signal quality*. Make sure the conversion event actually fires. **No data = no optimization.**
5. **Respect the learning phase.** Costs are high and erratic for the first few days. **Run 5–7 days untouched.** Editing an ad set **resets learning**. Most beginners kill winners after 48 hours.

> "Andromeda" is mostly **backend** — there is no dial to configure. As a beginner you tune nothing for it; you just follow the five rules. Treat any "secret Andromeda setting" advice as noise.

## Step 0 — load context (for a Saubhya campaign)

1. Read **`saubhya-brand-context.md`** — audience (Nepali women 18–40; UK/Aus diaspora), destination **`app.reffero.com/saubhya`**, product (short kurtis, tops, 3-piece sets), and the hard rules (no backstory, no invented prices).
2. Confirm the **business goal in one action** before choosing anything (see decision tree).
3. The creative comes from **`ad-creative`** — this skill produces the *brief* (objective, audience, what the ad must drive), not the ad.

## Step 1 — pick the objective (decision tree)

- **Sells in DM / chat, no website** (Saubhya's case) → **Engagement** objective, conversion location **Messaging apps → Instagram Direct** (and/or Messenger). Makes a "Send Message" button ad; optimizes for people likely to message. **No pixel/CAPI required.**
- **Has a real online store** → **Sales** objective, optimize for **Purchase**. Requires pixel + ideally Conversions API.
- **Has a landing page / catalog / Linktree worth visiting** → **Traffic** (optimize for landing-page views, not just link clicks).
- **Pure top-of-funnel, no sales path yet** → **Awareness** (cheapest reach) — but flag that there's no built-in route to revenue.
- **Wants followers** → there is no objective for this; route through Engagement/Traffic to the profile and let good creative convert. Set expectations.

## Step 2 — campaign structure (keep it brutally simple)

```
Campaign  (objective from Step 1)
└─ Budget: CBO / Advantage Campaign Budget = ON   (let Meta distribute spend)
   └─ Ad set ×1            (do NOT split into many)
      ├─ Optimization event = the action from Step 1 (e.g. Conversations)
      ├─ Audience: BROAD — geo + gender + age only, no detailed interests
      └─ Ads ×3–5          (the creatives — briefed to ad-creative)
```

One ad set. One objective. Several creatives competing inside it. That's the whole first campaign.

## Step 3 — placements ("Instagram & Facebook only")

- **Default best performance:** leave **Advantage+ placements ON** (Meta auto-places, usually cheapest).
- **If the user insists on IG + FB only:** switch to **Manual placements** and tick only **Facebook + Instagram** (Feed, Reels, Stories, Explore). Untick **Audience Network** and Messenger placements.
- **Trade-off to state plainly:** forcing IG+FB-only typically **raises cost** vs. letting Meta auto-place, because you remove inventory the algorithm could have used. Worth it only if there's a real reason to avoid Audience Network (e.g. brand-safety, junk placements). For most small brands, Advantage+ placements win.

## Step 4 — audience (broad, per the consensus)

- Geo: where they actually ship (Saubhya: **Nepal**; optionally a separate ad set for **UK/Aus diaspora** later — *after* the home campaign works).
- Gender / age: match the brand (Saubhya: **women, ~18–40**).
- **Interests: none** on the first cold campaign. Let Andromeda find them.
- **No lookalikes / retargeting yet** — you have zero conversion data to build them from. Those come in a *later* phase once the pixel/messaging events have fired enough.

## Step 5 — budget (be realistic, not US-blog-realistic)

- US sources quote **$50–100/day** as the floor to exit learning. That's **US CPMs — do not copy the dollar figure** to Nepal.
- **Nepal CPMs are a fraction of US.** For a first test, **NPR 500–1,000/day (~$4–8)** on the single ad set is a sensible start.
- **Put it all on the one ad set** — don't spread a small budget thin. Thin budget = algorithm can't learn = "ads don't work."
- **Run 5–7 days before judging or editing.** No panic edits.
- Lower budget is fine, it just **learns slower**. State that trade-off rather than promising fast results.

## Step 6 — tracking (only as much as the goal needs)

- **DM / messaging goal (Saubhya):** you do **NOT** need full Conversions API or a pixel. Track the **"Click to Message" / Conversations** event Meta provides natively and optimize on that. Meta just needs to learn *who actually messages*.
- **Website-sales goal:** then yes — install the **pixel + Conversions API** so purchase signal is clean. "No data = no optimization."
- Don't over-build tracking for a goal that doesn't need it; don't under-build it for one that does.

## Step 7 — read results & decide (after the learning window)

Judge on the **money metric**, not vanity:

- DM campaign → **cost per conversation started**, and crucially **how many DMs became sales** (track this manually; Meta can't see your chat closes).
- **Kill** a creative that, after the learning window, has clearly high cost-per-result vs. the others.
- **Scale** a winner *gradually* (≈20% budget bumps every few days — big jumps re-trigger learning).
- Only **then** consider: a diaspora ad set, a retargeting/lookalike audience, fresh creative angles. One change at a time.

## What to ignore (first campaign)

- ❌ Detailed interest targeting / audience stacking
- ❌ Lookalikes & retargeting (no data yet)
- ❌ Manufactured "Andromeda settings" (backend; nothing to set)
- ❌ Full pixel/CAPI when selling purely in DM
- ❌ Many ad sets, daily edits, panic-killing at 48h

## Handoffs

- **Creative → `ad-creative`.** Once objective + audience + the one action are set, brief `ad-creative` to produce the 3–5 ads (hook, anatomy, on-screen text, hard CTA to `app.reffero.com/saubhya`). This skill gives it the *target*; it gives the *ad*.
- **Production → `solo-reel-shoot`** (via `ad-creative`) — phone-shootable, founder-led, which is the native, trust-building format for paid anyway.

## Output of this skill

1. The **single objective** + why (tied to the user's real money action).
2. The **campaign structure** (objective, CBO, 1 ad set, optimization event).
3. **Placements** decision (Advantage+ vs. IG+FB-only, with the cost trade-off stated).
4. **Audience** (geo/age/gender, broad).
5. **Budget + run-time** plan in the brand's real currency, with the learning-phase rule.
6. **Tracking** scope (what to set up, what to skip).
7. **A creative brief to hand to `ad-creative`** (objective, avatar/angle direction, the one action the ad must drive).
8. **What to measure** and the kill/scale rule.

## How it composes

- **`ad-creative`** — the paired paid skill. That one says "out of scope: campaign structure/budget/pixel/audience" → **this** is that scope. Together they're the full paid playbook: this = where/how the money runs, that = the ad itself.
- **`saubhya` / `instagram-unskip`** — the **organic** skills (felt-not-sold, no prices). Paid is a different mode: selling is the job. Don't mix.
- **`saubhya-brand-context.md`** — source of truth for audience, destination link, and the off-limits rules (which hold in paid too — never invent prices).

## One caution

Specific numbers here are **starting points, not laws**: the $50–100/day US floor, the NPR 500–1,000 Nepal start, "5–7 days", "~50 conversions". Platform behavior and "Andromeda" specifics drift — the **durable** truths are: *optimize for one money action, go broad, keep structure simple, feed clean signal, respect the learning phase, and let creative do the heavy lifting.* Re-verify current platform mechanics before treating any exact figure or feature name as fixed.
