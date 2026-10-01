# firecrawl.izdrail.com

Self-hosted Firecrawl on predator (Coolify), internal only. No public domain, no published ports.

- Upstream images: ghcr.io/firecrawl/firecrawl, playwright-service, nuq-postgres (Firecrawl API has no built-in API key auth in self-host mode, USE_DB_AUTHENTICATION=false).
- `gate` (nginx) is the only service on the shared `coolify` network, alias `firecrawl-api`, and requires `Authorization: Bearer $FIRECRAWL_PROXY_KEY`.
- Internal URL for other Coolify apps: `http://firecrawl-api:3002` (the app container must be on the `coolify` network).
- Secrets (FIRECRAWL_PROXY_KEY, POSTGRES_PASSWORD) live in the Coolify application env, never in git.
