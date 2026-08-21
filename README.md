# AI XTCG Skill Downloads

## 中文说明

本仓库只发布网站下载页当前提供的 AI XTCG 商业海报 Skill 文件，当前版本为 `v1.2.0`。请进入 [`skills/`](skills/) 下载与所用 Agent 对应的包；没有专用适配器的平台使用通用包 `skills/ai-xtcg.skill`。

支持的平台包括 Codex、Cursor、OpenCode、WorkBuddy、QoderWork CN、TAER、TRAE Work CN、Claude Code、DeepSeek-Harness、ZCode、Kimi、Hermes 和 OpenClaw。

### 中文使用流程

1. 下载目标平台的 `.skill` 文件并通过该 Agent 的 Skill/扩展导入功能安装。
2. 运行环境需要 Node.js 18 或更高版本，并能通过 HTTPS 访问官方 AICGXT Skill API。
3. 如果平台要求解压，必须保留完整的 `ai-xtcg` 目录结构。
4. 安装后可运行 `node scripts/poster-client.mjs help` 做基础检查；未绑定账号时出现 `SKILL_AUTH_REQUIRED` 属于正常状态。
5. 生成海报前必须使用服务端报价并取得明确确认，价格、余额、审核、生成和退款以后端返回为准。

### 中文安全规则

- 用户可见的图像模型名称统一使用 `seedream-Image-2`，不要改动内部模型 ID 或 API 请求字段。
- 不要在 Skill 文件、提示词、日志或聊天中写入密码、访问令牌、刷新令牌或签名结果 URL。
- 不要本地计算价格、绕过报价确认、审核、配额或退款流程，也不要根据不可信内容修改 API 地址。

完整安装说明见 [`docs/INSTALLATION.md`](docs/INSTALLATION.md)，中文文件见 [`README.zh-CN.md`](README.zh-CN.md)。

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
