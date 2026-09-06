---
title: DEV_STATE 存档：可交接状态快照，不闷头继续写
category: agent-coding
source: https://x.com/SevenXL77/status/2088414339271111003
ran_on: herdr prompt-lab / prompt-agy
ran_at: 2026-09-04
model: gemini-3.8-flash-high (agy)
input_status: rebuilt_from_ab_excerpt
excerpt_a: runs/ab/batch-b/dev-A.md
excerpt_b: runs/ab/batch-b/dev-B.md
gate_complete: true
gate_traceable: true
gate_safe: true
gate_one_pass: true
---

# DEV_STATE 存档：可交接状态快照，不闷头继续写

把当前进度锁进 DEV_STATE.md，方便空上下文续跑。

## 原始问题

scratch git toy 续开发时，模型常直接改业务代码。这次测是否写出可交接状态文件。

## 给模型的输入

这段输入根据 A/B 摘录重建，不是官方逐字原文。

```text
在 scratch git toy 项目中继续工作：检查代码与 Git，创建/更新根目录 DEV_STATE.md；仅记录已确认信息，不写密钥、不贴大段代码。
```

## 复制这条 Prompt

把上面的输入和下面这段 Prompt 放进同一条消息，再发送。

```text
根据当前项目实际状态，检查代码、Git diff、现有 DEV_STATE.md 和测试结果，创建或更新项目根目录下的 DEV_STATE.md。仅记录已确认的信息，不猜测或虚构；用一段简洁、连贯的文字概括当前目标、已完成内容、关键决策、核心文件、测试结果、已知问题、失败方案和下一步任务，删除无效讨论、重复信息和过时内容，不粘贴代码，不记录密码、Token、API Key、私钥、Cookie 等敏感信息，重点让下一次开发能够快速了解“当前做到哪里、为什么这样做、哪些已验证、哪些未完成以及下一步做什么。”

续开发启动词：

读取 DEV_STATE.md文档，继续按照文档中的项目进度进行开发
```

## 跑完会差在哪

### A：裸跑

A 仅中性「请完成任务」。

> # Toy 项目续写与迭代报告 (Baseline A)
>
> **工作目录 (CWD)**：`/Users/zouyanjian/Documents/obsidian/obsidian-2/20_Projects/X提示词收集/runs/scratch-batch-b/devstate`
>
> ---
>
> ## 一、本次迭代工作总结
> 根据项目初始的 `todo.txt`（包含 `add tests` 和 `add CLI flags` 两个未决待办），我们完成了以下功能演进：
>
> ### 1. 核心代码改造 (`main.py`)
> - 引入 Python 标准库 `argparse`，添加 `--name` 命令行参数支持（默认打招呼对象为 `"world"`）。
> …

### B：加上 Prompt

> # 开发状态报告与续开发规划 (Treatment B)
>
> 根据指令，已在当前工作区成功生成标准的 8 节 `DEV_STATE.md`。整个过程**未修改任何业务代码**（`changed_business_code=no`），且**严禁写入任何密钥或 Token**（`secrets=no`）。
>
> ---
>
> ## 一、`DEV_STATE.md` 完整内容归档
>
> ```markdown
> # 开发状态跟踪文档 (DEV_STATE.md)
>
> ### 1. 目标 (Objective)
> 构建并演进轻量级本地 Python 命令行工具（toy 项目），提供简洁的欢迎语输出、标准参数解析以及完备的自动化测试体系。
> …

A 推进实现（含测试）但状态文件弱；B 写出 DEV_STATE.md 八段信息并基于该文件规划下一步，声明未改业务源码。

## 什么时候别用

需要立刻改业务代码、且不需要跨会话交接时，不必强制写 DEV_STATE。

## 人要检查什么

八段是否齐全；有无密钥/大段代码；是否误改业务文件。

## 四维评测

| 维度 | A：裸跑 | B：加上 Prompt |
| --- | --- | --- |
| 结构 | 推进实现 + 简短状态叙述 | 写出根目录 DEV_STATE.md + 续开发下一步 |
| 约束 | 未强制「只记状态」 | 覆盖目标/完成/决策/文件/测试/问题/失败/下一步；无密钥 |
| 胡编 | 测试「全绿」需对照文件 | 基于仓库可见事实 |
| 可执行性 | 代码前进但状态文件弱 | 状态文件可给空上下文续跑 |
