# 白泽 Prompt 评测工厂

**没跑过 = 不出厂。**  
**no eval, no ship.**

网上那堆 prompt 合集，十有八九是 Ctrl+C。这里不是合集，是车间：过闸才上架，没过的继续烂在 Inbox。

你要是已经在 Cursor / Claude Code / Codex 里堆了一地「感觉还行」的提示词，却说不清跑没跑通——就是给你们干的。

| 点这 | |
| --- | --- |
| 怎么写出厂文档 | [`docs/PROMPT_TEMPLATE.md`](docs/PROMPT_TEMPLATE.md) |
| 四道闸 | [`eval/rubric.md`](eval/rubric.md) |
| 网站 | https://fxai.ai |
| 方法页 | https://fxai.ai/method/ |
| SOP 全文 | https://github.com/SmartStudio/enterprise-ai-sop |

## 一眼对照

先看同一任务出了什么问题，再看加 Prompt 后具体差在哪。

### 1. 事故说明别再抬价

**问题**：发布流水线两次超时，模型保住了事实，却加了一层架构升华。

**输入**：同一段包含「失败两次、部署脚本、30 分钟超时」的事故说明。

**A 裸跑**：保留 “Beyond resolving the immediate timeout” 这层铺垫。  
**B 加 Prompt**：删掉铺垫，直接说处理架构问题。  
**差在哪**：四个事故事实都还在，没有新编数字或原因，语气更平。

完整页：[`remove-mannered-prose.md`](prompts/agent-coding/remove-mannered-prose.md)

### 2. 主 agent 别越权实现

**问题**：任务只是给 README 加一句简介，主 agent 直接改完文件，违反了只编排的角色约束。

**输入**：同一句 README 修改任务。

**A 裸跑**：自己改文件，再汇报完成。  
**B 加 Prompt**：说明自己只编排，给出派发清单，没有改 README。  
**差在哪**：A 完成了任务却越权，B 把实现留给 subagent。

完整页：[`claude-md-fable-orchestrate-opus.md`](prompts/agent-coding/claude-md-fable-orchestrate-opus.md)

### 3. 会话交接要能直接续

**问题**：上下文太长要换会话，普通交接只写概况和待办，没留下可直接启动下一会话的内容。

**输入**：同一个 scratch 会话迁移任务。

**A 裸跑**：给通用交接笔记，没钉新会话命名和失败降级。  
**B 加 Prompt**：固定交接结构，保留未提交改动，并给可粘贴启动词。  
**差在哪**：A 还要人二次整理，B 可以核对现场后直接续开发。

完整页：[`codex-session-handoff.md`](prompts/agent-coding/codex-session-handoff.md)

## 怎么玩

1. 打开任意出厂页：先读「原始问题」和「给模型的输入」，再复制 Prompt 自己跑。
2. 对照「跑完会差在哪」。看不懂输入、对不上 A/B 的条目不该出现在这里。
3. 要投稿，按 [`docs/PROMPT_TEMPLATE.md`](docs/PROMPT_TEMPLATE.md) 写。Inbox 半成品不公开。

| 目录 | 干啥的 |
| --- | --- |
| `docs/` | 出厂文档规范 |
| `eval/` | 闸门 |
| `prompts/agent-coding/` | 写代码的 Agent |
| `prompts/product-strategy/` | 产品和商业计划 |
| `prompts/research-pkm/` | 研究和知识库 |
| `prompts/marketing-sales/` | 营销销售 |
| `prompts/review/` | 评审验收 |
| `skills/` | 过闸再升格的技能 |

## 已出厂（2026-09-04 首批）

用户验收 + 四道闸 + A/B 对照后入库。按 v3 读者路径重排。

### prompts

| 类 | 文件 |
| --- | --- |
| agent-coding | [`remove-mannered-prose`](prompts/agent-coding/remove-mannered-prose.md) · [`claude-md-fable-orchestrate-opus`](prompts/agent-coding/claude-md-fable-orchestrate-opus.md) · [`codex-session-handoff`](prompts/agent-coding/codex-session-handoff.md) · [`codex-confidence-loop`](prompts/agent-coding/codex-confidence-loop.md) · [`workspace-audit-keep-remove`](prompts/agent-coding/workspace-audit-keep-remove.md) |
| product-strategy | [`startup-strategist-business-plan`](prompts/product-strategy/startup-strategist-business-plan.md) |
| research-pkm | [`paper-rewrite-13-constraints`](prompts/research-pkm/paper-rewrite-13-constraints.md) |

### skills（升格）

- [`codex-session-handoff`](skills/codex-session-handoff/SKILL.md)
- [`workspace-audit-keep-remove`](skills/workspace-audit-keep-remove/SKILL.md)
- [`codex-confidence-loop`](skills/codex-confidence-loop/SKILL.md)


## 已出厂（2026-09-05 第二批）

用户验收 11 条 Inbox A/B 后入库，按 v3 读者路径出厂。另开本 PR，不追加 #1。

### prompts / agent-coding

| 文件 | 一句话 |
| --- | --- |
| [`design-fragment-clarify`](prompts/agent-coding/design-fragment-clarify.md) | 碎碎念先多轮澄清，别闷头设计 |
| [`codex-github-research-before-build`](prompts/agent-coding/codex-github-research-before-build.md) | GitHub 先调研再实现，确认前停 |
| [`codex-pre-delivery-requirements`](prompts/agent-coding/codex-pre-delivery-requirements.md) | 交付前先出方案与验收清单 |
| [`codex-repeated-work-to-skill`](prompts/agent-coding/codex-repeated-work-to-skill.md) | 重复工作先列候选再沉淀 Skill |
| [`codex-dev-state-archive`](prompts/agent-coding/codex-dev-state-archive.md) | 根目录 DEV_STATE 可续跑 |
| [`codex-long-session-closeout`](prompts/agent-coding/codex-long-session-closeout.md) | 长会话收尾三件套 |
| [`codex-goal-template`](prompts/agent-coding/codex-goal-template.md) | 先落 GOAL.md 再实现 |
| [`codex-task-contract`](prompts/agent-coding/codex-task-contract.md) | 任务契约五段可审 |
| [`karpathy-pairing-constraints`](prompts/agent-coding/karpathy-pairing-constraints.md) | 冲突就停，不静默选边 |
| [`codex-context-slim`](prompts/agent-coding/codex-context-slim.md) | 先裁上下文再审查 |
| [`codex-goal-scenario-pack`](prompts/agent-coding/codex-goal-scenario-pack.md) | Goal 场景扩展包（部分场景未全测） |

## 一句话

全渠道就这一句，别自己编：

**白泽 Prompt 评测工厂——没跑过 = 不出厂。**

## License

MIT. 「白泽明理」「Formal eXplainable AI」是 Baize Tech 的牌子。
