# Version History

A chronological record of every version, the change made, and the rationale.

## v1 — Three Direction Exploration
**Format:** Written concepts only, no code
**Outcome:** Three approaches presented (Archive / Stage / Manifesto)

## v2 — Service Hero
**Format:** Full HTML mockup
**Decisions:**
- Warm beige background (#FAFAF7)
- Serif Chinese typography (Noto Serif TC)
- Service-oriented hero with venue visit info
- Three service cards (tour / classes / rental)
- Manifesto section relegated to second screen
**Rejected because:** Too refined, too "brand website," too safe

## v3 — Initial Avant-Garde
**Format:** Full HTML, downloadable file
**Decisions:**
- Pure black background (#050505)
- IBM Plex Mono + Inter 200 only
- "FILE — 001/002/003/004" archival numbering
- Off-grid asymmetric typography
- Blood red (#8B0000) used sparingly
- Pulsing red dot indicator
**Status:** Close, but still aesthetic-performance, not yet conceptually integrated

## v4 — Spotlight Mask
**Format:** Full HTML
**Decisions:**
- CSS radial-gradient mask creating a "hole" at cursor position
- Single mask over entire viewport
- Hard binary visibility (in/out of hole)
**Status:** Mechanism introduced, but no concept of memory/residue

## v5 — Per-Element Opacity + Residue
**Format:** Full HTML
**Decisions:**
- Each `.lum` element has individual opacity computed per frame
- Distance-based smoothstep falloff
- CSS transition handles afterimage on exit (1.2s desktop)
- Spotlight contracts on stillness: 200px → 35px over 6.5s
- Concept alignment fully achieved
**Status:** Conceptually integrated for first time

## v6 — Detail Refinement
**Format:** Full HTML
**Decisions:**
- Removed cursor's outer spotlight indicator ring (no teaching)
- Removed italic emphasis on "跳舞." (equal weight across all headline lines)
- Added `.faded` class (opacity 0.3 floor, 0.55 ceiling) for "historical layer"
- Raised minimum spotlight radius from 35 to 60 (less punishing)
- Touch-and-hold mechanics with afterglow
**Status:** Refined

## v6.1 — Mobile Hardening
**Format:** Full HTML (current version)
**Decisions:**
- `-webkit-tap-highlight-color: transparent`
- `user-select: none` + `-webkit-touch-callout: none`
- `min-height: 100svh` with `100vh` fallback
- `safe-area-inset-*` for notch handling
- `forced-color-adjust: none` to prevent iOS Smart Invert from breaking dark theme
- `<meta name="color-scheme" content="dark">`
- 30 FPS throttle on coarse-pointer devices
**Status:** Mobile-ready, current

## v6.1 portfolio — De-identification
**Format:** Full HTML + repository
**Decisions:**
- Top disclosure banner (concept exploration / unofficial / not affiliated)
- All real names replaced with generic equivalents
- Specific contact details, addresses, legal article numbers genericized
- Updated meta tags for public deployment
- Updated outbound links to GitHub repo
- README rewritten as portfolio case study (not foundation proposal)
- LICENSE file (MIT for code, CC BY-NC-SA 4.0 for design)
**Status:** Ready for public portfolio deployment
