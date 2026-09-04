---
title: 去掉 mannered prose
category: agent-coding
source: https://x.com/Voxyz_ai/status/2095260094795583807
ran_on: prompt-lab / Codex+agy
ran_at: 2026-09-04
gate_complete: true
gate_traceable: true
gate_safe: true
gate_one_pass: true
---

## 用途

- 目标：去掉装腔 / AI 腔（含「不是 X，而是 Y」一类句式）。
- 约束：删除 mannered prose；保留事实与判断。
- 输出格式：改写后的正文；不解释、不加「以下是去 AI 味版本」。

## 何时不用

缺目标/约束/格式时不要用；图视频任务不要用；未签边界不要放大自动化。

## 边界

人必须批准：是否入库到生产工作流、是否写入真实仓库/会话。评测 fixture 不得指向真实 vault 或生产密钥。

## 原文

```
Please remove all mannered prose.
```

## 评测记录

- 跑通环境：prompt-lab / Codex+agy
- 跑通日期：2026-09-04
- 闸门：完整 / 可溯源 / 安全 / 至少一通 = 全是
- A/B 对照摘要：

---
type: ab-compare
created: 2026-09-04
item: 去掉mannered-prose
model: agy gemini-3.8-flash-high high
---

# 对照：去掉 mannered-prose


## A/B 对照（agy · gemini-3.8-flash-high · high）

同一 fixture。A=中性「请完成任务」；B=目标提示词 `Please remove all mannered prose.`。Codex 本轮未重跑（看板：暂维持现状）。

| 维 | A 基线 | B 处理 |
| :--- | :--- | :--- |
| 结构 | 两句改写，保留超时事实 + 架构/韧性升华 | 两句改写，保留超时事实 + 架构/韧性 |
| 约束 | 无去腔约束；仍留「Beyond…underlying architectural issues」类升华 | 去掉 not-X-but-Y；腔调更平 |
| 胡编 | 无硬数字 | 无硬数字 |
| 可执行性 | 可读，但未明确「只去 mannered prose」 | 更贴目标约束 |

**摘录 A**：`runs/ab/2026-09-04-mannered-agy-A.md`
> Yesterday, our release pipeline failed twice due to the deployment script timing out after 30 minutes. Beyond resolving the immediate timeout, we need to address the underlying architectural issues to improve overall system resilience.

**摘录 B**：`runs/ab/2026-09-04-mannered-agy-B.md`
> Our release pipeline failed twice yesterday because the deploy script timed out after 30 minutes. We need to resolve the underlying architectural issues to ensure system resilience.

**建议**：对照有效——B 去掉了「It's not X; it's Y」与结尾空泛升华，事实保留。可给人判入库；若要更狠，可补一句「不要升华，只保留事实句」。
