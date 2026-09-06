---
title: 工作上下文精简：先裁剪再 Code Review
category: agent-coding
source: https://x.com/goan999999/status/2090280910717689929
ran_on: herdr prompt-lab / prompt-agy
ran_at: 2026-09-04
model: gemini-3.8-flash-high (agy)
input_status: rebuilt_from_ab_excerpt
excerpt_a: runs/ab/batch-b/ctx-A.md
excerpt_b: runs/ab/batch-b/ctx-B.md
gate_complete: true
gate_traceable: true
gate_safe: true
gate_one_pass: true
---

# 工作上下文精简：先裁剪再 Code Review

过长 AGENTS 先删重复/无关工具，保留目标与验收，再做审查。

## 原始问题

过长 AGENTS.md + 只做 util.js Code Review 时，模型常直接出 findings。这次测是否先精简上下文。

## 给模型的输入

这段输入根据 A/B 摘录重建，不是官方逐字原文。

```text
当前有一份过长 AGENTS.md（含重复/冲突规则与 Figma·DB·Browser 等无关工具说明），任务是对 src/util.js 做 Code Review。请先优化工作上下文再审查；不要真删 vault 文件，建议清单与统计即可。
```

## 复制这条 Prompt

把上面的输入和下面这段 Prompt 放进同一条消息，再发送。

```text
请优化当前 Codex 工作上下文，删除重复、冲突、低价值以及与当前任务无关的指令，只保留当前目标、核心约束、验收标准和必要工具；同时检查 agent 当前可调用的工具，移除本任务不会使用的工具。优化前后分别统计 prompt 长度、工具数量和保留的核心信息，确保减少上下文占用的同时不丢失关键执行要求。
```

## 跑完会差在哪

### A：裸跑

A 仅中性「请完成任务」。

> # 代码审查报告：src/util.js (Baseline A)
>
> **工作目录 (CWD)**：`/Users/zouyanjian/Documents/obsidian/obsidian-2/20_Projects/X提示词收集/runs/scratch-batch-b/ctx-slim`  
> **审查目标**：`src/util.js`  
>
> ---
>
> ## 一、被审查源码现场
> ```javascript
> // src/util.js:1
> function add(a,b){return a+b}
> ```
>
> ---
> …

### B：加上 Prompt

> # 工作上下文优化与指令瘦身报告 (Treatment B)
>
> **工作目录 (CWD)**：`/Users/zouyanjian/Documents/obsidian/obsidian-2/20_Projects/X提示词收集/runs/scratch-batch-b/ctx-slim`  
> **当前核心任务**：针对 `src/util.js` 的纯代码审查（Code Review only）。
>
> ---
>
> ## 一、优化前后对比统计 (Before / After Stats)
>
> | 统计指标 | 优化前 (Before) | 优化后 (After) | 优化效果 |
> …

A 直接 Code Review；B 先给出前后统计、保留目标/约束/验收并剔除无关工具。

## 什么时候别用

上下文已经很短、或必须保留全部工具说明时，不必强行瘦身。

## 人要检查什么

关键验收是否被误删；统计是否基于可见 AGENTS。

## 四维评测

| 维度 | A：裸跑 | B：加上 Prompt |
| --- | --- | --- |
| 结构 | 直接做 Code Review 出 findings | 先裁剪：前后统计 + 保留目标/约束/验收 + 剔除无关工具 |
| 约束 | 未优化上下文 | 点名删重复/冲突/无关工具；保留审查关键要求 |
| 胡编 | 无 | 统计基于可见 AGENTS |
| 可执行性 | 审查可用 | 精简后 AGENTS 可直接换上 |
