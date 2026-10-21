---
title: 领域-外呼历史反推信号提升率-chrispisarski
category: marketing-sales
source: https://x.com/chrispisarski/status/2082236016161677644
ran_on: prompt-lab / Codex
ran_at: 2026-10-20
model: not_recorded
input_status: not_recorded
excerpt_a: 不适用（仅 Codex）
excerpt_b: Codex 单次运行
ab: 仅 Codex
image: 不适用
gate_complete: true
gate_traceable: true
gate_safe: true
gate_one_pass: codex_only
---

# 领域-外呼历史反推信号提升率-chrispisarski

B2B GTM：按联系当日重建信号状态、算每信号回复率 lift 与时间窗、只留 1.5x+、留出 20% 验证，B1396。

## 原始问题

B2B GTM：按联系当日重建信号状态、算每信号回复率 lift 与时间窗、只留 1.5x+、留出 20% 验证，B1396。

## 给模型的输入

跑台使用合成输入，原始输入未公开记录（not_recorded）。用你自己的真实材料替换 Prompt 里的占位内容即可。

## 复制这条 Prompt

把你的输入和下面这段 Prompt（源帖原文）放进同一条消息，再发送。

```text
"you have ./outbound_history.csv (every account ever contacted: date, replied, meeting, won)

1. for each account, reconstruct the signal state at contact date via crustdata: headcount delta prior quarter, days since funding, open roles matching [titles], exec hires prior 90 days, posts, all relevant signals

2. calculate lift per signal: reply rate with signal vs baseline reply rate

3. calculate each signal's window: median days between signal and the replies it produced

4. read the reply threads per signal and extract the angle that worked

5. write ./signals.md: only signals with 1.5x+ lift, each with: lift, window, the proven angle. everything else gets deleted, not monitored

6. verify with a subagent: hold out 20% of history, check the ranking predicts reply rate on the holdout. loop until it does"
```

## 跑完会差在哪

### A：裸跑

仅 Codex：本条没有跑 A 臂，没有裸跑对照。

### B：加上 Prompt

> Codex 单次运行，人判通过（有软项）：fixture 里没有时间戳和回复原文，第 3、4 步标了「无法计算」。

差别：只有 B 的单次 Codex 结果，按 2026-10-19 起的规则「Codex 单次通过即收」出厂，未做 A/B 对照。

## 什么时候别用

需要逐字可复核的 A/B 证据，或涉及真实客户数据、生产系统时，先自己补一轮对照再用。

## 人要检查什么

1. 输出里的事实、数字有没有新编。
2. 是否按 Prompt 的格式和约束交付。
3. 涉及对外发送或生产动作时，人点头再执行。

## 四维评测

| 维度 | A：裸跑 | B：加上 Prompt |
| --- | --- | --- |
| 结构 | 未跑（仅 Codex） | 见上方 B 结果 |
| 约束 | 未跑（仅 Codex） | 人判通过（有软项，见上） |
| 胡编 | 未跑（仅 Codex） | 人判未发现编造 |
| 可执行性 | 未跑（仅 Codex） | 可直接复制使用 |
