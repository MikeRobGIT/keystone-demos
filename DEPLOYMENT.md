# Coolify deployment

- Repository: https://github.com/MikeRobGIT/keystone-demos
- Project: Keystone Demos (`gxk8xk16g9ymfvilrciychw8`)
- Environment: production
- Application: yogardener-demo (`gjs4gf6chgdvpxxyeyrzfryw`)
- Server: coolify-production, 5.161.196.69
- Dashboard: https://coolify.microcrisis.systems
- Public domain: https://yogardener.keystonecognition.com
- Dockerfile at repository root, nginx port 80, GET / health check.

DNS: a dedicated proxied A record points Yogardener at 5.161.196.69. The existing
wildcard points elsewhere and was preserved. Future demo names need dedicated
DNS records unless the user explicitly changes that wildcard.

Release process: commit through GitHub, POST /api/v1/deploy with the application
UUID, poll the returned deployment UUID, then verify public HTTPS and content. A
public-repository source is configured; automatic GitHub webhook deployments
have not been configured or verified. No credentials belong in this repository.

## The concept

This is a **redesign concept** for Yogardener, not a from-scratch build —
Yogardener already has a website (yogardener.com, plus go.yogardener.com).
`RESEARCH.md` in the repository root is the source of truth for every fact on
the page, the audit of the client's current site, and the asset provenance.

The page is a landscape architect's drawing sheet: the hero is a hand-drawn
site plan with a bottom title block and a twelve-month rail that re-tints the
plan by season. Self-hosted Anybody / Hanken Grotesk / Azeret Mono. No
external network requests beyond the footer links out to Yogardener's own
pages.

## Verified 2026-11-06

Release `1ada6fe` (site plan rebuild) deployed as `o0aryhyto1u5ipjrb0ydmvus`;
release `54db169` (fact-check corrections) deployed as `xjwcjddp9fsxouxzsujojnmp`.
Both finished; public HTTPS returned 200 with `x-robots-tag: noindex, nofollow`;
every asset path under `/assets/` returned 200; the month rail was driven on the
live page and re-tinted the plan and updated its note.

Content: 30 claims corrected against `RESEARCH.md` after a full fact-check —
the Nextdoor badge is five separate years and not consecutive, the Plymouth Road
caption and alt text now match the Morningside project, the service count is
twelve, the Atlanta Action Day roof was managed rather than donated, the summer
jobs programme carries its 2016 date and 16–24 age range, three unsupported
claims about who answers the phone were removed, the lime statistic was
narrowed to tested samples, sod was moved to the months the source supports,
two quotes were restored verbatim, Keystone's own tagline no longer claims the
client has no website, and the footer now attributes the Nextdoor badge as a
Nextdoor trademark.

Design quality: the impeccable detector reported 141 findings on the first
build and 6 on the current one (5 are false positives on the `.wrap` gutter;
1 is the deliberately tracked uppercase mono used for drawing annotations).
All contrast failures were cleared by darkening the ember action colour to
`#A8451F` and the secondary inks on paper to `#5A6A52`, and by lifting every
sub-11px label. The heading order was corrected — the year cells are now `h3`
under the section `h2`.

Responsive: checked at 320, 360, 390, 414, 600, 768, 900, 1024, 1100, 1280,
1440 and 1600px. No horizontal overflow at any width; the display headline holds
three lines at every width but 1100px. Under 760px the drawn sheet drops its
title block and an HTML facts strip carries the same information.

## Still open before a client production launch

Michael's email for the footer contact block. The exact Google review count on
the day of the call, to replace "60+". Written clearance from Yogardener for
its photography and logo, and separate clearance from Nextdoor for the award
badge. Confirmation of the licence string against the Georgia portal.
Confirmation of the service-area town list. Form delivery setup — the form is
deliberately inert and says so.
