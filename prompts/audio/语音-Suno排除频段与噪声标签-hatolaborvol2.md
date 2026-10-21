---
title: 语音-Suno排除频段与噪声标签-hatolaborvol2
category: audio
source: https://x.com/hatolaborvol2/status/2039717474770522436
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

# 语音-Suno排除频段与噪声标签-hatolaborvol2

Suno 工具格式：[Audio Engine…] 方括号参数块 + [Exclude: …] 排除字段，B213。

## 原始问题

Suno 工具格式：[Audio Engine…] 方括号参数块 + [Exclude: …] 排除字段，B213。

## 给模型的输入

跑台使用合成输入，原始输入未公开记录（not_recorded）。用你自己的真实材料替换 Prompt 里的占位内容即可。

## 复制这条 Prompt

把你的输入和下面这段 Prompt（源帖原文）放进同一条消息，再发送。

```text
■音質改善: 
これは、Lyricかな？
[Audio Engine: Ultra-HD 96kHz], [Buffer: Lossless], [Dithering: None], [Frequency Response: 20Hz-22kHz],

■不要な音の排除: 
これは、Exclude styleに入れるポイよ
[Exclude: 300Hz-500Hz mud, boxiness, phase cancellation, monophonic sub, frequency masking]
[Exclude: vocal gasps, humming, artifacts, hiss, noise]
```

## 跑完会差在哪

### A：裸跑

仅 Codex：本条没有跑 A 臂，没有裸跑对照。

### B：加上 Prompt

> 文本代验：output.md 292 字节，Audio Engine 参数块与两条 Exclude 原样落盘

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
