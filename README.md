# Mario The Roofer — Website (Design Reference)

Indigenous-owned residential roofing company in Saskatoon, SK. This bundle is the
**desktop homepage + full subpage set**, drafted as a clickable multi-page site.

> **These files are design references, not production code.** They are HTML/JS
> prototypes that show the intended look, copy, and behaviour. Recreate them in
> your target stack (React, Next, Astro, plain HTML — your call) using its own
> patterns, components, and responsive system. Don't ship these files as-is.

Fidelity: **High** — final colours, type, spacing, copy, and interactions are
intentional. Recreate them closely. Everything marked "(placeholder)" is content
the client still has to confirm (see "Placeholders" below).

---

## How to open

Each page is a `*.dc.html` file. Open `index.dc.html` in a browser; the nav,
footer, service sidebars, and primary CTAs are real links, so you can click
through the whole site. `support.js` is the small runtime that renders the
pages — keep it in the same folder. (You do not need to reproduce `support.js`
or the `.dc.html` format in your build — read the markup as a reference.)

## Pages & routes

| File | Suggested route | Purpose | Active nav |
|---|---|---|---|
| `index.dc.html` | `/` | Homepage | Home |
| `services.dc.html` | `/services` | Services overview (4 service rows) | Services |
| `shingle-installation.dc.html` | `/services/shingle-installation` | Service detail | Services |
| `roof-replacement.dc.html` | `/services/roof-replacement` | Service detail (insurance-claim angle) | Services |
| `roof-repairs.dc.html` | `/services/roof-repairs` | Service detail (fast-response / storm) | Services |
| `eavestrough.dc.html` | `/services/eavestrough` | Service detail (spring-melt) | Services |
| `band-tribal-council.dc.html` | `/band-tribal-council-services` | B2B page for band housing authorities & tribal councils | Band & Tribal Council |
| `about.dc.html` | `/about` | Founder story, values, crew, certifications | About |
| `gallery.dc.html` | `/gallery` | Filterable project gallery | Gallery |
| `contact.dc.html` | `/contact` | Contact info + quote-request form | Contact |

## Design system

**Typography**
- Display / headlines: **Anton** (Google Fonts), weight 400, used uppercase. Trades-signage credibility.
- Body / UI: **Source Sans 3** (Google Fonts), 400 / 600 / 700.
- Mono (placeholder labels only): system `ui-monospace`.

**Colour tokens**
| Token | Hex | Use |
|---|---|---|
| Charcoal (base dark) | `#1B1814` | Primary dark surfaces, headers, body text |
| Charcoal deep | `#14110E` | Top bar, footer, deepest surfaces |
| Bone | `#F4F0E7` | Light section background |
| Off-white | `#FBF9F4` | Page background / cards backdrop |
| Ochre (primary accent) | `#C8861F` | Primary CTAs, accents, motif |
| Ochre bright (hover) | `#DFA12E` | Hover state for ochre, nav highlight |
| Clay (secondary accent) | `#B3431F` | Secondary accent, "tânisi" eyebrow |
| Clay deep | `#9C3A1B` | Link text on light |
| Prairie-sky blue | `#46688A` | Quiet tertiary accent, location tags, motif top line |
| Card border | `#E2DCCE` / `#D8D2C4` | Hairline borders on light |
| Muted text | `#6E675C` / `#8A8378` | Secondary text |

Contrast meets WCAG AA on the combinations used.

**The one motif** — a three-rule "horizon line" (sky `#46688A` 100% width, ochre
`#C8861F` 66%, clay `#B3431F` 36%), used sparingly as a section marker. A second
restrained form is a small rotated square (diamond) at `#C8861F`/`#B3431F`. **Do
not** add feathers, dreamcatchers, medicine-wheel colour, or generic "tribal"
patterns — this is a deliberate hard constraint from the brand.

**Spacing / radius** — section padding `64px–88px` vertical, `64px` horizontal
(desktop). Cards `6–10px` radius. Buttons `4px` radius. Card shadow on hover:
`0 8–12px 20–28px rgba(27,24,20,0.08–0.12)`.

## Components & interactions

- **Header** (`#1B1814`): slim top bar (phone/email/territory), logo, nav, phone
  block, ochre "Get a Free Quote" CTA. Active nav item is ochre `#DFA12E`.
- **Hero**: full-bleed photo placeholder + dark scrim, Anton headline, dual CTA,
  and the circular **"Indigenous Owned & Operated" seal** (see `index` hero).
- **Trust bar**: Licensed · Bonded · Insured · CCAB (placeholder) · 10+ yrs · Google rating.
- **Service cards / rows**: hover lifts `translateY(-3px)` + ochre top/left border.
- **Shingle colour selector** (homepage + shingle page): click a swatch to select;
  selection shows an outline ring + bold name + a summary chip. 10 colours with names + lifespan.
- **FAQ accordion** (each service page): click a row to expand; one open at a time
  per page. State key per page: `shingle` / `replace` / `repair` / `eaves`.
- **Gallery** (`gallery`): filter chips (All / Replacement / Repair / Eavestrough /
  Band Housing) re-filter a CSS-columns masonry grid. Each card has a location tag.
- **Quote form** (`contact`): fields name*, phone*, email, address, service* (chip
  picker), message. Validation: name, phone, and service are required; inline error
  text appears under each. On valid submit, the form is replaced by a success panel.

## State (for the interactive bits)

- `selectedShingleIndex` (homepage/shingle selector)
- `openFaq` per service page (index of open item, or none)
- `galleryFilter` (one of the 5 categories)
- `quoteForm` { name, phone, email, address, service, message }, `formErrors`, `formSubmitted`

## Assets / imagery

All photography is **placeholder** (diagonal-striped boxes with a mono caption of
the intended shot, e.g. "crew on roofline, golden hour"). Replace with real photos:
crew on a roof against big prairie sky, Mario portrait, work trucks, hands/tools,
before/after roofs. The "Indigenous Owned & Operated" seal is drawn in SVG in the
markup (three finishes: on-dark/ochre, on-bone/clay, one-colour stamp) — it's
reusable for trucks, yard signs, and print. No icon fonts; the small roof/shingle
icons are inline SVG.

## Placeholders to confirm with the client

- Nation / community affiliation wording (brief says Cree-owned, may change)
- CCAB "Certified Indigenous Business" status + exact wording
- Real phone number (currently `(306) 555-0184`) and email
- Apprenticeship / training partnership (SIIT placeholder)
- Testimonial attributions (incl. the housing-authority quote)
- Stat figures (years, roofs installed, communities, units)

## Source

These pages were split out of a single working concept file,
`Mario The Roofer - Homepage Concepts.dc.html` (in the project root), which also
contains the two original art-direction explorations (Prairie Iron / Big Sky),
the mobile layouts, and the standalone badge studies — useful extra reference.
