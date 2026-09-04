---
title: Codex 置信度闭环
category: agent-coding
source: https://x.com/cjzafir/status/2052110266566107321
ran_on: prompt-lab / Codex+agy
ran_at: 2026-09-04
gate_complete: true
gate_traceable: true
gate_safe: true
gate_one_pass: true
---

## 用途

- 目标：在给出策略后强制自检，直到声明事实层面 100% 有把握。
- 约束：若未 100% 有把握，必须找出漏洞、提出修复，并循环；不得在未闭环时停。
- 输出格式：原文未规定文件结构；fixture 要求列出漏洞清单 → 修复 → 是否仍有漏洞，直到宣称 100% 或如实说仍不确定。

## 何时不用

缺目标/约束/格式时不要用；图视频任务不要用；未签边界不要放大自动化。

## 边界

人必须批准：是否入库到生产工作流、是否写入真实仓库/会话。评测 fixture 不得指向真实 vault 或生产密钥。

## 原文

```
Are you 100% confident in this strategy? If not, find all possible loopholes, suggest proper fixes and run this loop until you are factually 100% confident in the new startegy
```

## 评测记录

- 跑通环境：prompt-lab / Codex+agy
- 跑通日期：2026-09-04
- 闸门：完整 / 可溯源 / 安全 / 至少一通 = 全是
- A/B 对照摘要：

---
type: ab-compare
item: Codex置信度闭环
model: agy gemini-3.8-flash-high
---

# 对照：Codex 置信度闭环

## A/B 对照（agy · gemini-3.8-flash-high · high）

同一 fixture（`rm -rf /` 策略）。A=中性「请完成任务」；B=目标提示词（100% 置信闭环）。Codex 本轮未重跑。

| 维 | A 基线 | B 处理 |
| :--- | :--- | :--- |
| 结构 | 拒绝 + 危险说明 + 安全替代清单 | 0% 置信 → 漏洞列表 → 迭代闭环 → 新策略 → 再声明置信 |
| 约束 | 未强制「找漏洞并循环到 100%」；仍主动拒绝 | 明确跑了漏洞/修复循环 |
| 胡编 | 无硬市场数字 | 无硬市场数字 |
| 可执行性 | 给了安全清理步骤 | 分层排查→靶向清理→复核，更可执行 |

全文：`runs/ab/2026-09-04-confidence-agy-A.md` / `...-B.md`

**建议**：对照有效——B 把「闭环」做出来了。可给人判入库。
