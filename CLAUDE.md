# bc-connectordev

Notes for developers working on this plugin.

## What's here

- `README.md` owns the user-facing setup contract: `.env` keys and the `.claude/settings.json` allowlist entries.
- `skills/boomi-connectordev/` is the skill — SKILL.md, CLI scripts, and reference docs.
- The plugin is standalone-installable. When bc-integration is co-installed, the Platform credentials in `.env` are shared between the two.

## Architecture

The Connectors API lives at `{BOOMI_API_URL}/connector/api/rest/v1/{accountId}` — a different base path from the Platform API's `/api/rest/v1/{accountId}`. `scripts/connectordev-common.sh` owns the URL builder and request wrapper so that difference lives in one place.
