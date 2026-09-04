---
title: 一句话删掉事故说明里的装腔
category: agent-coding
source: https://x.com/Voxyz_ai/status/2095260094795583807
ran_on: prompt-lab / Codex+agy
ran_at: 2026-09-04
model: agy gemini-3.8-flash-high high
input_status: rebuilt_from_ab_excerpt
excerpt_a: runs/ab/2026-09-04-mannered-agy-A.md
excerpt_b: runs/ab/2026-09-04-mannered-agy-B.md
gate_complete: true
gate_traceable: true
gate_safe: true
gate_one_pass: true
---

# 一句话删掉事故说明里的装腔

事故已经够烦了，说明别再写成公司愿景。

## 原始问题

模型改写发布事故说明时，保住了事实，却顺手加上「解决底层架构问题、提升系统韧性」这类抬价句。工程师想先看清事故和处理项，不想从铺垫里捞重点。

这次只测一件事：一句很短的 Prompt，能不能把腔拿掉，又不改事故事实。

## 给模型的输入

这段输入根据 A/B 摘录重建，不是官方逐字原文。原始记录没有保存完整官方输入。

```text
Yesterday, our release pipeline failed twice due to the deployment script timing out after 30 minutes. Beyond resolving the immediate timeout, we need to address the underlying architectural issues to improve overall system resilience.
```

## 复制这条 Prompt

在 Cursor 或任意模型里新开对话。把上面的输入和下面这句放进同一条消息，再发送。

```text
Please remove all mannered prose.
```

只想看改写结果，可以在消息末尾另加一句「只返回改写后的正文」。这句是调用条件，不属于原始 Prompt。

## 跑完会差在哪

### A：中性指令

记录只写了 A 使用中性「请完成任务」，准确英文指令没有保存。真实摘录如下：

> Yesterday, our release pipeline failed twice due to the deployment script timing out after 30 minutes. Beyond resolving the immediate timeout, we need to address the underlying architectural issues to improve overall system resilience.

### B：加上 Prompt

> Our release pipeline failed twice yesterday because the deploy script timed out after 30 minutes. We need to resolve the underlying architectural issues to ensure system resilience.

B 删掉了 “Beyond resolving the immediate timeout” 这层铺垫，直接进入处理判断。失败两次、部署脚本、30 分钟超时和架构问题都还在，也没有多编数字或原因。

它没有删掉 “system resilience”。所以这条 Prompt 的真实效果是收平语气，不是把所有抽象词一扫而空。

## 什么时候别用

人物口吻、品牌文案和刻意保留修辞节奏的文本，不适合直接套。输入里有客户信息、生产密钥或没确认的事实，也先别跑。

这条 Prompt 只处理文字表达，不适合图片或视频任务。

## 人要检查什么

逐句核对数字、原因和处理判断。确认语气没有被削得过平，再决定是否写回真实仓库或接进生产工作流。人没点头，不自动放大。

## 四维评测

| 维度 | A：中性指令 | B：加上 Prompt |
| --- | --- | --- |
| 结构 | 两句，第二句先铺垫再谈处理 | 两句，第二句直接谈处理 |
| 约束 | 没有去腔约束，原句基本保留 | 去掉一处抬价铺垫，事实仍在 |
| 胡编 | 摘录内未见新增数字或原因 | 摘录内未见新增数字或原因 |
| 可执行性 | 能读，重点被铺垫拖慢 | 可直接对照回填，仍需人工核对 |
