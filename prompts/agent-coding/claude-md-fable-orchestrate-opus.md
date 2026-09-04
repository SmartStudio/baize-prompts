---
title: CLAUDE.md Fable 编排 Opus subagent
category: agent-coding
source: https://x.com/dotey/status/2088099630005264748
ran_on: prompt-lab / Codex+agy
ran_at: 2026-09-04
gate_complete: true
gate_traceable: true
gate_safe: true
gate_one_pass: true
---

## 用途

- 目标：主 agent 只做分析、编排、验证；实现类工作交给 Opus subagent。
- 约束：主 agent（尤其 Fable 5）不做读大量代码、写代码、跑测试、批量修改；这些一律派给 subagent。
- 输出格式：需求澄清 / 方案拆解 / 任务分发 / 结果验收。原文未规定文件名或 JSON schema。

## 何时不用

缺目标/约束/格式时不要用；图视频任务不要用；未签边界不要放大自动化。

## 边界

人必须批准：是否入库到生产工作流、是否写入真实仓库/会话。评测 fixture 不得指向真实 vault 或生产密钥。

## 原文

```
注意你的主要任务是分析、编排和验证，具体任务尽可能交给 subagent（Opus）去执行。当主 agent 是 Fable 5 时尤其如此：自己只做需求澄清、方案拆解、任务分发和结果验收，实现类工作（读大量代码、写代码、跑测试、批量修改）一律用 Agent 工具派给 Opus subagent 执行。
```

## 评测记录

- 跑通环境：prompt-lab / Codex+agy
- 跑通日期：2026-09-04
- 闸门：完整 / 可溯源 / 安全 / 至少一通 = 全是
- A/B 对照摘要：

---
type: ab-compare
item: CLAUDE.md-Fable编排Opus-subagent
---

# 对照：Fable 编排

## A/B 对照（agy · gemini-3.8-flash-high · high）

同一 fixture（给 README 加一句简介）。A=中性「请完成任务」；B=目标提示词（主 agent 只编排）。Codex 本轮未重跑。

| 维 | A 基线 | B 处理 |
| :--- | :--- | :--- |
| 结构 | 直接改完 README 并汇报 | 声明编排者 + 无 subagent 诚实说明 + 派发清单 |
| 约束 | **越权实现**（自己改文件） | 遵守「不直接实现」；未改 README |
| 胡编 | 无 | 无 |
| 可执行性 | 任务完成但违反编排约束 | 可派发清单，待真实 subagent |

全文：`runs/ab/2026-09-04-fable-agy-A.md` / `...-B.md`

**建议**：对照极有效——提示词把行为从「闷头改」改成「只编排」。推荐入库。
