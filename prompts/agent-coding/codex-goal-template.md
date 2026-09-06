---
title: Goal 通用模板：先落 GOAL.md 再交付可接手结果
category: agent-coding
source: https://x.com/aronhouyu/status/2067415348224422219
ran_on: herdr prompt-lab / prompt-agy
ran_at: 2026-09-04
model: gemini-3.8-flash-high (agy)
input_status: rebuilt_from_ab_excerpt
excerpt_a: runs/ab/batch-b/goal-A.md
excerpt_b: runs/ab/batch-b/goal-B.md
gate_complete: true
gate_traceable: true
gate_safe: true
gate_one_pass: true
---

# Goal 通用模板：先落 GOAL.md 再交付可接手结果

把「写出能跑」升成 Goal 可验收交付，并做 Done 自检。

## 原始问题

stdin 字符数 CLI 任务下，模型常直接实现。这次测是否先建 Goal 文件并验收。

## 给模型的输入

这段输入根据 A/B 摘录重建，不是官方逐字原文。

```text
Build a tiny Python CLI that counts characters of one stdin line. Add a test if you want.
（跑 B 时把 Goal 占位填成上述任务 + 验收标准后执行模板。）
```

## 复制这条 Prompt

把上面的输入和下面这段 Prompt 放进同一条消息，再发送。

```text
Goal: {在这里完整描述你的任务 + 最终要达到的效果 + 验收标准}

你是 Codex 环境下的 Senior Staff Engineer。

执行规则：
1. 首先在项目中创建/更新一个清晰的 Goal 文件（推荐 GOAL.md 或当前任务对应的进度文件），把任务、成功标准、架构思路完整记录下来。
2. 每完成一个有意义的步骤后，必须：
   - 进行真实端到端验证（包括必要时的 browser / computer use）
   - 把当前进度、遇到的问题、决策理由更新到进度文件里
   - 自我 review 是否符合 Goal
3. 持续推进，直到架构、实现、测试、文档全部达到 production-grade 标准。
4. 最后必须做一次完整的 review pass。

Done 的定义：不是“能跑起来”，而是“一个真实的用户/开发者可以直接接手使用，没有明显风险”。
```

## 跑完会差在哪

### A：裸跑

A 仅中性「请完成任务」。

> # 字符计数 CLI 构建报告 (Baseline A)
>
> **工作目录 (CWD)**：`/Users/zouyanjian/Documents/obsidian/obsidian-2/20_Projects/X提示词收集/runs/scratch-batch-b/goal`
>
> ---
>
> ## 一、任务与实现概述
> 根据指令，我们构建了一个极简的 Python 命令行工具，用于统计从标准输入 (`stdin`) 传入的单行字符数：
>
> ### 1. 核心代码 (`charcount.py`)
> - 从 `sys.stdin.readline()` 读取单行输入。
> …

### B：加上 Prompt

> # 目标驱动交付与工程 Review 报告 (Treatment B)
>
> **工作目录 (CWD)**：`/Users/zouyanjian/Documents/obsidian/obsidian-2/20_Projects/X提示词收集/runs/scratch-batch-b/goal`
>
> ---
>
> ## 一、交付成果概述 (Delivery Summary)
> 以 Senior Staff Engineer 标准完成目标驱动开发，全部成果已完成落盘与端到端真实测试验证：
>
> 1. **GOAL 文件已建立 (`GOAL.md`)**：
>    - 记录完整任务目标、成功标准、架构解耦思路、端到端测试记录与最终 Self-Review。
> …

A 直接实现 CLI+测试；B 先落 GOAL.md，再实现+README+pytest，并做 Done 自检。

## 什么时候别用

一次性抛出小修、不需要进度文件与接手标准时，不必套整模板。

## 人要检查什么

GOAL.md 是否含成功标准；验证是否真实跑过。

## 四维评测

| 维度 | A：裸跑 | B：加上 Prompt |
| --- | --- | --- |
| 结构 | 直接实现 CLI+测试 | 先落 GOAL.md，再实现+README+pytest，并做 Done 自检 |
| 约束 | 无强制 Goal/进度文件 | 命中 Goal 文件 + 验收项；宣称可接手 |
| 胡编 | 无 | 无 |
| 可执行性 | 能跑 | 能跑且目标可审计 |
