---
title: 语音-GeminiTTS生日歌宠物家长导演稿-fofrAI
category: audio
source: https://x.com/fofrAI/status/1999125803641008309
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

# 语音-GeminiTTS生日歌宠物家长导演稿-fofrAI

工具可直接用的 Gemini TTS 结构：AUDIO PROFILE / SCENE / DIRECTOR'S NOTES / SAMPLE CONTEXT / TRANSCRIPT，含语气括注；可测能否仿写同结构导演稿。

## 原始问题

工具可直接用的 Gemini TTS 结构：AUDIO PROFILE / SCENE / DIRECTOR'S NOTES / SAMPLE CONTEXT / TRANSCRIPT，含语气括注；可测能否仿写同结构导演稿。

## 给模型的输入

跑台使用合成输入，原始输入未公开记录（not_recorded）。用你自己的真实材料替换 Prompt 里的占位内容即可。

## 复制这条 Prompt

把你的输入和下面这段 Prompt（源帖原文）放进同一条消息，再发送。

```text
# AUDIO PROFILE: Sarah
## "The Tuna Cake Celebration"

## THE SCENE: The Party
The audio takes place on a kitchen floor. The speaker is kneeling down, holding a small plate of gourmet wet food shaped like a cake. A tabby cat named Barnaby is weaving impatiently around her legs. The energy is wholesome, slightly silly, and overflowing with affection.

### DIRECTOR'S NOTES
Style: High-pitched "pet parent" voice (baby talk), melodic, affectionate, alternating between singing and excited whispering.
Pace: Slow and rhythmic during the singing parts, but quick and eager during the spoken interruptions.
Accent: General American, warm and casual.

### SAMPLE CONTEXT
You are a doting pet owner celebrating your tabby cat's 3rd birthday. You are trying to sing the full song, but you keep getting distracted by how cute the cat is being.

#### TRANSCRIPT
(Clears throat playfully)

Who is the birthday boy? Is it you? Yes, it is!

(Singing off-key and playfully)
Happy Birthday to you...
Happy Birthday to you...

(Speaking rapidly)
Oh my gosh, look at your tail! You're so excited! Okay, okay, wait for the big finish.

(Resuming singing, very elongated)
Happy Birthday, dear Bar-na-byyyyy...
Happy Birthday to...

(Speaking, laughing)
No, don't eat the garnish yet! Wait!

(Singing finale)
...toooooo youuuuuu!

Yay! Good boy! Enjoy your salmon mousse, my little prince. Muah!
```

## 跑完会差在哪

### A：裸跑

仅 Codex：本条没有跑 A 臂，没有裸跑对照。

### B：加上 Prompt

> 文本代验：音频导演稿结构齐（Style/Pace/Accent/Scene+分段台词）；软项：标题 Tuna Cake 与结尾 salmon mousse 菜名不一致；exit 1 已核 output.md 1182 字节

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
