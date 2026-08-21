# Installation

Use the file matching the host platform:

`codex`, `cursor`, `opencode`, `workbuddy`, `qoderwork-cn`, `taer`, `trae-work-cn`, `claude-code`, `deepseek-harness`, `zcode`, `kimi`, `hermes`, or `openclaw`.

The generic `skills/ai-xtcg.skill` package is available for hosts without a dedicated adapter. Node.js 18+ is required. After import, run `node scripts/poster-client.mjs help` as a smoke test. An unbound account may return `SKILL_AUTH_REQUIRED`; start binding only through the supported official flow.

Never embed passwords, access tokens, refresh tokens, provider routing details, or locally calculated prices. Obtain quotes and generation confirmation from the official service.

