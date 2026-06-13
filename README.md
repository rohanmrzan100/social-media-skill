
# Social Media Skills for AI Agents

The complete set of Claude skills behind Charlie Hills' content system. 350k+ followers across LinkedIn, Instagram, Substack, X and YouTube. 100m+ views per year. All running through one system that starts with the newsletter and flows out to every other channel.

Built by [Charlie Hills](https://charliehills.substack.com). Subscribe to the [MarTech AI newsletter](https://charliehills.substack.com) for weekly breakdowns of how this system works in practice.

**Contributions welcome.** Found a way to improve a skill? [Open a PR](https://github.com/charlie947/social-media-skills/pulls). Run into a problem? [Open an issue](https://github.com/charlie947/social-media-skills/issues).

## What are Skills?

Skills are markdown files that give AI agents specialised knowledge and workflows for specific tasks. When you install these in your project, Claude recognises when you're work ing on a social media task and applies the right patterns, voice rules, and platform constraints.

## How Skills Work Together

Every skill reads shared context. The `voice-builder` skill is the foundation. Every other skill checks it first (via `about-me.md` and `voice.md`) before drafting a line.

```
                    ┌──────────────────────────────────────┐
                    │           voice-builder              │
                    │   about-me.md + voice.md             │
                    │   (read by every skill below)        │
                    └──────────────────┬───────────────────┘
                                       │
                    ┌──────────────────▼───────────────────┐
                    │         newsletter-voice             │
                    │   newsletter-voice.md                │
                    │   (the source every piece comes from)│
                    └──────────────────┬───────────────────┘
                                       │
           ┌────────────────────┴────────────────────┐
           ▼                                         ▼
     ┌──────────┐                            ┌──────────────┐
     │Instagram │                            │ Video        │
     ├──────────┤                            ├──────────────┤
     │instagram-│                            │reels-        │
     │ unskip   │                            │ scripting    │
     └──────────┘                            └──────────────┘
```

See each skill's `SKILL.md` for trigger phrases, inputs, and dependencies.

## Available Skills

<!-- SKILLS:START -->
| Skill | Description |
|---|---|
| [voice-builder](skills/voice-builder/) | Build `about-me.md` and `voice.md` from an interview plus 3 to 5 writing samples. The foundation every other skill reads. |
| [newsletter-voice](skills/newsletter-voice/) | Add newsletter-specific writing instructions on top of voice-builder. Produces `newsletter-voice.md`. |
| [reels-scripting](skills/reels-scripting/) | Reverse-engineer an outlier Reel via Apify + Gemini 2.5 Flash. Write a new script in your voice from your newsletter. |
| [instagram-unskip](skills/instagram-unskip/) | Engineer Reels, carousels, and statics against the signals Instagram actually ranks on — skip rate down, shares up. Self-contained: reach hierarchy, SUCCESs message design, and caption craft. |
| [solo-reel-shoot](skills/solo-reel-shoot/) | Turn a Reel script into a phone-shootable shot list — solo (tripod) or one friend filming, cheap mic, outdoor-lean. The production layer under instagram-unskip. |
| [saubhya](skills/saubhya/) | Create a Reel for @saubhya.np — loads her brand context and Nepali-English voice, scripts via instagram-unskip, then hands off to solo-reel-shoot for the shot list. Invoke with `/saubhya`. |
| [fandom-funnel](skills/fandom-funnel/) | The superfan / Fandom Funnel playbook (Kallaway). Optimize for content-minutes per person, not single-video virality — binge bank, connective tissue, the profile audit, and the 4 drivers + 7 shifts. The audience-over-time layer above instagram-unskip. |
| [hook-machine](skills/hook-machine/) | Data-driven hook engineering (Kallaway's "Hook Machine"). Don't generate hooks blind — mine your own scraped winners vs. losers, build a niche rubric, and critique drafts against it. Replaces Sandcastles.ai with the repo's own Apify pipeline (`saubhya-data/`). The hook pass under instagram-unskip. |
<!-- SKILLS:END -->

## Installation

### Option 1: Claude Code plugin marketplace

```bash
# Add the marketplace
/plugin marketplace add charlie947/social-media-skills

# Install the plugin
/plugin install social-media-skills
```

### Option 2: Clone and copy

```bash
git clone https://github.com/charlie947/social-media-skills.git
cp -r social-media-skills/skills/* ~/.claude/skills/
```

### Option 3: Individual skill upload (Claude Desktop)

Download any skill folder, zip it, and upload via Customise skills in Claude.

```bash
cd social-media-skills/skills
zip -r voice-builder.skill voice-builder
# Upload voice-builder.skill through Customise skills in the Claude app
```

### Option 4: Git submodule

```bash
git submodule add https://github.com/charlie947/social-media-skills.git .agents/social-media-skills
```

Then reference skills from `.agents/social-media-skills/skills/`.

### Option 5: Fork and customise

Fork the repo, swap the voice rules for your own, and clone your fork into your projects.

## Usage

Run `voice-builder` first. Every other skill needs `about-me.md` and `voice.md` to work properly.

Once installed, ask Claude to help with content tasks and it will pick the right skill:

```
"Build my voice" → voice-builder
"Set up my newsletter voice" → newsletter-voice
"Turn this outlier Reel into a script" → reels-scripting
"My reels aren't reaching, fix my Instagram" → instagram-unskip
"Make me an Instagram carousel" → instagram-unskip
```

## Skill Categories

### Voice foundation
- `voice-builder` — interview + sample analysis, writes about-me.md and voice.md
- `newsletter-voice` — newsletter-specific writing rules on top of voice-builder

### Instagram
- `reels-scripting` — Apify + Gemini 2.5 Flash reference analysis, newsletter-aligned script
- `instagram-unskip` — engineer Reels, carousels, and statics for reach (skip rate down, shares up)

## Prerequisites

A few skills need external services. Set these environment variables before use:

| Variable | Needed for |
|---|---|
| `APIFY_API_TOKEN` | reels-scripting |
| `GOOGLE_AI_API_KEY` | reels-scripting (Gemini 2.5 Flash video analysis) |

Set them with:

```bash
export APIFY_API_TOKEN=your_token
export GOOGLE_AI_API_KEY=your_key
```

## Contributing

PRs and issues welcome. See [CONTRIBUTING.md](CONTRIBUTING.md) for guidelines on adding or improving skills.

Run `./validate-skills.sh` before submitting to check your skill against the spec.

## License

[MIT](LICENSE). Use these however you like. If they help you, a link back to the [newsletter](https://charliehills.substack.com) is appreciated.

— Charlie
