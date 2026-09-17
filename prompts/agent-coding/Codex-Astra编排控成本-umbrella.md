---
title: Astra 编排控成本：事件等待 + Luna 委派，停掉分钟级心跳
category: agent-coding
source: https://x.com/umbrella_uni/status/2098758114400997663
ran_on: prompt-lab / agy+Codex
ran_at: 2026-09-16
model: gemini-3.8-flash-high (agy); gpt-6-astra medium (codex)
input_status: note_verbatim_main
excerpt_a: runs/ab/batch-search0915pm/umbrella-A.md
excerpt_b: runs/ab/batch-search0915pm/umbrella-B.md
gate_complete: true
gate_traceable: true
gate_safe: true
gate_one_pass: true
---

# Astra 编排控成本：事件等待 + Luna 委派，停掉分钟级心跳

同 fixture 下，裸跑会出基线审计；目标 Prompt 把「给现有 Luna 完整工作流、事件驱动等待、禁短心跳、简洁报告、前后 token 对比」写成可落地方案。

## 原始问题

Astra 父协调器每分钟唤醒查进度、倾倒全量日志，30 分钟 +180k tokens。要在不破 scope/锁/审批边界下控成本。

## 给模型的输入

```text
工作目录：scratch-umbrella/{a|b|c}（REPORT-ONLY；禁止启动真实 subagent/worker）
fixture：orchestration/scenario.md · workers.json · logs/parent-token-before.txt
边界：不改真实 Astra/Luna 运行时；不声称已实测节省除非有 after 日志
报告：runs/ab/batch-search0915pm/umbrella-{A|B|B-codex}.md
```

## 复制这条 Prompt

把上面的输入和下面这段 Prompt（源帖原文）放进同一条消息，再发送。

```text
Additional orchestration cost control:

Apply this now and preserve it through handoffs and compaction. Give existing Luna Max workers complete operational workflows, including execution, testing, polling, verification, and routine recovery. Use one existing Luna coordinator for worker/reviewer handoffs and already-authorized next steps. Preserve scope, locks, serialization, and approval boundaries.

Astra must not wake every minute to check progress. Use event-driven waiting that returns on meaningful worker results or user input. Where only timed event waits exist, use the longest permitted wait that remains interruptible by those events—not short heartbeat intervals. A timeout alone is not a reason to request status, reread logs, or say “still waiting.”

Do not end a turn merely to announce waiting if a persistent goal immediately restarts it. Workers should progress independently within their authorization and report completed milestones, actionable blockers, or exceptions requiring intervention.

Keep reports concise: outcome, evidence paths, blocker, and decision needed. Avoid full logs, duplicate verification, and unchanged-status messages. Cached context still consumes usage; short responses do not necessarily mean cheap calls.

Verify actual behavior: instruction received, execution delegated, long/event waits active, and repeated status-only model calls stopped. Compare parent token consumption over time before and after. A queued instruction is not an applied fix, and an unchanged rounded usage percentage does not mean zero consumption.

If runtime constraints prevent suspension, identify the exact limitation and required control change. Do not claim success or guaranteed savings. Do not create another frequent model-driven monitoring loop to check this one.
```

## 跑完会差在哪

### A：裸跑

> 基线审计：28 次状态轮询 / +180234 tokens / 60s 心跳 / 0 事件等待；根因与委派缺口写清。偏诊断，弱「apply now + verify after」。

### B：加上 Prompt

> 按 MAIN 落「Luna 完整工作流 + luna-coord-1 交接 + 事件等待 + 简洁报告」；明确 REPORT-ONLY；给验证规划与 before/after 指标表。

差别：A=诊断；B=可执行控成本方案 + 验证清单。Codex-B 更硬：当前仅方案与基线，未下发指令、未采 after 日志、不保证已节省。

## 什么时候别用

没有 Luna/协调器 fixture、或需要真改运行时并测节省时，先换带 after 日志的评测夹具。

## 人要检查什么

1. 是否 REPORT-ONLY（未启动真实 worker）。
2. 是否把「排队指令≠已应用」「rounded %≠零消耗」写清。
3. 是否保留 scope/锁/审批边界。

## 四维评测

| 维度 | A：裸跑 | B：加上 Prompt |
| --- | --- | --- |
| 结构 | 基线审计 | 方案+验证规划 |
| 约束 | REPORT-ONLY | 同左 + MAIN 控成本契约 |
| 胡编 | 未谎称已节省 | Codex 明确 after 未采 |
| 可执行性 | 可参考诊断 | 可当编排控成本 MAIN |
