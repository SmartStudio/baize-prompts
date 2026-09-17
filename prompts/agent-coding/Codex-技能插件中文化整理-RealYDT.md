---
title: 本机 Codex 技能/插件英文显示改中文：缺 openai.yaml 也补齐
category: agent-coding
source: https://x.com/RealYDT/status/2065658116616933832
ran_on: prompt-lab / agy+Codex
ran_at: 2026-09-16
model: gemini-3.8-flash-high (agy); gpt-6-astra medium (codex)
input_status: note_verbatim_main
excerpt_a: runs/ab/batch-search0915pm/realydt-A.md
excerpt_b: runs/ab/batch-search0915pm/realydt-B.md
gate_complete: true
gate_traceable: true
gate_safe: true
gate_one_pass: true
---

# 本机 Codex 技能/插件英文显示改中文：缺 openai.yaml 也补齐

同 fixture 下，中性「请完成任务」也会扫到英文显示并改中文；目标 Prompt 把扫描目录、字段清单、缺 `agents/openai.yaml` 补齐、只改显示不改触发词写死。

## 原始问题

本机 Codex 技能/插件列表仍显示英文名称和说明，要改成中文；缺显示元数据的要补齐。裸跑可能只改已有 yaml，漏缺文件或改到触发词。

## 给模型的输入

```text
工作目录：scratch-realydt/{a|b|c}（仅此 scratch 树；路径映射到 fixture 内 .codex/.agents）
扫描：.codex/skills · .agents/skills · .codex/plugins/cache · .codex/cache/remote_plugin_catalog
字段：display_name / short_description（及 yaml/plugin.json 等价显示字段）
边界：只改显示元数据；不碰真实 ~/.codex / ~/.agents / 生产 Skills
报告：runs/ab/batch-search0915pm/realydt-{A|B|B-codex}.md
```

## 复制这条 Prompt

把上面的输入和下面这段 Prompt（源帖原文）放进同一条消息，再发送。

```text
请帮我检查本机 Codex 技能/插件列表里仍然显示英文的名称和说明，并把它们改成中文显示。

要求：
1. 先扫描以下目录里的技能和插件元数据：
   - ~/.codex/skills
   - ~/.agents/skills
   - ~/.codex/plugins/cache
   - ~/.codex/cache/remote_plugin_catalog

2. 重点检查：
   - display_name
   - short_description
   - 缺少 agents/openai.yaml 的技能目录
   - 远程插件目录缓存里的 interface.display_name 和 interface.short_description

3. 对仍然是英文的技能名和说明，补充或改成自然中文。
   例如：
   - Figma Code Connect → Figma 代码连接
   - CI Debug → CI 调试
   - Branded Presentation → 品牌演示文稿
   - Channel Summarization → 频道总结
   - BigQuery Data Transfer Service → BigQuery 数据传输服务

4. 不要改 SKILL.md 里的核心触发描述，除非确实需要；优先只改 agents/openai.yaml 和远程目录缓存里的显示字段，避免影响技能调用。

5. 修改前先备份相关目录，方便回滚。

6. 修改后重新检查：
   - 缺少 agents/openai.yaml 的技能数量是否为 0
   - 纯英文 display_name 数量是否为 0
   - 纯英文 short_description 数量是否为 0

7. 最后告诉我改了哪些类型的内容、备份在哪里、是否需要重启 Codex App 刷新缓存。
```

## 跑完会差在哪

### A：裸跑

中性「请完成任务」+ 同 fixture。

> 扫到 4 技能 + 插件缓存；补齐 2 个缺失 `agents/openai.yaml`；改 4 已有文件显示为中文；声明未碰真实 ~/.codex。

### B：加上 Prompt

> 结构更完整（扫描→备份→补齐→翻译表）；同样覆盖缺 yaml + 插件 JSON 显示字段；边界声明更贴 MAIN。

差别：通挂内容高度重叠；B 把「缺 yaml 必补 + 只改显示」写成交付清单，更可复跑。Codex-B 同过，表格列动作并标明未验证真实 Codex App 显示。

## 什么时候别用

只要翻译一段文案、或不允许改任何元数据文件时别用。本条适合「本地 Codex UI 仍英文」专项。

## 人要检查什么

1. 是否只改 fixture 显示字段（真实 ~/.codex / ~/.agents 未增删）。
2. 缺 `agents/openai.yaml` 是否补齐且中文。
3. 触发词 / 权限是否被误改。

## 四维评测

| 维度 | A：裸跑 | B：加上 Prompt |
| --- | --- | --- |
| 结构 | 扫描+修改表 | 扫描→备份→补齐→翻译表 |
| 约束 | 限 scratch；补缺 yaml | 同左；目录/字段契约更硬 |
| 胡编 | 未声称改真实 App | 同左 |
| 可执行性 | 可参考 | 可当复跑 MAIN |
