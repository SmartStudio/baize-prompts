---
title: 长对话上下文清理：只留目标/约束/决策/进度/未决/下一步
category: agent-coding
source: https://x.com/goan999999/status/2089284950411317362
ran_on: prompt-lab / agy+Codex
ran_at: 2026-09-16
model: gemini-3.8-flash-high (agy); gpt-6-astra medium (codex)
input_status: note_verbatim_main
excerpt_a: runs/ab/batch-search0915pm/goan-A.md
excerpt_b: runs/ab/batch-search0915pm/goan-B.md
gate_complete: true
gate_traceable: true
gate_safe: true
gate_one_pass: true
---

# 长对话上下文清理：只留目标/约束/决策/进度/未决/下一步

同 noisy SESSION_DUMP fixture 下，裸跑也会出精简摘要；目标 Prompt 把「删废弃/已完成噪音/无关历史/低价值重复 → 六段摘要 → 后续只依摘要」写死。

## 原始问题

长会话塞满废弃方案与重复输出，要清成可继续执行的精简任务摘要。

## 给模型的输入

```text
工作目录：scratch-goan/{a|b|c}
fixture：SESSION_DUMP.md（嘈杂长会话；含废弃方案/完成噪音/无关历史）
边界：REPORT-ONLY；勿改 SESSION_DUMP.md 本体（除非必要）
报告：runs/ab/batch-search0915pm/goan-{A|B|B-codex}.md
```

## 复制这条 Prompt

把上面的输入和下面这段 Prompt（源帖原文）放进同一条消息，再发送。

```text
请整理当前任务的上下文，清理无效信息，删除或标记已废弃方案、已完成无需参考的内容、与当前目标无关的历史记录以及低价值重复输出，并重新生成一份精简任务摘要，仅保留当前目标、核心约束、已确认决策、当前进度、未解决问题和下一步计划；后续执行任务时，以最新摘要作为主要依据，不再依赖已失效信息。
```

## 跑完会差在哪

### A：裸跑

> 六段摘要齐全（目标/约束/决策/进度/未决/下一步）；声明后续以摘要为准；未改 SESSION_DUMP。

### B：加上 Prompt

> 同六段；显式「彻底摒弃失效方案」措辞更贴 MAIN；结构更像交付模板。

差别：内容高度重叠；B 契约措辞更硬。Codex-B 更短，并诚实标明进度来自合成记录、未核实代码/测试。

## 什么时候别用

需要保留完整审计轨迹、或要改写原会话文件时别用。近族 DEV_STATE / 上下文精简——人判去重。

## 人要检查什么

1. SESSION_DUMP 是否未改（或仅必要标记）。
2. 六段是否齐；废弃方案是否剔除。
3. 是否声明后续只依摘要。

## 四维评测

| 维度 | A：裸跑 | B：加上 Prompt |
| --- | --- | --- |
| 结构 | 六段摘要 | 同左 + MAIN 契约措辞 |
| 约束 | REPORT-ONLY | 同左 |
| 胡编 | 未声称已改代码 | Codex 标明合成进度 |
| 可执行性 | 可继续跑任务 | 同左，模板更稳 |
