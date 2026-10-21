---
title: 文本-建议背后隐藏激励三段拆解-free_ai_guides
category: research-pkm
source: https://x.com/free_ai_guides/status/2089031816544215112
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

# 文本-建议背后隐藏激励三段拆解-free_ai_guides

三段式（来源与利益/激励与信号/零利益改写），要求不预设恶意，输出可核对。

## 原始问题

三段式（来源与利益/激励与信号/零利益改写），要求不预设恶意，输出可核对。

## 给模型的输入

跑台使用合成输入，原始输入未公开记录（not_recorded）。用你自己的真实材料替换 Prompt 里的占位内容即可。

## 复制这条 Prompt

把你的输入和下面这段 Prompt（源帖原文）放进同一条消息，再发送。

```text
You are my incentive analyst. I'll paste a piece of advice, a recommendation, or a sales pitch, and your job is to show me the incentive behind it so I can weigh it for myself.

Break it into three parts:

1. Source and stake. Name who is giving this and what they gain if I act on it (money, status, attention, or a belief they need to defend).

2. Incentive vs signal. Point out which parts of the message are bent by that stake, and which parts would still hold if the person had nothing to gain.

3. The clean version. Rewrite the advice the way it would sound from someone with zero stake in my choice.

Stay fair. Don't assume bad faith. Most advice mixes real help with self-interest, and I want to see exactly where that line falls.

Advice to analyze:
[paste it here]
```

## 跑完会差在哪

### A：裸跑

仅 Codex：本条没有跑 A 臂，没有裸跑对照。

### B：加上 Prompt

> 读 fixture 合成建议，按来源与利益/激励与信号/干净版本三段拆解，声明占位值非真实

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
| 约束 | 未跑（仅 Codex） | 人判通过 |
| 胡编 | 未跑（仅 Codex） | 人判未发现编造 |
| 可执行性 | 未跑（仅 Codex） | 可直接复制使用 |
