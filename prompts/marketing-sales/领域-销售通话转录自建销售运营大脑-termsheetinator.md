---
title: 领域-销售通话转录自建销售运营大脑-termsheetinator
category: marketing-sales
source: https://x.com/termsheetinator/status/2088969272416673820
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

# 领域-销售通话转录自建销售运营大脑-termsheetinator

B2B RevOps：通话转录同步→结构化富化→异议库/买方语言/报告/记忆文件，每条结论回链来源，B152。

## 原始问题

B2B RevOps：通话转录同步→结构化富化→异议库/买方语言/报告/记忆文件，每条结论回链来源，B152。

## 给模型的输入

跑台使用合成输入，原始输入未公开记录（not_recorded）。用你自己的真实材料替换 Prompt 里的占位内容即可。

## 复制这条 Prompt

把你的输入和下面这段 Prompt（源帖原文）放进同一条消息，再发送。

```text
“Turn this folder into a self-enriching Sales-Ops Brain.

Build a Fathom sync that pulls every new meeting  transcript, tracks meeting IDs in processed.json and never duplicates or overwrites raw calls.

Use the OpenAI API with structured outputs to analyze every transcript and create:

- /calls/raw/ for immutable transcripts
- /calls/enriched/ for one structured .md file per call
- /knowledge/objections.md with exact buyer language
- separate .md files for desired outcomes, buying criteria, winning language, stakeholders, risks, deal stages and next steps
- /reports/daily/ and /reports/monthly/
- /prompts/ for one-shot VSL, deck, email and content prompts
- MEMORY.md for repeated sales patterns
- AGENTS.md for stable operating rules

Every claim must link back to the source call and date.”
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
