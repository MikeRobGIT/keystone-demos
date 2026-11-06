# Coolify deployment

- Repository: https://github.com/MikeRobGIT/keystone-demos
- Project: Keystone Demos (`gxk8xk16g9ymfvilrciychw8`)
- Environment: production
- Application: yogardener-demo (`gjs4gf6chgdvpxxyeyrzfryw`)
- Server: coolify-production, 5.161.196.69
- Dashboard: https://coolify.microcrisis.systems
- Public domain: https://yogardener.keystonecognition.com
- Dockerfile at repository root, nginx port 80, GET / health check.

DNS: a dedicated proxied A record points Yogardener at 5.161.196.69. The existing wildcard points elsewhere and was preserved. Future demo names need dedicated DNS records unless the user explicitly changes that wildcard.

Release process: commit through GitHub, POST /api/v1/deploy with the application UUID, poll the returned deployment UUID, then verify public HTTPS and content. A public-repository source is configured; automatic GitHub webhook deployments have not been configured or verified. No credentials belong in this repository.

## Verified 2026-11-06

Content release `3e293fafc13b7005bea302fbe395d94bbbec4ac6`; deployment `16mqpossq5q5cobdwufahrth` finished. Public HTTPS returned 200 with noindex header. Rendered desktop at 1440px and mobile at 375px; no document overflow at 320, 375, 1200 or 1440px. At 375px the primary call begins around 421px, within the first screen. Reduced-motion mode and month anchor navigation checked at 320px. Telephone targets match client and Michael numbers; no call initiated. Form remains disabled and clearly marked. No new browser errors after the DNS correction.

Verdict: ready to share as an independent demo; client production launch remains pending confirmed content, owner approval, and form delivery setup. Michael contact email is not supplied.
