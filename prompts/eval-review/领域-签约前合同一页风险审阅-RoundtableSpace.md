---
title: 领域-签约前合同一页风险审阅-RoundtableSpace
category: eval-review
source: https://x.com/RoundtableSpace/status/2110283260597010773
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

# 领域-签约前合同一页风险审阅-RoundtableSpace

企业/个人签约前审阅：费用/期限/单边条款逐条引用原文、缺失项、签前 5 问，明确非法律意见，B104。

## 原始问题

企业/个人签约前审阅：费用/期限/单边条款逐条引用原文、缺失项、签前 5 问，明确非法律意见，B104。

## 给模型的输入

跑台使用合成输入，原始输入未公开记录（not_recorded）。用你自己的真实材料替换 Prompt 里的占位内容即可。

## 复制这条 Prompt

把你的输入和下面这段 Prompt（源帖原文）放进同一条消息，再发送。

```text
"You are reviewing a document I'm about to sign. I am not a lawyer. Read the entire document before answering.

1.⁠ ⁠Summarize what I'm agreeing to in 5 plain-English bullet points.
2.⁠ ⁠List every payment, fee, deposit, penalty and automatic price increase, with the clause number and the exact amount or formula.
3.⁠ ⁠List every deadline and notice period I have to meet, and what happens if I miss it.
4.⁠ ⁠Flag clauses that are unusual, one-sided or hard to undo, such as auto-renewal, early termination, liability, arbitration and data sharing. Quote each clause and explain the risk in one sentence.
5.⁠ ⁠Tell me what a document like this would normally include that this one is missing.
6.⁠ ⁠Write the 5 questions I should ask before signing, most important first.

Rules: quote the document for every claim. If something is unclear or not in the document, say so instead of guessing. Don't give legal advice. Tell me where I should ask a lawyer."
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
