---
title: 任务契约模板：五段收口 + 验证诚实声明
category: agent-coding
source: https://x.com/Dicklong1999/status/2095481543884206256
ran_on: herdr prompt-lab / prompt-agy
ran_at: 2026-09-04
model: gemini-3.8-flash-high (agy)
input_status: rebuilt_from_ab_excerpt
excerpt_a: runs/ab/batch-b/contract-A.md
excerpt_b: runs/ab/batch-b/contract-B.md
gate_complete: true
gate_traceable: true
gate_safe: true
gate_one_pass: true
---

# 任务契约模板：五段收口 + 验证诚实声明

修 bug 时按契约填空，最后五段说清根因、改动与验证。

## 原始问题

auth/login.js 空指针白屏时，模型修完就汇报。这次测契约五段与「不可验证要说实话」。

## 给模型的输入

这段输入根据 A/B 摘录重建，不是官方逐字原文。

```text
Fix the null deref bug in auth/login.js that causes white screen after login.
限制：只改必要部分；不要改数据库结构。把契约模板占位填成该 bug 后执行。
```

## 复制这条 Prompt

把上面的输入和下面这段 Prompt 放进同一条消息，再发送。

```text

```

## 跑完会差在哪

### A：裸跑

A 仅中性「请完成任务」。

> # Auth 模块空指针异常修复报告 (Baseline A)
>
> **工作目录 (CWD)**：`/Users/zouyanjian/Documents/obsidian/obsidian-2/20_Projects/X提示词收集/runs/scratch-batch-b/contract`
>
> ---
>
> ## 一、问题原因分析
> 原 `auth/login.js` 代码实现如下：
> ```javascript
> function login(user) {
>   return user.profile.name.toUpperCase();
> }
> ```
> 当接口返回的 `user` 为 `null` / `undefined`，或者登录用户缺少 `profile` 属性或未设置 `name` 时，直接链式访问属性会导致未捕获的 `TypeError: Cannot read properties of undefined`，在前端运行时触发未捕获异常导致页面白屏。
> …

### B：加上 Prompt

> # Auth 模块空指针缺陷修复报告 (Treatment B)
>
> ---
>
> ### 1. 根因是什么
> 在 `auth/login.js` 中，原实现直接通过链式调用 `user.profile.name.toUpperCase()` 处理入参。当 `user` 为 `null`、`undefined`，或者 `user` 缺少 `profile` / `name` 属性时，JavaScript 引擎会直接抛出未捕获的运行时异常 `TypeError: Cannot read properties of undefined`。该未捕获异常导致前端调用栈崩溃并阻断渲染流程，最终表现为页面直接白屏。
> …

A 修完即汇报；B 五段齐全，只改 login.js，诚实说明验证方式（无假 lint 已过）。

## 什么时候别用

无关的大重构或「先随便修一下看看」探索时，别假装契约已确认。

## 人要检查什么

diff 是否干净；五段是否齐；验证项不可执行时是否如实说明。

## 四维评测

| 维度 | A：裸跑 | B：加上 Prompt |
| --- | --- | --- |
| 结构 | 修完即汇报 | 最终五段（根因/文件/作用/验证/未处理）齐全 |
| 约束 | 可能顺手扩 scope | 只改 login.js；无 DB；诚实说明验证 |
| 胡编 | 无 | 无假「lint 已过」 |
| 可执行性 | bug 已修 | bug 已修 + 契约输出可审 |
