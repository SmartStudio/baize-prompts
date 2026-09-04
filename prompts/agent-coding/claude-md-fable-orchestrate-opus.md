---
title: 主 agent 只编排，别闷头改
category: agent-coding
source: https://x.com/dotey/status/2088099630005264748
ran_on: prompt-lab / Codex+agy
ran_at: 2026-09-04
model: agy gemini-3.8-flash-high high
input_status: rebuilt_from_ab_excerpt
excerpt_a: runs/ab/2026-09-04-fable-agy-A.md
excerpt_b: runs/ab/2026-09-04-fable-agy-B.md
gate_complete: true
gate_traceable: true
gate_safe: true
gate_one_pass: true
---

# 主 agent 只编排，别闷头改

任务做完了，不等于角色守住了。这条 Prompt 把主 agent 留在分析和验收位。

## 原始问题

主 agent 收到一句小改动，很容易自己读文件、改 README、再宣布完成。测试想看的是：加上 Prompt 后，它会不会停下直接实现，把工作交给 Opus subagent。

## 给模型的输入

这段输入根据 A/B 摘录重建，不是官方逐字原文。现存记录只写了「给 README 加一句简介」，没有保存简介内容和仓库上下文。

```text
请给当前项目的 README 加一句简介。
```

## 复制这条 Prompt

把上面的输入和下面这段 Prompt 放进同一条消息，再发送。

```text
注意你的主要任务是分析、编排和验证，具体任务尽可能交给 subagent（Opus）去执行。当主 agent 是 Fable 5 时尤其如此：自己只做需求澄清、方案拆解、任务分发和结果验收，实现类工作（读大量代码、写代码、跑测试、批量修改）一律用 Agent 工具派给 Opus subagent 执行。
```

## 跑完会差在哪

完整运行文件当前不在工作区。下面照录 raw 里的真实评测摘录，不冒充模型完整输出。

### A：裸跑

A 使用中性「请完成任务」。

> 直接改完 README 并汇报
>
> **越权实现**（自己改文件）

### B：加上 Prompt

> 声明编排者 + 无 subagent 诚实说明 + 派发清单
>
> 遵守「不直接实现」；未改 README

A 把 README 改完了，却越过了主 agent 的角色边界。B 没碰文件，先说明当前能不能调用 subagent，再给派发清单。摘录内没看到新增事实。

## 什么时候别用

没有可用 subagent，或任务只有一两处机械修改时，强制编排可能只会多一层转述。安全、架构和跨任务取舍也不能直接甩给实现 agent。

## 人要检查什么

确认任务真的适合委派，派发清单写清文件、约束和验收条件。真实仓库是否允许 subagent 写入，也要由人点头。

## 四维评测

| 维度 | A：裸跑 | B：加上 Prompt |
| --- | --- | --- |
| 结构 | 直接改完 README 并汇报 | 先说明角色和能力，再列派发清单 |
| 约束 | 主 agent 越权实现 | 没直接改 README |
| 胡编 | 摘录内未见新增事实 | 摘录内未见新增事实 |
| 可执行性 | 任务完成，但不符合编排要求 | 可派发，仍要等真实 subagent |
