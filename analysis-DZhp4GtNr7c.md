# Audit — DGO/Himalaya Sports "Fake Football Fan" reel (@dreesti.grg · DZhp4GtNr7c)

_Posted 2026-06-13 12:21 UTC · collab with @watchdgo · paid FIFA World Cup 2026 promo. Live data via Apify, edit + compliance check via Gemini 2.5 Flash. This is the `dgo-fwc26-arsenal-story-reel-v2.md` script, executed._

## Live numbers
| Metric | This post | Note |
|---|---|---|
| Plays | **1,590** | |
| Views | **417** | |
| Comments | **18** | **the headline** — for context, @saubhya.np's all-time max is 4 |
| Plays/view | 3.8× | healthy replay despite a non-looping outro |
| Duration | 46.2s | long (script targeted ~35s) |
| Audio | original | not a trending clip — expected for a branded asset cut |

**The PASS mechanism is working.** The script's "comment PASS and I'll send the link" trigger is in the video, and the comments show people actually doing it (`sasuke_grg9: Pass`, `chaliseprakriti: Pass`, `____asmiiii: Pass`, `mahat_dipin: Pass` …). Every "Pass" is a high-intent viewer asking for the Season Pass link — that's a **conversion signal, not vanity engagement**. 18 comments on a creator-account promo is a strong result.

## ⚠️ Compliance — verify before this counts as clean (paid deal)
The DGO Influencer Guidelines in your script files are strict. The posted cut triggers three things to confirm with your POC (Aashish):

1. **FIFA trophy + "26 FIFA" branded graphics appear (0:21, 0:36, 0:39), plus animated players (Messi/Mbappé) and a "Red Bull FOOTBALL 26" outro.** The guideline says *no FIFA emblem/trophy/official look*. This is **only OK if those graphics came from the official DGO asset kit** (the OneDrive licensed-graphics link). They look supplied (price end-card + Red Bull co-brand = a DGO template), so this is probably fine — **but confirm they're official assets, not self-made.** If self-made, it's a violation.
2. **On-screen pricing shown: NPR 999 (TV) / NPR 549 (mobile).** Guideline: pricing must be **confirmed in writing by Aashish**. Make sure that written approval is on file — these exact numbers came from the brief, not a confirmation.
3. **Approval workflow:** send the live post URL to your POC **within 1 hour** of posting, and confirm written approval was obtained before it went up.

**What's compliant ✓:** approved phrase "Live & Exclusive On Himalaya Sports & Streaming On DGO" is present verbatim · TM cadence correct ("FIFA World Cup 2026™") · approved hashtags only (#MatchHimalayaMa #WeAreDGO #FIFAWorldCup2026) · brand names exact · no real match footage · no competitor/betting/politics.

**One caption nit:** the caption says matches *"in the best quality."* That's a (mild) quality claim the script never made; guidelines lean "facts only." Low risk since no competitor is named, but cleaner to drop it.

## Craft (vs the v2 script + frameworks)
**Strong:**
- **Hook (8/10):** "Confession: I was a fake football fan" text + football in hand + the confession VO — all three fire in second one. Exactly the self-own opener the script designed; far better than a polite "be honest" question.
- **Structure intact:** confession → Arsenal climb (joke→bottler→champion, "now everyone hates them") → 104 matches → Season Pass → PASS CTA. The identity/share lever and the comment driver both landed.

**Fix next time:**
1. **The caption is the biggest miss.** Posted line-1 is a generic *"Watch all FIFA World Cup 2026™ matches in the best quality 😛."* The script's caption — the **confession** + the team question + "Comment PASS" — is far stronger above the fold. You burned the most valuable caption real estate on boilerplate. Use the scripted caption next time.
2. **Trim the tail.** 46s is long; the last ~6s (0:40–0:46) is a branded sponsor/price card with animated players. It doesn't loop (Gemini: `loops: false`), so the auto-replay watch-through lever the script wanted is lost. Land the human CTA last and keep the price card shorter, or move pricing to caption.
3. **Hook visual:** script wanted the tight Arsenal-crest jersey-pull pattern interrupt; posted is "holding a football" — fine, but the crest-pull is a sharper scroll-stop for next time.

## Net
Reach engine and the conversion CTA are working (18 comments, real PASS intent). The two real to-dos: **(a) confirm the FIFA-branded graphics + pricing are officially approved** (paid-deal risk), and **(b) use the scripted confession caption** instead of the generic one-liner.

_Raw artifacts: `~/Desktop/Reels/reel_data_DZhp4GtNr7c.json`, `~/Desktop/Reels/analysis_gemini_DZhp4GtNr7c.json`, `~/Desktop/Reels/dreesti.grg_DZhp4GtNr7c.mp4`_
