---
title: 文本-NotebookLM学习研究二十条-sonalshukla3377
category: research-pkm
source: https://x.com/sonalshukla3377/status/2051133114702074337
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

# 文本-NotebookLM学习研究二十条-sonalshukla3377

NotebookLM 20 条短提示（摘要、初学者解释、学习计划、教学稿等），B2009。

## 原始问题

NotebookLM 20 条短提示（摘要、初学者解释、学习计划、教学稿等），B2009。

## 给模型的输入

跑台使用合成输入，原始输入未公开记录（not_recorded）。用你自己的真实材料替换 Prompt 里的占位内容即可。

## 复制这条 Prompt

把你的输入和下面这段 Prompt（源帖原文）放进同一条消息，再发送。

```text
01. Instant Summary
Turn long documents into digestible insights.
👉 Prompt:
“Summarize this source into the 10 most important ideas, key arguments, and practical takeaways in plain English.”

02. Beginner Explanation
Make complex topics easy to understand.
👉 Prompt:
“Explain this material as if I am a complete beginner. Use simple analogies, step-by-step logic, and avoid jargon.”

03. Deep Dive Breakdown
Understand the topic layer by layer.
👉 Prompt:
“Break this source into core concepts, hidden assumptions, expert-level nuances, and what most readers usually miss.”

04. Compare Sources
Spot agreements and contradictions.
👉 Prompt:
“Compare all uploaded sources. Show where they agree, where they conflict, and what unique insights each source contributes.”

05. Study Notes Builder
Create clean notes instantly.
👉 Prompt:
“Turn this content into structured study notes with headings, bullet points, definitions, and memorable examples.”

06. Flashcards Generator
Convert information into active recall.
👉 Prompt:
“Generate 25 high-quality flashcards from this material with question on front and concise answer on back.”

07. Quiz Me
Test your understanding.
👉 Prompt:
“Create a progressive quiz from easy to difficult based only on this source. Wait for my answers and grade me.”

08. Memory Hooks
Make information stick.
👉 Prompt:
“Create mnemonics, analogies, and memory anchors that help me retain the most important parts of this content.”

09. Timeline Extraction
Organize events chronologically.
👉 Prompt:
“Extract every important event, milestone, or development from these sources and arrange them into a clean timeline.”

10. Key Quotes Finder
Find the strongest supporting evidence.
👉 Prompt:
“Pull out the most impactful quotes, data points, and evidence from these sources that I can cite in writing or presentations.”

11. Research Gaps
See what’s missing.
👉 Prompt:
“Identify unanswered questions, weak arguments, missing evidence, and research gaps across these materials.”

12. Debate Both Sides
Sharpen critical thinking.
👉 Prompt:
“Present the strongest arguments for and against the main thesis of these sources as if two experts were debating.”

13. Turn Into Framework
Extract repeatable systems.
👉 Prompt:
“Convert the ideas in these sources into a practical framework, checklist, or repeatable system I can apply.”

14. Content Repurposing
Turn research into publishable content.
👉 Prompt:
“Use these sources to generate a LinkedIn post, article outline, tweet thread, and newsletter idea.”

15. Expert Interview Mode
Ask the notebook questions.
👉 Prompt:
“Act as the world’s top expert on these uploaded materials. I will ask questions answer only from the sources.”

16. Executive Briefing
Condense for busy decision making.
👉 Prompt:
“Create a 5-minute executive briefing with only the most strategic insights, implications, and action points.”

17. Lesson Plan Creator
Transform notes into a curriculum.
👉 Prompt:
“Turn this notebook into a 7-day learning plan with daily lessons, exercises, and checkpoints.”

18. Idea Generator
Use sources for new thinking.
👉 Prompt:
“Generate 20 original ideas, opportunities, or applications inspired by the uploaded materials.”

19. Simplify for Teaching
Prepare to explain to others.
👉 Prompt:
“Rewrite the key ideas from these sources into a teaching script that I can explain to someone in 5 minutes.”

20. Action Plan
Move from knowledge to execution.
👉 Prompt:
“Based on everything in these sources, create a practical action plan with first steps, priorities, and deadlines.”
```

## 跑完会差在哪

### A：裸跑

仅 Codex：本条没有跑 A 臂，没有裸跑对照。

### B：加上 Prompt

> 读 fixture 三篇合成笔记，按合集第 1 条提示输出 10 条要点，逐条可回溯到笔记，未补外部事实

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
