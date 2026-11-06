# Yogardener demo design

Scope: `clients/yogardener/index.html`. Mode: Persuade. Preserve the approved garden-journal direction.

## Visual system

- Warm ruled paper: #F7F3E8; deeper paper: #EFE9D8; plant tag: #FFFDF7.
- Graphite green ink: #2C3A2F; secondary ink: #4E5D50.
- Botanical red actions: #B4432E; hover: #93351F; small red text: #8F331F.
- Georgia serif body, 17px, line height 1.55; italic serif wordmark and promise.
- Desktop: two-page spread with fixed month tabs, journal left, identity and contact right.
- Below 880px: single column, identity and contact first, scrollable month tabs, two-column calendar.
- One authored entrance: the underline beneath the promise. Respect reduced motion.
- No raster assets or external font dependencies. Rules and tape are CSS; underline is an authored geometric SVG path.

## Preview boundaries

Visible independent-concept notice, illustrative content labels and noindex metadata/header. Real business telephone links and Michael's contact link work. The request form is intentionally disabled and explicitly states that it sends nothing. Owner approval, confirmed services and service area, Michael's email, and form delivery setup remain prerequisites for a client production launch.

## Finish review

Initial live desktop review found an illegible SVG wordmark: replaced with readable text and a semantic h1. Mobile review found contact below the journal: moved the contact page first. Set mobile month tabs not to shrink and fixed narrow wordmark sizing. Deployment and responsive verification are recorded in `DEPLOYMENT.md` after release checks.
