# In The Black Time, Dance

> **在全黑的時代,跳舞**
>
> A concept exploration on cultural heritage, modern dance, and the politics of preservation. An unofficial fan-made design tribute.

[**→ Live Demo**](https://YOUR-DEPLOY-URL.vercel.app) *(replace with your URL after deploy)*

![Status](https://img.shields.io/badge/status-concept_exploration-8B0000)
![Type](https://img.shields.io/badge/type-unofficial_tribute-1A1A1A)
![Year](https://img.shields.io/badge/year-2025-1A1A1A)

---

## ⚠️ Important Notice

This is an **unofficial concept exploration** and design study by Awack Studio. It is **not affiliated with, endorsed by, or commissioned by any real organization or foundation**. All names, contact details, and specific facts have been genericized. This work is published as a portfolio piece exploring the intersection of cultural heritage, modern dance history, and avant-garde interface design.

---

## Concept

> *In a time of total darkness, dance.*

This project is a meditation on what avant-garde **interface** could mean when the subject matter itself — modern dance during an era of political repression — was itself an act of avant-garde existence.

The premise: **The site does not perform itself for visitors.** Content is hidden in darkness by default. Visitors must actively move — with their cursor or finger — to illuminate fragments of text. When still, the spotlight contracts. When moved, it expands. Just as dance, in an era of political darkness, demanded continuous motion to remain visible.

## Design Decisions

### 1. Default state: pure black
Not "dark mode" — *darkness as historical context.* Background is `#000000`. Text is `#FFFFFF`. No softening.

### 2. Cursor as spotlight
Every text node has its own opacity computed each frame based on distance from cursor. Inside spotlight: fully visible. Outside: fades to black over 1.2 seconds (residue / afterimage).

### 3. Spotlight contraction on stillness
Stop moving for 2 seconds, and the spotlight slowly shrinks from 200px to 60px over 4.5 seconds. **Stillness = loss of visibility.** Motion is required for continued seeing.

### 4. The faded historical layer
One line in section 2 — "*數千次,在這裡發生的*" (*thousands of times, here happened*) — is marked with a `.faded` class. Its opacity ceiling is 0.55 even at maximum illumination; its floor is 0.3 even in total darkness. **It is never fully clear. It is never fully gone.** A visual metaphor for how some histories exist.

### 5. The blood color, used once
`#8B0000` appears in only three places:
- The pulsing dot at bottom-right (this place is still alive)
- Section 001 / 004 labels (the statement, and the ongoing fight)
- The word "古蹟" / "時代" (heritage, era) and the join link

It is the only non-monochrome color in the entire site.

### 6. Touch and hold (mobile)
On mobile, tap and hold to reveal. On release, the spotlight remains in place and fades over 2.5 seconds — like a visual aftertrace of a dance step.

### 7. Refusal of UX conventions
No nav bar. No hero image. No "Welcome" message. No tooltip explaining "move your cursor to explore." If the visitor doesn't move, they don't see. Discovery is the visitor's responsibility — which is the only honest position when the subject is *the responsibility of remembering.*

## Stack

- Pure HTML + CSS + vanilla JavaScript (no frameworks, no build step)
- Single file (`index.html`), ~16 KB
- External: only Google Fonts CDN (IBM Plex Mono, Inter, Noto Sans TC)
- ~60 FPS desktop, throttled to 30 FPS on coarse-pointer devices for battery savings
- Mobile-safe: `100svh`, safe-area-insets, no tap highlight, forced color preservation

## Files

```
.
├── index.html       Production-ready demo
├── README.md        This file
├── LICENSE          MIT for code, CC BY-NC-SA 4.0 for design
└── docs/
    ├── design-notes.md       Full design rationale
    └── version-history.md    v1 → v6.1 evolution
```

## Run Locally

```bash
# Just open the file
open index.html

# Or serve it (required for some font/SEO testing)
npx serve .
# or
python3 -m http.server 8000
```

No build, no dependencies.

## Deploy

### Vercel (recommended)
```bash
npm i -g vercel
vercel
```

### GitHub Pages
1. Push to `main`
2. Settings → Pages → Source: `main` branch, root
3. Wait ~1 minute

### Netlify
Drag and drop `index.html` into Netlify's deploy dashboard.

## Why This Design

The site that inspired this exploration covers a real foundation working on real cultural heritage preservation — but its current digital presence is a Google Sites default template with 40+ sidebar items and no narrative hierarchy. The disconnect between the **weight of what they do** and **how the website carries it** raised the question: *what does it mean to design an interface that takes its subject as seriously as its subject takes itself?*

The answer in this exploration: by refusing the conventions of the contemporary cultural-institution website. By being closer to a piece of installation art than to a CMS landing page. By making the visitor *do something* — even something small, like moving the cursor — to participate in the work.

Whether this is the *correct* answer for a real foundation is another question. This exploration is the maximalist version. A live deployment for an actual organization would need to compromise toward operational realities (donations, rentals, accessibility for non-design-literate visitors). Those compromises are valid design work — but they are not what this exploration is about.

## Trade-offs (Honest Disclosure)

This design is **not appropriate as the primary website** for an active cultural foundation. It would:

- Lose visitors looking for venue rental info, class schedules, or donation forms
- Hurt SEO engagement metrics (high bounce rate, possibly long dwell time but unclear conversion)
- Confuse older visitors who may think the website is broken
- Need an accompanying `prefers-reduced-motion` static fallback for accessibility

It is best understood as **what a campaign landing page or an art-residency announcement site could look like** when the subject demands a non-commercial register.

## Process Documentation

The full design process, version-by-version reasoning, and the conversation that produced this work is documented in `docs/design-notes.md`. It includes deliberate dead ends, rejected approaches, and the criteria for each iteration.

## Inspiration / References

- Maurizio Cattelan — using physical space against itself
- Robert Wilson — silence and minimal illumination in theater
- Hito Steyerl — early documentary aesthetics
- Acne Studios / Berlin gallery websites — file-archive interface language
- Modern dance pioneers operating under political repression — the historical thread

The historical framing draws on the broader pattern of modern dance history under authoritarian regimes — a subject worth its own dedicated research, well beyond the scope of this design exploration.

## License

- **Code** (HTML/CSS/JS) — MIT License
- **Design concept and written content** — Creative Commons BY-NC-SA 4.0
  - Attribution required
  - Non-commercial use only
  - Share-alike for derivative works

You may fork, modify, and learn from this code freely. If you adapt the design concept itself for your own work, please credit Awack Studio and link back.

## Author

**Awack Studio**
Independent design and game development practice based in Taiwan.

Currently working on *BÔ BÂNG* — a third-person narrative adventure game exploring Taiwan's history through interactive storytelling. This concept exploration shares a lineage with that work: both ask how form can carry historical weight without flattening it.

- Web: [awackstudio.com](https://awackstudio.com)
- GitHub: [@your-username](https://github.com/your-username)

---

*This concept exploration is dedicated to all those who continued to move when stillness was demanded.*
