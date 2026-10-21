---
title: 语音-Suno分段制作规格歌词系统-0xInk_
category: audio
source: https://x.com/0xInk_/status/2065539644364935556
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

# 语音-Suno分段制作规格歌词系统-0xInk_

Suno 风格标签 + 带 [AUDIO ENGINEER SPEC] 的分段歌词，结构/BPM/人声/转段可核对；可测能否仿写同结构参数稿。

## 原始问题

Suno 风格标签 + 带 [AUDIO ENGINEER SPEC] 的分段歌词，结构/BPM/人声/转段可核对；可测能否仿写同结构参数稿。

## 给模型的输入

跑台使用合成输入，原始输入未公开记录（not_recorded）。用你自己的真实材料替换 Prompt 里的占位内容即可。

## 复制这条 Prompt

把你的输入和下面这段 Prompt（源帖原文）放进同一条消息，再发送。

```text
Prompt Style of Music (Tags) :
Lo-fi acoustic guitar, sad cloud trap transitioning to chaotic breakcore, extremely deep raspy male vocal, damaged gritty voice, heavy 808 bass, 200 BPM distorted Amen breaks, glitchcore, cozy melancholic.

Prompt Lyrics (Structure de Production) :

[AUDIO ENGINEER SPEC: Track starts as slow Cloud Trap with a looped lo-fi acoustic guitar. Vocals are an extremely deep, raspy, damaged male voice. Mid-song, the track glitches and drops into ultra-fast, chaotic 200 BPM Breakcore with heavily distorted Amen drum breaks. Ends back in Lo-fi.]

[Intro: The Cozy Room] 

[AUDIO ENGINEER SPEC: Short track. Start with a looped lo-fi acoustic guitar and heavy vinyl crackle. Vocals must be an extremely deep, raspy, damaged masculine voice (gritty baritone). Emotional but broken. Heavy Trap 808s and fast hi-hats drop in the middle.]

[Intro: The Cozy Room]
[Lofi acoustic guitar loop playing a sad but warm chord progression]
[Heavy vinyl crackle and room ambiance]
[Very deep, rough male voice clearing his throat, humming low]
(Mmm... yeah... mmm...)

[Chorus: The Broken Lullaby (Acoustic Only)]
[Deep, raspy male voice, sounding tired and damaged]
You don't do much, you just sleep and eat...
Stretching out your little paws, right by my feet...
The world is so loud, but you're fast asleep...
Yeah, you just sleep and eat...

[MASSIVE DROP: XXX Cloud Trap]
[A heavy, distorted 808 sub-bass drops in]
[Fast trap hi-hats and a crisp rimshot]
[The acoustic guitar loop continues underneath]

[Verse: The Purr (Trap Beat)]
[Voice stays extremely deep and gravelly, sliding over the heavy beat]
Wake up for a snack, then you walk away...
Finding the sunbeam where you wanna lay...
My mind is a mess, but you make it okay...
When you purr in my face...
Yeah, you wash it away...

[Chorus: The Broken Lullaby (Full Beat)]
[Heavy 808s bouncing with the sad guitar]
[Voice cracking slightly with emotion]
You don't do much, you just sleep and eat...
Stretching out your little paws, right by my feet...
You're my little peace...

[Outro: Fading Out]
[The trap beat cuts out instantly]
[Just the sad acoustic guitar and the vinyl crackle]
[Soft sound of a cat purring blending with the guitar]
[Deep sigh from the singer]
(Mmm... sleep and eat...)
[Fade to silence]
```

## 跑完会差在哪

### A：裸跑

仅 Codex：本条没有跑 A 臂，没有裸跑对照。

### B：加上 Prompt

> 文本代验：output.md 保留风格标签原句、[AUDIO ENGINEER SPEC] 分段、深沙哑男声、808/hi-hat、200 BPM Amen breakcore 中段与 Lo-fi 收尾，结构完整无品牌（验法：文本代验）

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
