# Design Notes — In The Black Time, Dance

> Full process documentation. Read this if you want to understand *why* the design ended where it did.

## Context

This concept exploration began as a redesign brief for an existing cultural foundation website that suffered from two failures:

**Structural failure**
- 40+ first-level sidebar items with no hierarchy
- Homepage was a flat chronological news feed
- Bilingual labels concatenated without proper language switching
- No clear focal point or call-to-action

**Narrative failure**
- The foundation works on culturally and politically significant heritage preservation
- But the website read like any other small cultural institution
- The weight of what they do was completely flat on the page

The question this exploration tries to answer: **what would it look like to design an interface that takes its subject as seriously as its subject takes itself?**

## Iteration Log

### v1 — Three Direction Exploration

Three written-only concepts were proposed:

- **A. Archive** — Restraint, scholarly, archival numbering, dated metadata
- **B. Stage** — Dark background, performance imagery, theatrical
- **C. Manifesto** — White background, bold serif, blood red, political

The reviewer chose **C** but selected a "service-oriented hero" — a contradictory choice that led to v2.

### v2 — Service Hero + Refined Aesthetic

A compromise version: warm beige background, serif Chinese type, red as accent on political content only, mostly conventional layout with refined typography.

**Verdict from reviewer:** Too safe. Too "brand-website-y." No edge. Looks like every other Taiwanese cultural foundation that has hired a competent designer.

**The lesson:** Refinement is not avant-garde. A good serif and good kerning don't make a manifesto. The version was thrown out.

### v3 — In The Black Time

The first attempt at a genuinely uncompromised version:

- Pure black background
- Monospace (IBM Plex Mono) + Inter 200 only
- "FILE — 001 / 002 / 003 / 004" archival numbering
- Off-grid typography, deliberate asymmetry
- Blood red used three times, total
- A pulsing red dot indicating "this place is still alive"
- No nav bar, no logo, no hero image

**Verdict:** Close, but the "FILE" archival numbering and the italic emphasis on certain words still felt like designer aesthetics performing themselves. Not yet avant-garde — still avant-garde-style.

### v4 — Spotlight Mask

First version of the cursor-as-spotlight mechanic. Implementation used a single CSS radial-gradient mask over the entire viewport. Everything inside the mask hole was visible; everything outside was black.

**Limitation:** Hard edges. Binary visibility. No sense of residue or memory.

### v5 — Per-Element Opacity + Residue

Rewrote the spotlight system. Instead of a single mask:

- Every text node has an independent opacity, computed each frame based on distance from cursor
- Smooth falloff with smoothstep easing
- CSS `transition: opacity 1.2s cubic-bezier(0.33, 0, 0.4, 1)` handles the residue/afterimage on the exit side
- Spotlight contracts when cursor is still: from 200px (active) to 35px (after 6.5 seconds of stillness)

**Concept alignment:**
- Darkness = the political era of repression
- Spotlight = the visitor's attention as searching light
- Residue = memory's slow decay
- Contraction = stillness equals loss

This was the first version where every mechanic had a concept correspondence, not just a visual one.

### v6 — Detail Refinement

Five micro-decisions:
1. Removed the cursor's outer ring (no more visual indicator of spotlight size — let users discover the contraction on their own)
2. Removed the italic on "dance." — equal weight across all three lines of the headline
3. Implemented `.faded` class for the historical layer that never fully clears
4. Raised minimum spotlight radius from 35 to 60 — still small, but readable
5. Touch-and-hold semantics on mobile with proper afterglow

### v6.1 — Mobile Hardening

Real-device mobile fixes:
- `-webkit-tap-highlight-color: transparent` to remove the blue flash on link tap
- `user-select: none` to prevent long-press text selection
- `min-height: 100svh` for iOS Safari viewport correctness
- `safe-area-inset-*` for notch handling
- `forced-color-adjust: none` to prevent iOS Smart Invert from breaking the dark theme
- `<meta name="color-scheme" content="dark">` for OS-level intent
- 30 FPS throttle on coarse-pointer devices for battery savings

This is the current version.

## Rejected Approaches

### Approach: Brutalist typography
Considered making the headlines enormous (200px+), red, slanted, broken. Rejected because that aesthetic has been completely co-opted by fashion brands (Vetements, Off-White, Balenciaga). It is the visual language of *commercial avant-garde* — the opposite of what this project explores.

### Approach: Sound design
Considered adding subtle ambient audio (wood floor footsteps, post-fire wind, rehearsal breathing). Rejected because executed poorly, ambient sound becomes cheap atmosphere. Executed well, it requires a sound designer with archival access. Out of scope for a single-designer exploration. Reserved as a possible future addition.

### Approach: Character-level animation
Considered making each Chinese character or English letter individually computed for opacity. Tested briefly. Performance was acceptable but the visual effect felt fragmented in a way that pulled focus *to* the technique rather than *to* the content. Rejected.

### Approach: "Footprint" trails
Considered leaving faint gray traces along the cursor's path, slowly fading — making the visitor's movement literally dance trails. Tested. Rejected because it crossed into "interactive art" territory — clever, but pulling concept away from the subject and toward the designer's cleverness.

### Approach: Total content removal
Considered making the site contain only 20 lines of text spread across 8 full-screen black panels with no navigation. Rejected because it would damage the operational reality of any real foundation that might adopt this language. The avant-garde response to subject seriousness should not be the same as the avant-garde response to silence.

## What Could Still Be Pushed

If this concept were to be developed further as a deployable site, these are the next layers:

1. **Reduced-motion fallback** — A `prefers-reduced-motion` static high-contrast version that preserves the political stance while removing the interaction barrier for accessibility-impaired visitors.

2. **A genuine "complete archive" sub-site** — One that *breaks* this exploration's interface and provides full, fast, conventional reading. The exploration as currently designed cannot be the only entry point. There must be a way to read everything plainly. The transition from concept-site to archive-site is its own design problem.

3. **Live recording behavior** — The "RECORDING · [date]" indicator could be hooked to actual content events (a press release issued, a public hearing scheduled, a community signature added). The site would *be* the archive of an ongoing struggle, not just a snapshot.

4. **Versioning across time** — As the political situation referenced in section 004 changes (the petition succeeds, fails, evolves), the site could maintain visible historical states. Visitors today see "ONGOING." Visitors in 2030 see "RESOLVED 2027" or "STILL ONGOING." The site becomes its own historical record.

## Working Principles That Emerged

Through the six iterations, several principles solidified:

1. **Refinement is not avant-garde.** Good typography and tasteful restraint can produce excellent commercial design but cannot produce a genuine political statement.

2. **Concept must drive every mechanic.** If an interaction is only "cool," it dilutes the work. Every animation, every transition, every color must correspond to something in the subject.

3. **The designer's job is to refuse cleverness.** When the concept gets clever, it pulls focus away from the subject and toward the designer. The discipline is to stop one step before that point.

4. **Operational reality matters but cannot be the only criterion.** A foundation needs donations and venue rentals. A site that abandons those entirely is failing its host. But a site that *only* serves those completely flattens the subject. The art is in the negotiation — which is why this exploration documents the trade-offs honestly rather than pretending they don't exist.

5. **Silence is louder than noise.** The blood red is one color used three times. The headlines are not large. The spotlight is small. Restraint amplifies the few elements that do appear.

## Acknowledgments

This exploration was developed in dialogue with an AI assistant (Claude) as a thinking partner — proposing rejections, identifying weaknesses, articulating the difference between aesthetic-refinement and concept-refinement. The final design decisions, the rejections of safe versions, the push to ever-more-extreme variants, were made by a human designer.

The historical subject — modern dance under political repression — is real, and the people who lived it are real. This exploration is dedicated to them, without claiming to represent them.
