---
title: 领域-AI代理共享权限六项安全审计-Michael_Fenech_
category: eval-review
source: https://x.com/Michael_Fenech_/status/2110027278864552008
ran_on: prompt-lab / Codex
ran_at: 2026-10-20
model: not_recorded
input_status: not_recorded
excerpt_a: 不适用（仅 Codex）
excerpt_b: Codex 单次运行
ab: 仅 Codex
image: 不适用
gate_complete: true
gate_traceable: true
gate_safe: true
gate_one_pass: codex_only
---

# 领域-AI代理共享权限六项安全审计-Michael_Fenech_

企业 AI 落地治理：6 项审计（连接账号/敏感数据/代理权限/审批规则/活动追踪/闲置权限）、按严重度排序、已核实与未核实分开、未经批准不改权限。

## 原始问题

企业 AI 落地治理：6 项审计（连接账号/敏感数据/代理权限/审批规则/活动追踪/闲置权限）、按严重度排序、已核实与未核实分开、未经批准不改权限。

## 给模型的输入

跑台使用合成输入，原始输入未公开记录（not_recorded）。用你自己的真实材料替换 Prompt 里的占位内容即可。

## 复制这条 Prompt

把你的输入和下面这段 Prompt（源帖原文）放进同一条消息，再发送。

```text
"Audit my Grok Bot setup for shared-access and security risks.

Check these 6 areas:

1 - Connected accounts: Identify connected apps, active browser sessions and available credentials. Flag anything unnecessary or overly permissive.

2 - Sensitive information: Find accessible customer data, financial records, confidential documents and sensitive files that shouldn't remain in shared storage.

3 - Agent access: Review my agents and their responsibilities. Identify which shared resources they could access but don't need for their jobs.

4 - Approval rules: Check which actions can happen without my approval, especially sending emails, making purchases, deleting files, publishing content and changing permissions.

5 - Activity tracking: Determine whether I can identify which agent performed an important action, what changed and whether I could investigate a problem.

6 - Unused access: Identify old connections, logged-in sessions, unused credentials and files that should be removed.

For every issue, explain the risk and recommend a specific fix.

Separate verified findings from anything you couldn't inspect.

Rank the issues by severity and give me the 5 most important actions to take.

Do not change permissions, disconnect accounts, delete files or revoke access without my approval."
```

## 跑完会差在哪

### A：裸跑

仅 Codex：本条没有跑 A 臂，没有裸跑对照。

### B：加上 Prompt

> 只读 fixture 合成权限导出，按六域核对、区分已验证与无法检查部分，给严重度排序与五项行动，未改任何权限

差别：只有 B 的单次 Codex 结果，按 2026-10-19 起的规则「Codex 单次通过即收」出厂，未做 A/B 对照。

## 什么时候别用

需要逐字可复核的 A/B 证据，或涉及真实客户数据、生产系统时，先自己补一轮对照再用。

## 人要检查什么

1. 输出里的事实、数字有没有新编。
2. 是否按 Prompt 的格式和约束交付。
3. 涉及对外发送或生产动作时，人点头再执行。

## 四维评测

| 维度 | A：裸跑 | B：加上 Prompt |
| --- | --- | --- |
| 结构 | 未跑（仅 Codex） | 见上方 B 结果 |
| 约束 | 未跑（仅 Codex） | 人判通过 |
| 胡编 | 未跑（仅 Codex） | 人判未发现编造 |
| 可执行性 | 未跑（仅 Codex） | 可直接复制使用 |
