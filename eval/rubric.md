# 评测闸门

一条提示词要出厂，四条必须同时为是。任何一条为否，留在 Inbox，不进本仓。

| # | 闸门 | 通过标准 |
| --- | --- | --- |
| 1 | 完整 | 写清目标、约束、输出格式。缺一段就不完整。 |
| 2 | 可溯源 | 能指到来源（URL 或内部笔记路径）。来源 URL 放 frontmatter。 |
| 3 | 安全 | 无客户名、密钥、未授权数据。图 / 视频提示词排除。 |
| 4 | 至少一通 | 在真实 Agent（Cursor / Claude Code / Codex / 同等）上跑通过一次，有日期和结果。 |

## 出厂条目结构

`prompts/<cat>/<slug>.md`：

```md
---
title:
category: agent-coding | product-strategy | research-pkm | marketing-sales | review
source:
ran_on:            # 哪一个 Agent
ran_at:            # 跑通日期
gate_complete: true
gate_traceable: true
gate_safe: true
gate_one_pass: true
---

## 用途

## 何时不用

## 边界

人必须批准什么。没签之前不要用这条去放大自动化。

## 原文

## 评测记录

- 跑通环境：
- 结果：
```

升格 Skill：上述四闸仍在，另加「同一任务隔周再跑，验收标准不变」。只放 `skills/<name>/SKILL.md`。

## 不进本仓

- `提示词待验收` Inbox
- `needs-human` / `incomplete` / `pending-run`
- 图、视频提示词
- 用户未点「入库」或「升格 Skill」的条目
