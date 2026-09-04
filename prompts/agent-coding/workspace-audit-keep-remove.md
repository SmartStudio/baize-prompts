---
title: 工作区配置审计 KEEP/REMOVE
category: agent-coding
source: https://x.com/Voxyz_ai/status/2086150296842219888
ran_on: prompt-lab / Codex+agy
ran_at: 2026-09-04
gate_complete: true
gate_traceable: true
gate_safe: true
gate_one_pass: true
---

## 用途

- 目标：先审计工作区里会塑造 agent 行为的持久配置，再等批准后清理，然后按 outcome / boundaries / checks 继续当前任务。
- 约束：第一阶段禁止改任何文件；必须等批准；只删已批准的 REMOVE 项；安全规则、密钥处理、项目明确要求的配置一律保留；不清楚就问，不许猜。
- 输出格式：KEEP / REMOVE 清单，每项一句说明；清理后展示 diff 并跑项目已有检查。

## 何时不用

缺目标/约束/格式时不要用；图视频任务不要用；未签边界不要放大自动化。

## 边界

人必须批准：是否入库到生产工作流、是否写入真实仓库/会话。评测 fixture 不得指向真实 vault 或生产密钥。

## 原文

```
Audit every persistent configuration in this workspace that shapes how you work: project instructions, skills, MCPs, and memory.

Find anything redundant, outdated, conflicting, or irrelevant to this project. First give me a KEEP / REMOVE list with one sentence per item. Do not edit any files.

Wait for my approval. Remove only approved REMOVE items. Keep every safety rule, secret-handling rule, and configuration this project explicitly requires.

After cleanup, reread my current task. Focus on three things: the final outcome, the boundaries you must not cross, and the checks that prove the work is done.

Choose the implementation yourself. When finished, show the diff and run the project's existing checks. If anything is unclear, ask. Don't guess.
```

## 评测记录

- 跑通环境：prompt-lab / Codex+agy
- 跑通日期：2026-09-04
- 闸门：完整 / 可溯源 / 安全 / 至少一通 = 全是
- A/B 对照摘要：

---
type: ab-compare
item: 工作区配置审计-KEEP-REMOVE
---

# 对照：工作区配置审计

## A/B 对照（agy · gemini-3.8-flash-high · high）

同一 scratch fixture。A=中性「请完成任务」；B=目标提示词原文。Codex 本轮未重跑。未改文件。

| 维 | A 基线 | B 处理 |
| :--- | :--- | :--- |
| 结构 | KEEP/REMOVE 清单 | KEEP/REMOVE + 明确等批准 + MCP/Memory 缺失说明 |
| 约束 | 安全规则进 KEEP；Python2 进 REMOVE | 同；更强调「一句话说明」「等待审批」 |
| 胡编 | 无 | 无 |
| 可执行性 | 可用 | 更贴「先清单、等批准、再改」流程 |

全文：`runs/ab/2026-09-04-audit-agy-A.md` / `...-B.md`

**建议**：对照有差但不大——中性指令也能产出清单；B 把「等批准」钉死。可给人判入库。
