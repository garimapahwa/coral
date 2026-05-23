# PostHog Source (core)

This is the canonical `posthog` source shipped in `sources/core`.

## Notes

- Authentication: `POSTHOG_API_KEY` is required and must be a valid bearer token.
- Region/self-hosting: set `POSTHOG_API_BASE` to match your deployment:
  - US Cloud: `https://us.posthog.com`
  - EU Cloud: `https://eu.posthog.com`
  - Self-hosted: your own base URL
- Scope: use read-only scopes for the resources you plan to query.

## Quick usage

- List organizations

  SELECT id, name FROM posthog.organizations LIMIT 20

- List projects

  SELECT id, name, organization_id FROM posthog.projects LIMIT 50

- Query actions in a project

  SELECT id, name, event, created_at
  FROM posthog.actions
  WHERE project_id = 'your-project-id'
  LIMIT 100

## Inputs

- `POSTHOG_API_KEY` (secret, required)
- `POSTHOG_API_BASE` (variable, default `https://us.posthog.com`)

## Docs

- PostHog API reference: https://posthog.com/docs/api
