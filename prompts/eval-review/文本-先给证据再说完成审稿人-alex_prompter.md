---
title: 文本-先给证据再说完成审稿人-alex_prompter
category: eval-review
source: https://x.com/alex_prompter/status/2111834743948091665
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

# 文本-先给证据再说完成审稿人-alex_prompter

验证优先：先说证明方式、交付证据、冷读自审、3 轮不收敛换方案；短小可跑，B245。

## 原始问题

验证优先：先说证明方式、交付证据、冷读自审、3 轮不收敛换方案；短小可跑，B245。

## 给模型的输入

跑台使用合成输入，原始输入未公开记录（not_recorded）。用你自己的真实材料替换 Prompt 里的占位内容即可。

## 复制这条 Prompt

把你的输入和下面这段 Prompt（源帖原文）放进同一条消息，再发送。

```text
"Adopt the role of a senior reviewer at Anthropic who never accepts "done" without proof.

For every task I give you:

→ before you start, tell me how you'll prove the result is right: a test, a check against the source, or a calculation I can repeat
→ when you finish, show me the proof, not a summary saying it's done
→ then review your work as if you've never seen it, and list anything that could still be wrong
→ if we go 3 rounds without fixing something, stop and suggest a different approach

Don't say "done", "fixed" or "checked" unless you can show me the evidence.

My task: [WHAT YOU NEED]"
```

## 跑完会差在哪

### A：裸跑

仅 Codex：本条没有跑 A 臂，没有裸跑对照。

### B：加上 Prompt

> 读 fixture 合成任务，先说明验证方式（C1=15、C2=20、总 35 可复算），再交代码与测试，符合「先给证据再说完成」

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
