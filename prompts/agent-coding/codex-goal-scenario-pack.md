---
title: Goal 扩展包 #5：高级调试三件套 + DEBUG.md
category: agent-coding
source: https://x.com/aronhouyu/status/2067415420991426880
ran_on: herdr prompt-lab / prompt-agy
ran_at: 2026-09-04
model: gemini-3.8-flash-high (agy)
input_status: rebuilt_from_ab_excerpt
excerpt_a: runs/ab/batch-b/dbg-A.md
excerpt_b: runs/ab/batch-b/dbg-B.md
gate_complete: true
gate_traceable: true
gate_safe: true
gate_one_pass: true
---

# Goal 扩展包 #5：高级调试三件套 + DEBUG.md

高级调试场景：根因 / 方案 / 可应用代码+验证，并写入调试文档。

## 原始问题

本批只测扩展包中的「5）高级调试」。scratch 里 login(null) 白屏，看是否先分析再修并落 DEBUG.md。

## 给模型的输入

这段输入根据 A/B 摘录重建，不是官方逐字原文。

```text
Fix the bug that login(null) whitescreens.
（仅使用扩展包 #5 高级调试工程师模板；#2–#4 本批未跑。）
```

## 复制这条 Prompt

把上面的输入和下面这段 Prompt 放进同一条消息，再发送。

```text
Act as a Senior Debugging Engineer in Codex environment.

任务：定位并修复生产环境中的 bug。

执行流程：
1. 仔细阅读相关代码，逐步推理
2. 找到根本原因（root cause）
3. 设计健壮的修复方案（考虑 edge cases 和性能）
4. 实现修复
5. 验证修复有效性

最终输出必须包含三部分：
- 根本原因分析
- 修复方案说明
- 可直接应用的 production-ready 代码 + 验证方法

把分析过程和决策记录到调试文档中。
```

## 跑完会差在哪

### A：裸跑

A 仅中性「请完成任务」。

> # Login(null) 白屏缺陷修复报告 (Baseline A)
>
> **工作目录 (CWD)**：`/Users/zouyanjian/Documents/obsidian/obsidian-2/20_Projects/X提示词收集/runs/scratch-batch-b/debug-login`
>
> ---
>
> ## 一、缺陷分析
> 原实现代码中：
> ```javascript
> function login(user) {
>   return user.profile.name.toUpperCase();
> }
> ```
> 当传入 `login(null)` 或未初始化的用户信息时，尝试在 `null` 上读取 `.profile` 会触发 `TypeError: Cannot read properties of null`。在前端 SPA 架构中，该异常未被局部捕获，向上冒泡导致 React/Vue 渲染树整体卸载，从而呈现为页面白屏。
> …

### B：加上 Prompt

> # 高级生产环境缺陷调试与修复总结 (Treatment B)
>
> **工作目录 (CWD)**：`/Users/zouyanjian/Documents/obsidian/obsidian-2/20_Projects/X提示词收集/runs/scratch-batch-b/debug-login`  
> **调试日志存档**：`DEBUG.md` 已在当前工作区生成。
>
> ---
>
> ## 一、根本原因分析 (Root Cause Analysis)
> 1. **多层解引用无防御**：原代码 `user.profile.name.toUpperCase()` 在缺少对象存在性校验的前提下执行链式属性寻址。
> …

A 分析+修复+简短验证；B 根因/方案/可应用代码+验证三件套，并落盘 DEBUG.md。

## 什么时候别用

包内 #2–#4 场景本批未夹具验证，入库时勿当作已全测。无关大重构不要借调试名义做。

## 人要检查什么

是否先分析再改；DEBUG.md 是否可接力；有无大范围无关重构。

## 四维评测

| 维度 | A：裸跑 | B：加上 Prompt |
| --- | --- | --- |
| 结构 | 分析+修复+简短验证 | 根因/方案/可应用代码+验证三件套 + 落盘 DEBUG.md |
| 约束 | 无强制调试文档 | 先分析再改；无大范围无关重构 |
| 胡编 | 无 | 无 |
| 可执行性 | bug 已修 | bug 已修且决策可接力 |
