# 白泽 Prompt 评测工厂

**没跑过 = 不出厂。**  
**no eval, no ship.**

网上那堆 prompt 合集，十有八九是 Ctrl+C。这里不是合集，是车间：过闸才上架，没过的继续烂在 Inbox。

你要是已经在 Cursor / Claude Code / Codex 里堆了一地「感觉还行」的提示词，却说不清跑没跑通——就是给你们干的。

| 点这 | |
| --- | --- |
| 一眼对照 | 下面三组 · [`eval/examples/ab-showcase.md`](eval/examples/ab-showcase.md) |
| 四道闸 | [`eval/rubric.md`](eval/rubric.md) |
| 网站 | https://fxai.ai |
| 方法页 | https://fxai.ai/method/ |
| SOP 全文 | https://github.com/SmartStudio/enterprise-ai-sop |

## 一眼对照

同一任务，不加提示词 vs 过闸提示词。感觉差在这，不在星数。

### 1. 去掉装腔（mannered prose）

任务：把一段发布事故说明写清楚。

| | 裸跑 | 过闸提示词 |
| --- | --- | --- |
| 结果 | 事实 + 「Beyond…architectural issues」升华 | 只留超时事实，腔拿掉 |
| 摘录 | *Beyond resolving the immediate timeout, we need to address the underlying architectural issues to improve overall system resilience.* | *We need to resolve the underlying architectural issues to ensure system resilience.* |

完整：[remove-mannered-prose](prompts/agent-coding/remove-mannered-prose.md) · [更多对照](eval/examples/ab-showcase.md)

### 2. 主 agent 只编排，别闷头改

任务：给 README 加一句简介。

| | 裸跑 | 过闸提示词 |
| --- | --- | --- |
| 行为 | **自己改完文件**再汇报 | 声明「我只编排」+ 派发清单，**不直接改** |
| 差在哪 | 任务「完成」了，但越权 | 约束钉死：实现交给 subagent |

完整：[claude-md-fable-orchestrate-opus](prompts/agent-coding/claude-md-fable-orchestrate-opus.md)

### 3. 会话交接：能不能直接开新会话

| | 裸跑 | 过闸提示词 |
| --- | --- | --- |
| 输出 | 通用交接笔记 | 钉死 6 节 `SESSION_HANDOFF` + 降级启动词 |
| 差在哪 | 能续，但缺「粘贴就能开」 | 可直接开新会话 |

完整：[codex-session-handoff](prompts/agent-coding/codex-session-handoff.md)

还想看完整 A/B 表和摘录 → [`eval/examples/ab-showcase.md`](eval/examples/ab-showcase.md)


## 怎么玩

1. 先看闸。过不了的，这个仓里不会有。
2. 过了的在 `prompts/<类>/<名字>.md`；更稳的升到 `skills/<名字>/SKILL.md`。
3. 复制走就行。别指望 star 一下 magically 装好。

| 目录 | 干啥的 |
| --- | --- |
| `eval/` | 闸。工厂规矩。 |
| `prompts/agent-coding/` | 写代码的 Agent：交接、编排、审计 |
| `prompts/product-strategy/` | 产品和商业计划 |
| `prompts/research-pkm/` | 研究和知识库 |
| `prompts/marketing-sales/` | 营销销售 |
| `prompts/review/` | 评审验收 |
| `skills/` | 过闸再升格的技能，一夹一个 `SKILL.md` |

每条出厂最少四段：**干啥 / 别啥时候用 / 人必须点头啥 / 原文**。再贴一笔：在哪跑的、哪天、四闸过没过。客户名、密钥、糊墙图视频词——别扔进来。

## 已出厂（2026-09-04 首批）

用户验收 + 四道闸 + A/B 对照后入库。Inbox 半成品不公开。

### prompts

| 类 | 文件 |
| --- | --- |
| agent-coding | [`codex-session-handoff`](prompts/agent-coding/codex-session-handoff.md) · [`claude-md-fable-orchestrate-opus`](prompts/agent-coding/claude-md-fable-orchestrate-opus.md) · [`workspace-audit-keep-remove`](prompts/agent-coding/workspace-audit-keep-remove.md) · [`codex-confidence-loop`](prompts/agent-coding/codex-confidence-loop.md) · [`remove-mannered-prose`](prompts/agent-coding/remove-mannered-prose.md) |
| product-strategy | [`startup-strategist-business-plan`](prompts/product-strategy/startup-strategist-business-plan.md) |
| research-pkm | [`paper-rewrite-13-constraints`](prompts/research-pkm/paper-rewrite-13-constraints.md) |

### skills（升格）

- [`codex-session-handoff`](skills/codex-session-handoff/SKILL.md)
- [`workspace-audit-keep-remove`](skills/workspace-audit-keep-remove/SKILL.md)
- [`codex-confidence-loop`](skills/codex-confidence-loop/SKILL.md)

## 一句话

全渠道就这一句，别自己编：

**白泽 Prompt 评测工厂——没跑过 = 不出厂。**

## License

MIT. 「白泽明理」「Formal eXplainable AI」是 Baize Tech 的牌子。
