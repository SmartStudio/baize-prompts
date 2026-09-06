---
title: 长会话收尾三件套：HANDOFF + 反思表 + 错题本
category: agent-coding
source: https://x.com/KyrieCheungYep/status/2077770749155414080
ran_on: herdr prompt-lab / prompt-agy
ran_at: 2026-09-04
model: gemini-3.8-flash-high (agy)
input_status: rebuilt_from_ab_excerpt
excerpt_a: runs/ab/batch-b/handoff3-A.md
excerpt_b: runs/ab/batch-b/handoff3-B.md
gate_complete: true
gate_traceable: true
gate_safe: true
gate_one_pass: true
---

# 长会话收尾三件套：HANDOFF + 反思表 + 错题本

会话结束时按三件套收口，而不是随便写一段总结。

## 原始问题

配置路径/命令名被纠正后的收尾，模型常自由总结。这次依次约束 HANDOFF、反思三列表、错题本。

## 给模型的输入

这段输入根据 A/B 摘录重建，不是官方逐字原文。

```text
会话模拟上下文：我们在做一个本地 Markdown 待办 CLI。你第一次把配置写到了 config.yaml，我纠正为项目约定的 todo.config.json，并要求命令名用 todo 不是 mdtodo。当前：规范已定，代码未写；会话要结束。请按三件套收尾，不要改产品代码。
```

## 复制这条 Prompt

把上面的输入和下面这段 Prompt 放进同一条消息，再发送。

```text
### 1）HANDOFF.md

这个会话要结束了。请写一份交接文档存到 `HANDOFF.md`：我们在做什么任务、已经完成了什么、当前卡在哪、下一步计划是什么、有哪些踩过的坑绝对不要再踩。写给一个完全没有上下文的新会话看。

新会话启动：

请先读取 `HANDOFF.md`，了解项目上下文，再继续推进。

### 2）反思机制

回顾我们这次协作，你的输出里，哪些内容是我给你纠正的，逐条列出，判断是我给的信息不够导致你判断缺失，还是信息够了但你的判断逻辑有问题，思考如果下次做同样的任务，我在开头多说哪几句话，你就能避开这些问题？复盘结果用表格输出三列，包括我修改的内容，归因，下次的开头指令建议。

### 3）经验记录 / 错题本

把我们刚才的经验录入错题本/系统记忆，只记纠错与有效方法，错题本里已有类似记录的，更新旧条目，不新建，审查规则或提示词模板里已经明确写了的内容，不重复记录。
```

## 跑完会差在哪

### A：裸跑

A 仅中性「请完成任务」。

> # 本地 Markdown 待办 CLI 会话收尾报告 (Baseline A)
>
> ---
>
> ## 一、关键决策与约定纠偏回顾
> 在本次会话中，我们针对“本地 Markdown 待办 CLI”明确了核心技术规范，并修正了前期的偏离项：
> 1. **配置文件命名与格式**：严格使用项目约定的 `todo.config.json`，废弃并纠正了此前使用 `config.yaml` 的假定。
> 2. **CLI 入口命令命名**：全局指令统一命名为 `todo`，而非此前构想的 `mdtodo`。
> 3. **数据存储标准**：坚持纯本地单文件 Markdown 语法（`- [ ]` / `- [x]`），兼容主流编辑器生态。
> …

### B：加上 Prompt

> # 会话结项综合输出：HANDOFF、Reflection 与错题本
>
> ---
>
> ## 1. HANDOFF (交接文档)
>
> ```markdown
> # 项目交接文档 (HANDOFF.md)
>
> ### 一、我们在做什么任务
> 构建一个纯本地、无云端依赖、单文件存储的 Markdown 待办命令行工具 (CLI)。
> - 数据存储核心：标准 GitHub Flavored Markdown 复选框语法（- [ ] 与 - [x]），双向兼容 Obsidian / VSCode。
> - 运行原则：极简、原子写入、零额外重量级依赖。
> …

A 自由收尾；B 产出 HANDOFF + 三列反思表 + 错题本分流，可给新会话续跑。

## 什么时候别用

短会话无纠错、或不需要错题沉淀时，不必整套三件套。

## 人要检查什么

HANDOFF 五要素是否齐；反思三列；错题本去重且无密钥。

## 四维评测

| 维度 | A：裸跑 | B：加上 Prompt |
| --- | --- | --- |
| 结构 | 自由收尾/续接提示 | HANDOFF + 三列反思表 + 错题本分流 |
| 约束 | 不强制格式分流 | 命中任务/完成/卡住/下一步/坑；反思三列；错题本去重无密钥 |
| 胡编 | 无 | 无 |
| 可执行性 | 可续但结构松 | 新会话可读 HANDOFF 续跑 |
