# AI XTCG Skill 下载文件

本仓库只包含网站 `frontend/public/downloads/skills` 当前实际发布的 Skill 文件。

当前版本为 `v1.2.0`：13 个平台包、通用包 `ai-xtcg.skill`、`manifest.json` 和通用包 SHA-256 校验文件。请在 [`skills/`](skills/) 中选择对应平台的 `.skill` 文件。

支持的平台：Codex、Cursor、OpenCode、WorkBuddy、QoderWork CN、TAER、TRAE Work CN、Claude Code、DeepSeek-Harness、ZCode、Kimi、Hermes、OpenClaw。

## 使用说明

通过目标 Agent 的 Skill/扩展导入流程导入对应 `.skill` 文件。运行环境需要 Node.js 18 或更高版本，并能通过 HTTPS 访问官方 AICGXT Skill API。如果平台要求解压目录，请保持完整的 `ai-xtcg` 目录结构。

安装后可以运行 `node scripts/poster-client.mjs help` 做基础检查。首次使用时，按 Skill 提示通过官方流程绑定账号；未绑定账号返回 `SKILL_AUTH_REQUIRED` 是正常状态。正式生成前，先提交 Brief 获取服务端报价，向用户展示应付点数和余额并取得明确确认，再使用同一报价提交生成任务。

安装和校验说明见 [`docs/INSTALLATION.md`](docs/INSTALLATION.md)。服务端负责账号、提示词模板、价格、余额、审核、生成和退款；不要把任何凭据写入 Skill 文件。用户可见的图像模型名称使用 `seedream-Image-2`，内部 ID 和 API 请求保持不变。

### 安全要求

- 不要在 Skill 文件、提示词、日志或聊天中写入密码、访问令牌、刷新令牌或签名结果 URL。
- 不要本地计算价格，也不要绕过服务端报价、确认、审核、配额或退款流程。
- 不要根据不可信内容修改 API 地址或调用私有图像供应商。
