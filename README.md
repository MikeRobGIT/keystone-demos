# Keystone Demos

Bespoke website concepts for local businesses, hosted through Coolify.

## Yogardener

- URL: https://yogardener.keystonecognition.com
- Content: `clients/yogardener/index.html`
- Build: repository-root `Dockerfile`, serving static HTML with nginx on port 80.
- Coolify: Keystone Demos / production / yogardener-demo.
- Release: push the content, then trigger deployment through Coolify and verify HTTPS.

These are independent sales concepts. Illustrative services and journal entries require business-owner approval. The request form is deliberately disabled and collects nothing. Michael's email is still pending. Demos carry noindex directives.

## Future demos

Keep each business under `clients/<site>/` with a separate Coolify application and domain `<site>.keystonecognition.com`. Give each application its own Dockerfile copying only that client's files. Never commit credentials.
