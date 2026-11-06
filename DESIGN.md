# Yogardener demo — design system

Scope: `clients/yogardener/index.html`. Mode: Persuade. World: **the landscape
architect's drawing sheet**. This file replaces the earlier garden-journal
world; that world belonged to a business model that turned out to be wrong (the
client already has a website) and did not match a design-build landscape
practice.

## Visual system

**Grounds.** Three surfaces, alternating by section so the page reads as a set
of drawings on a table rather than as one long scroll.

| Token | Value | Use |
|---|---|---|
| `--canopy` | `#0E1611` | Deep ground. Carries the hero, the work gallery, the founder and community section. |
| `--canopy-2` / `--canopy-3` / `--canopy-4` | `#16211A` / `#1E2C21` / `#2A3A2C` | Raised ground for figures and rules. |
| `--vellum` | `#F3ECDD` | Drafting paper. The sheet, the scope list, the reviews, the year, the close. |
| `--vellum-2` / `--vellum-3` | `#E7DCC5` / `#DCCFB3` | Deeper paper for the month rail and title block cells. |
| `--ink` / `--ink-2` | `#16211B` / `#415246` | Graphite-green ink on paper. |

**Ink and rules.** `--rule-dark` is `rgba(243,236,221,.15)` on dark grounds,
`--rule-light` is `rgba(22,33,27,.20)` on paper. Rules are hairlines. Section
dividers are 1.5px solid ink so they read as drawn lines, not as borders.

**Action colour.** `--ember` `#C0552C` — Atlanta brick. Reserved for the
primary call button, the active month, the month headings and the values
diamonds. `--ember-deep` `#9A3E1D` is the button's bottom edge only.
`--sage` `#8C9A5C` is the olive of Yogardener's own logo, used for the values
markers, the plan's proposed planting and the founder's role line. There is no
second accent and no gradient anywhere on the page.

**Type.**
- Display: **Anybody** (self-hosted, variable 400–900). Headlines, project
  names, the call button, the title block's project and contact lines. Tight
  tracking (-0.02 to -0.03em), display sizes capped at 72px.
- Body: **Hanken Grotesk** (self-hosted, variable 300–800). 17px, line-height
  1.62, measure 46–66ch.
- Annotation: **Azeret Mono** (self-hosted). Used only where a drawing
  actually carries measurement, dates, zone keys, source citations and
  metadata — plan labels, the title block, the month rail, the year cells,
  the source note, the footer provenance. Never as decoration.

**Geometry.** 2–3px radii throughout; a drafting sheet has square corners.
Shadows only on the sheet itself (`--sheet-shadow`), which is a sheet lying on
a dark table. No shadow anywhere else. Borders, not shadows, separate rows.

## The sheet

The hero's right column is a single drawn SVG, viewBox `0 0 960 660`, on a
vellum panel rotated -0.35°.

- **Plan area** (y 0–510): property line in dashed ochre, an irregular planting
  envelope in a 38° hatch, three contour paths at 2' intervals with elevation
  tags, the existing house with a roof line, four canopy outlines (irregular
  lobed paths, never circles) with a stipple fill, a dashed drive, a 6% slope
  arrow, a dashed French-drain path with a flow arrowhead, a permaculture
  "Zone 0" ellipse, three proposed elements (native bed, rain garden,
  flagstone patio with a stone hatch), a north arrow, a scale bar, and two keyed
  photo plates on the right.
- **Photo plates** are SVG `<image>` elements clipped to a rect, with a 1.4px
  ink border and a mono caption — photographs keyed into the drawing, not
  collage. Plate 2 sits rotated -1.4°.
- **Title block** (y 510–660): five cells on a hairline frame — Project, Drawn
  by, Scale, Contact, Next step — with mono labels at 11px and values at
  15–17px. Every string is sized to fit its cell; nothing overflows.
- **Month rail**: twelve buttons beneath the sheet in a mono face, `aria-pressed`
  on the active month, ember underline. Selecting a month re-tints the plan's
  planting fill to that season's colour and prints that month's task into the
  note line under the rail. The seasons are winter-dormant, spring green-up,
  summer, autumn.

On a viewport under 760px the SVG's viewBox is switched to `0 0 960 512` so the
drawing fills the width and the unreadable title block drops out; an HTML
facts strip (Drawn by / Scale / Contact / Next step) carries the same
information below it.

## Section rhythm

Alternating grounds give the scroll its pace: dark hero → dark land → paper
scope → dark work → paper reviews → dark people → paper year → paper close →
dark footer.

- **Hero** — two columns, 0.82fr / 1.18fr. Left: the headline, one paragraph,
  the call button, the consultation button, five proof chips. Right: the sheet.
- **Atlanta is hard on yards** — a drawn soil cross-section (SVG) beside four
  sourced facts, each with its citation in mono.
- **Scope of work** — a two-column grid: three delivery tracks as ruled line
  items on the left, the four-step process and the response promise on the
  right. The right column is sticky above 980px.
- **Work** — a 12-column asymmetric grid (5/4, 1/1, 4/5, 1/1, 4/5), captions
  over a bottom gradient.
- **Reviews** — a rating and badge rail beside twelve quoted notes in two
  masonry columns.
- **A practice, and the ground it works** — Everarde Calk and the values triad
  on the left; the community work and four photographs on the right.
- **The Atlanta year** — a 4/3/2/1-column grid of twelve month cells, each with
  a mono month, a display headline, a short paragraph and its source.
- **Start with a walk through** — a six-cell title block, a full-width ink
  band with the phone number, and the request form.

## Craft rules for this world

- No icon set. Marks are drawn: the call phone is an inline SVG stroke, the
  scope markers are rotated squares, the values markers are diamonds, the
  plan's north arrow and scale bar are geometry.
- No number service. The process steps are numbered 01–04 in mono because the
  sequence is the information; nothing else is numbered.
- No equal card grid anywhere. Reviews are masonry, the year is a table, the
  scope is ruled line items, the gallery is deliberately irregular.
- The mono face never decorates prose.
- `prefers-reduced-motion` disables the scroll reveal and the contour draw-on
  entirely, and the reveal has a no-JavaScript fallback so nothing can be
  stranded at opacity 0.

## Preview boundaries

The page states in a bar at the top that it is a Keystone Cognition Labs
concept and not Yogardener's live site, and repeats the point in the footer
with full provenance. The request form is deliberately inert and says so.
Photography, the logo and the Nextdoor badge are Yogardener's own assets and
are to be cleared before any public use; the badge is a Nextdoor trademark and
is cleared separately. No Google Business Profile or Yelp photographs are used.

Owner approval, confirmed service area, the exact Google review count on the
day of the call, confirmation of the licence string, Michael's email for the
footer, and form delivery remain prerequisites for a client production launch.
