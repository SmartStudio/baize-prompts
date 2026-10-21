---
title: 文本-让AI追问找盲点九条-iannuttall
category: research-pkm
source: https://x.com/iannuttall/status/1933498347849232431
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

# 文本-让AI追问找盲点九条-iannuttall

九条「请追问我」式诊断提示（增长/营销/代码），B230。

## 原始问题

九条「请追问我」式诊断提示（增长/营销/代码），B230。

## 给模型的输入

跑台使用合成输入，原始输入未公开记录（not_recorded）。用你自己的真实材料替换 Prompt 里的占位内容即可。

## 复制这条 Prompt

把你的输入和下面这段 Prompt（源帖原文）放进同一条消息，再发送。

```text
"I've hit a growth plateau at [specific metric] despite implementing [strategies I've tried]. Please ask me detailed questions about my business model, customer acquisition, and processes to identify potential blind spots in my approach."

"My customer retention rate is [%] and I've attempted [list of retention strategies]. Please interrogate my user onboarding, product experience, and customer success processes through targeted questions to find the root cause."

"My product has solid user engagement but monetization is struggling at [current metrics]. Please ask probing questions about my pricing strategy, value proposition, and customer willingness to pay until we identify the core issue."

Marketing:

"My conversion rates are stuck at [%] across [channels] despite optimizing [specific elements]. Please ask detailed questions about my target audience, messaging, and customer touchpoints to uncover what I'm missing."

"I'm spending [budget] on paid advertising with poor ROAS of [ratio]. Please interrogate my targeting parameters, creative assets, and attribution model through systematic questioning."

"My content generates strong engagement metrics but produces minimal qualified leads. Please question my content strategy, calls‑to‑action, and lead nurturing process to identify the disconnect."

Code:

"I'm experiencing persistent performance issues with [specific system] despite implementing [optimizations attempted]. Please ask technical questions about my architecture, database queries, and infrastructure to diagnose the problem."

"Users are experiencing issues with [feature] that I recently launched, despite thorough testing. Please question my implementation approach, user experience design, and feedback collection methods."

"My application has comprehensive test coverage but critical bugs still reach production. Please interrogate my testing methodology, deployment pipeline, and monitoring systems."
```

## 跑完会差在哪

### A：裸跑

仅 Codex：本条没有跑 A 臂，没有裸跑对照。

### B：加上 Prompt

> Codex 单次运行通过人判。

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
