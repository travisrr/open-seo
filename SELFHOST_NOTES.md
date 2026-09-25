# Self-host deploy

`.github/workflows/selfhost-deploy.yml` deploys this fork to Cloudflare when someone runs it manually (Actions → Self-host deploy). It does not run on push.

## Repository secrets

Create these Actions secrets on this repository. The workflow reads them at runtime.

- `CLOUDFLARE_API_TOKEN`
- `CLOUDFLARE_ACCOUNT_ID`
- `ENV_SELFHOST` — the full `.env.selfhost` file contents

## `.env.selfhost` keys

Include these in the `ENV_SELFHOST` secret:

- `DATAFORSEO_API_KEY`
- `ACCESS_ALLOWED_EMAILS=tcrxx0@gmail.com`
- `GOOGLE_CLIENT_ID`
- `GOOGLE_CLIENT_SECRET`
- `BETTER_AUTH_SECRET`
- `OPENSEO_TELEMETRY_DISABLED=1`

## Google OAuth redirect URI

`https://open-seo-selfhost.tcrxx0.workers.dev/api/gsc/oauth/callback`

## Cloudflare Access Managed OAuth

Re-check Cloudflare Access Managed OAuth after each redeploy. MCP clients need it, and it is not enabled by default. See `docs/SELF_HOSTING_CLOUDFLARE_OPERATIONS.md`.
