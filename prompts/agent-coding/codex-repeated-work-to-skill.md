---
title: 重复工作沉淀 Skill：先列候选，确认前不改文件
category: agent-coding
source: https://x.com/Saccc_c/status/2085275196412547133
ran_on: herdr prompt-lab / prompt-agy
ran_at: 2026-09-04
model: gemini-3.8-flash-high (agy)
input_status: rebuilt_from_ab_excerpt
excerpt_a: runs/ab/batch-b/skill-A.md
excerpt_b: runs/ab/batch-b/skill-B.md
gate_complete: true
gate_traceable: true
gate_safe: true
gate_one_pass: true
---

# 重复工作沉淀 Skill：先列候选，确认前不改文件

从会话摘要提炼 Skill 时，先出候选清单，别直接落盘。

## 原始问题

给假会话摘要后，模型易直接展开 Skill 正文。这次测是否先候选、未改文件。

## 给模型的输入

这段输入根据 A/B 摘录重建，不是官方逐字原文。

```text
根据下列假会话摘要，找出适合沉淀为 Skill 的候选项；先输出清单，不要直接修改文件。
1) 反复手工写 DEV_STATE.md 交接
2) 每次 PR 前都手跑同一套 lint+test 口令
3) 三轮都在帮用户把「模糊需求」拆成验收清单
```

## 复制这条 Prompt

把上面的输入和下面这段 Prompt 放进同一条消息，再发送。

```text
检查我最近 30 天的 Codex 会话、Memories、Chronicle，以及已有的 Skills、Agents 和 Automations。

找出至少重复出现两次、耗时、容易出错、需要大量上下文的人工工作。

对每个候选项给出：实际证据和日期、出现频率、适合做成 Skill / Agent / Automation，或者暂时跳过、预计能节省什么。

先输出候选清单，不要直接修改文件。只保留高置信度、输入稳定、流程可重复、结果可验收的任务
```

## 跑完会差在哪

### A：裸跑

A 仅中性「请完成任务」。

> # 会话工作流提炼：可复用 Skills (技能) 方案设计
>
> 根据提供的三项高频会话场景，我们将重复性的人工动作提炼为 3 个标准化的自动化 Agent 技能（Skills），以极大降低认知负荷与手工操作成本。
>
> ---
>
> ## 技能一：`dev-state-handoff`（开发状态与会话交接自动化）
>
> ### 1. 提炼背景
> 解决会话上下文过长、多轮对话后需手工整理 `DEV_STATE.md` 造成的时间浪费与遗漏风险。
>
> ### 2. 触发时机
> - 用户输入 `/handoff`、`准备交接`，或会话上下文即将耗尽需要新建会话时。
> …

### B：加上 Prompt

> # 适合沉淀为 Skill 的候选清单
>
> > **阶段声明**：当前仅列出 Skill 候选定义（包含**名称**、**触发场景**与**一句话职责**）。**尚未创建或修改任何 Skill 文件**，等待您的确认与授权后再进行落盘。
>
> ---
>
> ### 候选 1：`dev-state-handoff`
> * **名称**：`dev-state-handoff`（开发状态与会话交接助手）
> * **触发场景**：当会话上下文过长、开发者准备暂停工作，或需跨窗口/跨会话安全交接开发进度时。
> * **一句话职责**：只读审计当前 Git 现场与未提交改动，自动生成结构化任务进度、遗留问题清单及可直接粘贴的新会话启动提示词并写入 `DEV_STATE.md`。
> …

A 偏直接展开 Skill 规范细节；B 只输出 3 个候选（名+场景+职责）并等确认，未改文件。

## 什么时候别用

已授权落盘、只要生成完整 Skill 文件时，不要再只停在候选。

## 人要检查什么

候选项是否有证据；有无擅自写文件/密钥。

## 四维评测

| 维度 | A：裸跑 | B：加上 Prompt |
| --- | --- | --- |
| 结构 | 偏直接展开 Skill 正文/规范细节 | 仅输出 3 个候选并等确认 |
| 约束 | 易越过「先列清单」 | 先候选、未改文件 |
| 胡编 | 无假会话日期伪造 | 基于夹具摘要，无密钥 |
| 可执行性 | 可落盘但跳过确认 | 确认后可落盘 |
