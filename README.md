# AI XTCG Skill Downloads

This repository contains the exact Skill files currently published by the website at `frontend/public/downloads/skills`.

The current release is `v1.2.0`: 13 platform packages, the generic `ai-xtcg.skill`, `manifest.json`, and the generic SHA-256 file. Choose the package matching your agent platform from [`skills/`](skills/).

## Installation

Import the matching `.skill` file through your agent's Skill/extension workflow. The package requires Node.js 18 or newer and HTTPS access to the official AICGXT Skill API. Keep the complete `ai-xtcg` directory together if the host asks for an unpacked directory.

For package-specific notes, see [`docs/INSTALLATION.md`](docs/INSTALLATION.md). Verify the generic package with:

```powershell
$expected = (Get-Content skills/ai-xtcg.skill.sha256).Split()[0]
$actual = (Get-FileHash skills/ai-xtcg.skill -Algorithm SHA256).Hash.ToLowerInvariant()
if ($expected -ne $actual) { throw "SHA-256 mismatch" }
```

The server remains the source of truth for account binding, prompt templates, pricing, balance, moderation, generation, and refunds. Never put credentials in Skill files. User-facing image-model text must use `seedream-Image-2`; internal IDs and API payloads remain unchanged.

