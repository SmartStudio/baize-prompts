# 四道闸

要出厂，四条全过。一条挂，回 Inbox，别硬塞。

| # | 闸 | 过关长啥样 |
| --- | --- | --- |
| 1 | 写全了吗 | 目标、约束、输出格式都有。少一段就回去补。 |
| 2 | 哪来的 | frontmatter 里写清来源 URL 或笔记路径。 |
| 3 | 脏不脏 | 没客户名、没密钥、没不该公开的东西。图 / 视频提示词直接拒。 |
| 4 | 真跑过吗 | 在 Cursor / Claude Code / Codex（差不多的也行）上跑通过，有日期 + 结果。 |

## 出厂模板

`prompts/<类>/<名字>.md`：

```md
---
title:
category: agent-coding | product-strategy | research-pkm | marketing-sales | review
source:
ran_on:
ran_at:
gate_complete: true
gate_traceable: true
gate_safe: true
gate_one_pass: true
---

## 干啥

## 别啥时候用

## 人必须点头啥

没点头就别拿去放大自动化。

## 原文

## 评测

- 在哪跑的：
- 结果：
```

升 Skill：四闸还在，外加「隔一周再跑同一件事，标准没飘」。只放 `skills/<名字>/SKILL.md`。

## 别扔进来

- Inbox「提示词待验收」
- `needs-human` / `incomplete` / `pending-run`
- 图、视频提示词
- 人没点过「入库」或「升格 Skill」的半成品


## 给人看的对照（出厂必带）

评测记录里除了四闸，还要有：

1. 同一 fixture 的 **A 裸跑摘录** 和 **B 过闸摘录**（各至少两句，别只写「有效」）
2. 一张四维表：结构 / 约束 / 胡编 / 可执行性
3. 一句话点出「差在哪」

第一屏和 [`examples/ab-showcase.md`](examples/ab-showcase.md) 靠这些摘录活着。没摘录 = 看的人没感觉 = 不出厂。
