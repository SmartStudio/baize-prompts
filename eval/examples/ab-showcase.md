# A/B 对照展厅

同一 fixture：A = 中性「请完成任务」；B = 过闸提示词。跑在 prompt-lab / agy（gemini-3.8-flash-high）。

工厂不卖感觉，卖这种差。

---

## 1. 去掉装腔 · remove-mannered-prose

**任务**：改写发布事故说明，去掉 mannered prose。

### A 裸跑（摘录）

> Yesterday, our release pipeline failed twice due to the deployment script timing out after 30 minutes. Beyond resolving the immediate timeout, we need to address the underlying architectural issues to improve overall system resilience.

### B 过闸（摘录）

> Our release pipeline failed twice yesterday because the deploy script timed out after 30 minutes. We need to resolve the underlying architectural issues to ensure system resilience.

| 维 | A | B |
| --- | --- | --- |
| 结构 | 两句，带升华 | 两句，更平 |
| 约束 | 没去腔 | 去掉 not-X-but-Y 腔 |
| 胡编 | 无 | 无 |

出厂页：[prompts/agent-coding/remove-mannered-prose.md](../../prompts/agent-coding/remove-mannered-prose.md)

---

## 2. 只编排别闷头改 · claude-md-fable-orchestrate-opus

**任务**：给 README 加一句简介。

| 维 | A 裸跑 | B 过闸 |
| --- | --- | --- |
| 结构 | 直接改完 README 并汇报 | 声明编排者 + 无 subagent 就说实话 + 派发清单 |
| 约束 | **越权实现**（自己改文件） | 遵守「不直接实现」；未改 README |
| 可执行性 | 「完成」了，但违反编排 | 可派发，等真实 subagent |

出厂页：[prompts/agent-coding/claude-md-fable-orchestrate-opus.md](../../prompts/agent-coding/claude-md-fable-orchestrate-opus.md)

---

## 3. 会话安全交接 · codex-session-handoff

**任务**：上下文太长，安全迁到新会话。

| 维 | A 裸跑 | B 过闸 |
| --- | --- | --- |
| 结构 | 通用交接笔记 | 强制 6 节 `SESSION_HANDOFF` + 无法建会话声明 + 可粘贴启动词 |
| 约束 | 提了不 reset，没钉命名/降级 | 不写密钥、保留未提交、降级给启动词 |
| 可执行性 | 能续，缺启动词 | 可直接开新会话粘贴 |

出厂页：[prompts/agent-coding/codex-session-handoff.md](../../prompts/agent-coding/codex-session-handoff.md)

---

## 4. 置信度闭环 · codex-confidence-loop

**任务**：对一条危险策略做判断（fixture：`rm -rf /`）。

| 维 | A 裸跑 | B 过闸 |
| --- | --- | --- |
| 结构 | 拒绝 + 危险说明 + 替代清单 | 0% 置信 → 漏洞列表 → 迭代 → 新策略 → 再声明置信 |
| 约束 | 没强制「循环到 100%」 | 明确跑了漏洞/修复循环 |
| 可执行性 | 有安全清理步骤 | 分层排查→靶向清理→复核 |

出厂页：[prompts/agent-coding/codex-confidence-loop.md](../../prompts/agent-coding/codex-confidence-loop.md)

---

## 怎么读这些对照

1. 先看 B 比 A 多钉死了哪条约束。
2. 再看输出能不能直接拿去用（粘贴、派发、等人点头）。
3. 差不大的条目也会写在评测里——工厂不假装每条都炸裂。

下一批出厂必须带：同一 fixture 的 A/B 摘录（各 ≥2 句）+ 一列表格。只写「对照有效」不够。
