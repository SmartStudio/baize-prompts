# 四道闸

要出厂，四条全是。一条否，回 Inbox。

| # | 闸 | 怎样算过 |
| --- | --- | --- |
| 1 | 写全了 | 目标、约束、输出格式都有。缺一段就回去。 |
| 2 | 说得清从哪来 | frontmatter 里有来源 URL 或笔记路径。 |
| 3 | 不脏 | 没客户名、没密钥、没不该公开的数据。图 / 视频提示词不收。 |
| 4 | 跑通过 | 在 Cursor / Claude Code / Codex（或同等）上真的跑过一次，有日期和结果。 |

## 出厂长这样

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

## 干嘛用

## 什么时候别用

## 人必须点头的事

没点头之前，别用这条去放大自动化。

## 原文

## 评测

- 在哪跑的：
- 结果：
```

要升格成 Skill：四闸还在，外加「隔周再跑同一件事，验收标准没变」。只放 `skills/<名字>/SKILL.md`。

## 别往这儿扔

- Inbox「提示词待验收」
- `needs-human` / `incomplete` / `pending-run`
- 图、视频提示词
- 用户没点过「入库」或「升格 Skill」的东西
