---
name: solo-reel-shoot
description: "Turn a Reel script or idea into something actually shootable by one person with a phone. Translates beats into a simple shot list constrained to two shoot modes — solo (phone on a tripod) or one friend filming — using only a budget phone and a cheap clip-on mic, leaning outdoors. Use whenever the user needs to film a Reel themselves, says 'how do I shoot this,' 'make it simple to film,' 'I shoot on my phone,' 'I film alone / with my friend,' 'outdoor shoot,' 'no fancy gear,' or wants a script's scenes redesigned to be filmable without a crew, gimbal, second phone, or studio. This is the production/shooting layer only — for the script, hooks, captions, on-screen text, and reach engineering, use instagram-unskip. Out of scope: paid ads, multi-cam shoots, professional lighting/grip setups, video editing/rendering."
---

# Solo Reel Shoot

> A perfect script that can't be filmed is worthless. This skill is the bridge between "here's the script" and "here's exactly what I point my phone at." It assumes one person, one budget phone, one cheap mic, and no crew.

This is the **production layer**. The creative — hooks, structure, on-screen text, captions, reach engineering — comes from `instagram-unskip` (or whatever produced the script). This skill only answers one question: **how does this actually get filmed by one person with a phone?**

## When to use this skill

- The user has a Reel script or idea and needs to film it themselves
- "How do I shoot this?", "make it simple to film", "I shoot on my phone"
- "I film alone" or "I film with one friend"
- "Outdoor shoot", "no fancy gear", "I don't have a gimbal/studio"
- A script's scenes need to be redesigned so they're filmable without a crew

**Do not use this skill for:** the script itself, hooks, captions, or on-screen text → `instagram-unskip`. Paid ads, multi-cam shoots, professional lighting/grip, or video editing/rendering → out of scope.

## The two shoot modes (the hard constraint)

Every shot must be filmable in one of exactly two modes. If a beat can't fit either, redesign the beat.

| Mode | Setup | Best for | Limits |
|------|-------|----------|--------|
| **Solo** | Phone on a tripod (or propped), creator steps into frame | Talking-to-camera, locked-off action, walking toward/away from a fixed phone | No camera movement during the take; framing is fixed before you hit record |
| **One friend** | A friend holds the phone and follows the creator | Walking-with shots, reveals, reaction cuts, handheld energy | Friend is untrained — keep moves slow and simple; no focus-pulling or complex choreography |

Default to **solo** unless a beat genuinely needs motion or a second angle. Solo is always available; a friend is a bonus, not a requirement.

## Gear baseline (assume nothing more)

- **One budget smartphone.** Shoot rear camera (better than selfie cam), 1080p/30 or 4K/30, locked focus and exposure on the subject before recording.
- **One cheap clip-on / lavalier mic.** Bad audio kills retention faster than bad video. Clip it ~a hand's width below the chin. No mic? Film within arm's reach in a quiet spot — never rely on phone audio from across a room.
- **Natural light, outdoor-lean.** Daylight is free and flattering. Face the light (sun behind the phone, not behind the subject). Shoot in open shade or golden hour to avoid harsh midday shadows. Indoors: face a window.
- **A tripod, or anything to prop the phone** — a wall, a ledge, a stack of books, a railing. "Tripod" means "phone held still."

No gimbal, no second phone, no lights, no reflectors, no boom. If a shot needs them, cut it.

## How to build the shot list

Take the script beat by beat. For each beat, output a shot card:

```
SHOT n — [beat name / the line or action]
Mode:      Solo (tripod)  |  One friend
Frame:     [shot size + angle, e.g. "waist-up, phone at chest height, slight angle"]
Location:  [where — outdoor/indoor, what's behind the subject]
Action:    [what the creator does in plain language]
Audio:     [spoken line, or "ambient only"]
On-screen: [text overlay for this beat, from the script]
Note:      [the one thing that makes or breaks this shot]
```

Rules for the shot list:

- **One location block at a time.** Group shots by location so the creator films everything in one spot before moving. Don't ping-pong.
- **Keep moves filmable by an untrained hand.** Slow pans, walk-with, simple reveals. No whip-pans, no rack focus, no orbiting.
- **Locked-off beats are the default.** Talking-head and most action work as solo tripod shots. Reserve "one friend" for beats that truly need movement.
- **Match shot size to content.** Close for emotion/intimacy and on-screen-text moments; wider for action, outfit, or showing a space.
- **Clean backgrounds.** Plain wall, greenery, or simple street beats a cluttered room. Mention it in `Location`.
- **Each shot is one continuous take.** No in-shot cuts. Multiple takes of the same shot are fine; editing joins them later.

## Output structure

1. **Shoot summary** — total shots, how many solo vs friend, locations needed, rough time to film, and the single gear must-have (usually: mic + something to prop the phone).
2. **The shot list** — shot cards in filming order (grouped by location, not script order, if that saves setups). Note where script order ≠ filming order.
3. **Shoot-day checklist** — battery, storage, lock focus/exposure, mic check, frame check, do a 5-second test recording before the real takes.

## What this skill does NOT do

- Write or rewrite the script, hooks, captions, or on-screen text → `instagram-unskip`
- Editing, transitions, music sync, captions burn-in, rendering → done later in CapCut / the user's editor
- Paid ads, multi-cam, professional lighting/grip, studio setups → out of scope

If the incoming script has a beat that simply cannot be shot solo-or-one-friend on a phone (e.g. a drone shot, a crowd scene, a moving-vehicle rig), flag it and propose a phone-able substitute that preserves the beat's intent.
