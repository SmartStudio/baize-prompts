# 白泽 Prompt 评测工厂 · Baize Prompt Lab

**提示词过评测才出厂。**  
**A factory that only ships prompts that passed eval.**

[白泽明理](https://fxai.ai) 的公开评测车间。不是又一个提示词搬运站。Inbox 里的半成品、截图、视频提示词、没跑通的条目，都不会出现在这里。

**给谁。** 已经在用 Cursor / Claude Code / Codex 的团队：仓库里堆了一堆「好像能用」的提示词，没人说清目标、约束、和人必须批准什么。

**比现状好在哪。** 大多数公开 prompt 库是粘贴板。这里先过四道闸，再出厂：完整（目标 + 约束 + 格式）/ 可溯源 / 安全 / 至少一通。先写清边界，再自动化。

| 下一步 | 链接 |
| --- | --- |
| 评测闸门 | [`eval/rubric.md`](eval/rubric.md) |
| 官网 / 方法 | https://fxai.ai · https://fxai.ai/method/ |
| SOP（方法论） | https://github.com/SmartStudio/enterprise-ai-sop |
| 预约诊断 | https://fxai.ai/contact/ |

## Quick start

1. 先读 [评测闸门](eval/rubric.md)。过不了闸的条目不会进本仓。
2. 过闸之后按分类看 `prompts/<cat>/<slug>.md`，或升格后的 `skills/<name>/SKILL.md`。
3. 复制到你的 Agent，或贴进对话。没有安装包。

| 路径 | 出厂后放什么 |
| --- | --- |
| `eval/` | 闸门、模板。工厂本身。 |
| `prompts/agent-coding/` | 编码 Agent：交接、编排、审计 |
| `prompts/product-strategy/` | 产品策略 / 商业计划 |
| `prompts/research-pkm/` | 研究与知识库维护 |
| `prompts/marketing-sales/` | 营销销售 |
| `prompts/review/` | 评审验收 |
| `skills/` | 评测后升格的可重复技能，每技能一个目录 + `SKILL.md` |

每条出厂提示词最少四段：**用途 / 何时不用 / 边界（人必须批准什么） / 原文**。另附评测记录：来源、跑通日期、闸门逐条结果。不收客户名和密钥。

现在公开的是工厂骨架。第一条过闸条目随验收发布。

## 品类句

全渠道复用这一句，不另起：

白泽 Prompt 评测工厂——提示词过评测才出厂。

## License

MIT. 品牌名「白泽明理」「Formal eXplainable AI」仍归 Baize Tech。
