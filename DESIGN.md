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

The hero's right column became the page. After the first review round the
sheet was measured at 660px wide for a 960-unit viewBox — a scale of 0.688,
which put every annotation on the page at 7.6 CSS px. The sheet now spans the
full content width (≈1180px), so the drawing renders at 1.23 and its
annotations at 15px. The promise sits in a band above it; the drawing is the
page.

- **Plan area** (y 0–560 of a 960×700 viewBox): property line in dashed ochre,
  an irregular planting envelope in a 38° hatch whose colour is driven by a
  CSS variable, four contour lines at a 2' interval falling 988 → 976 to the
  south in a warm sepia that clears 3:1 on vellum, the existing house with a
  full roof, a front door, a patio door, a stoop and a path, three scalloped
  canopy symbols, a 6% slope arrow, a dashed French drain with a flow
  arrowhead, a permaculture "Zone 0" ellipse, three proposed elements drawn
  with their own convention (dashed outline and a distinct hatch: native bed,
  rain garden, flagstone patio), a north arrow, and a drive.
- **The existing/proposed convention is real.** Existing canopy is a solid
  scalloped outline; proposed planting is dashed with a 45° bed hatch. An
  earlier version drew the proposed bed in the same cloud shape as a tree,
  which destroyed the one convention a plan cannot lose.
- **Sidebar** (x 690–942): two keyed reference photographs side by side with
  mono captions, a six-row key, and four drawing notes.
- **Title block** (y 560–700): five cells on a hairline frame — Project,
  Drawn by, Drawing, Contact, Next step — with mono labels at 12px and values
  at 14–18px. Every string is measured against its cell with the mono's real
  0.61em advance; nothing overflows the viewBox.
- **The scale claim is honest.** The sheet is fluid, so 1 SVG unit is not a
  fixed distance. The cell reads "Sheet 01 of 01 / Scale — not to scale"
  rather than printing a scale bar that would be a lie at every width but
  one.
- **Month rail**: twelve buttons beneath the sheet in a mono face,
  `aria-pressed` on the active month, ember underline. Selecting a month
  re-tints the plan's planting fill to that season's colour and prints the
  month's task and its source into the note under the rail. Seasons are
  winter-dormant, spring green-up, summer, autumn, and March is green-up.
- **On a viewport under 760px** the SVG's viewBox is switched to the plan
  area alone, the title block drops out and an HTML facts strip carries the
  same information, and the sheet pans horizontally with a hint. A technical
  drawing at 350px wide is illegible; a drawing you can pan is legible.

## Section rhythm

Alternating grounds give the scroll its pace: dark hero → dark land → paper
scope → dark work → paper reviews → dark people → paper year → paper close →
dark footer.

- **Hero** — a promise band above the sheet. The band is 1.28fr / 0.72fr: the
  headline, one paragraph, the call button and the consultation button on the
  left; a residential photograph and a ruled proof record on the right — Google
  rating, Nextdoor favourite, licence and hours as a definition list with
  hairline rules, not a wall of bordered chips. Then the sheet, full width.
- **Atlanta is hard on yards** — Section A-A, a drawn soil cross-section on
  its own vellum sheet with its own title block, beside four sourced facts each
  with its citation in mono. The section uses the plan's canopy symbol, its
  swale sits at grade rather than buried in the clay, and it is a sheet like
  the hero's, not a diagram in a dark card.
- **Scope of work** — a two-column grid: three delivery tracks as ruled line
  items on the left, the four-step process and the response promise on the
  right. The right column is sticky above 980px.
- **Work** — a 12-column asymmetric grid (5/4, 1/1, 4/5, 1/1, 4/5), captions
  over a bottom gradient.
- **Reviews** — a title strip first (rating and review count on the left,
  Google's own highlighted lines in the middle, the Nextdoor award badge on the
  right), then the twelve quoted notes in three masonry columns below it.
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
- No eyebrow kicker above a heading. The three delivery tracks are named by
  their headings and ordered by position; "How a project runs" is a heading.
- No equal card grid anywhere. Reviews are masonry, the year is a table, the
  scope is ruled line items, the gallery is deliberately irregular.
- The mono face never decorates prose.
- The action colour means one thing: the call. The concept notice is set on
  the dark ground, not in the accent; the review stars use a tint of it, not
  the accent itself.
- Buttons are flat fills with a keyline, not embossed slabs.
- `prefers-reduced-motion` disables the scroll reveal and the contour draw-on
  entirely, and the reveal has a no-JavaScript fallback so nothing can be
  stranded at opacity 0.
- The reveal fades only. Nothing drifts onto a sheet.

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
