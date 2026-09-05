---
title: 先调研再实现：确认前不写代码
category: agent-coding
source: https://x.com/SevenXL77/status/2088566153991835910
ran_on: herdr prompt-lab / prompt-agy
ran_at: 2026-09-04
model: gemini-3.8-flash-high (agy)
input_status: rebuilt_from_ab_excerpt
excerpt_a: runs/ab/batch-b/gh-research-A.md
excerpt_b: runs/ab/batch-b/gh-research-B.md
gate_complete: true
gate_traceable: true
gate_safe: true
gate_one_pass: true
---

# 先调研再实现：确认前不写代码

新项目先调研同类开源与选型，确认前停在方案阶段。

## 原始问题

本地 Markdown 待办 CLI 需求下，模型常直接给实现向设计。这次测确认前是否不写代码。

## 给模型的输入

这段输入根据 A/B 摘录重建，不是官方逐字原文。

```text
我要开发一个本地 Markdown 待办 CLI（无云、单文件存储）。暂时不要创建文件，也不要输出代码。先调研再给选型/架构/MVP/顺序，等确认后再实现。
```

## 复制这条 Prompt

把上面的输入和下面这段 Prompt 放进同一条消息，再发送。

```text
我要开发一个 XXX。暂时不要创建文件，也不要输出代码。先在 GitHub 调研同类开源项目，筛选出最有参考价值的方案。分析它们解决了什么问题、采用什么架构、依赖哪些技术、目前是否活跃，以及有哪些设计值得复用或避开。最后结合我的需求，给出技术选型、系统架构、MVP 范围和开发顺序。得到我的确认后，再进入实现阶段。
```

## 跑完会差在哪

### A：裸跑

A 仅中性「请完成任务」。夹具把 XXX 换成本地 Markdown 待办 CLI。

> # 本地 Markdown 待办 CLI 构建方案（无云·单文件存储）
>
> ---
>
> ## 一、方案概述与设计原则
> 本方案遵循 **KISS 原则**，旨在打造一个完全运行在本地、无任何外部云端依赖、直接读写单一 Markdown 文件的轻量命令行待办工具（CLI）。
>
> ### 核心特性
> 1. **纯单文件存储**：默认存储于当前目录下的 `TODO.md`（或全局配置文件 `~/.todo.md`）。
> 2. **原生 Markdown 兼容**：使用标准 GitHub Flavored Markdown 复选框语法（`- [ ]` 与 `- [x]`），不仅 CLI 可读写，在 Obsidian、VSCode 或任意文本编辑器中亦可无缝打开和勾选。
> …

### B：加上 Prompt

> # 本地 Markdown 待办 CLI（无云·单文件存储）开源调研与方案规划
>
> > **阶段说明**：当前阶段仅进行同类开源方案调研、需求分析与架构规划。**未输出任何实现代码，亦未在项目中生成代码文件**，等待您的确认后再启动具体实现。
>
> ---
>
> ## 一、GitHub 知名同类开源项目调研与借鉴分析
>
> 基于知名公开开源项目的架构范式与实践经验，针对“纯本地文本待办 CLI”领域，有以下几个典型方案可供深度参考：
>
> ### 1. `todo.txt-cli`（Gina Trapani 经典作品）
> * **定位与架构**：基于纯文本行格式（`todo.txt`）的 Bash 脚本管理工具。
> …

A 直接给方案与命令表偏实现；B 调研同类后选型并明确等确认，未输出实现代码。

## 什么时候别用

需求已确认、只要立刻写代码时不要再卡调研门。

## 人要检查什么

有无伪造 star/克隆；是否真的停在确认前。

## 四维评测

| 维度 | A：裸跑 | B：加上 Prompt |
| --- | --- | --- |
| 结构 | 直接给方案 + 命令表 + 偏实现向设计 | 调研同类 → 选型 → MVP 顺序 → 等确认 |
| 约束 | 未强制「确认前停」 | 未输出实现代码；明确等待确认 |
| 胡编 | 无假克隆声称 | 调研基于公开范式，未伪造 star/commit |
| 可执行性 | 可直接开写 | 可确认后开写 |
