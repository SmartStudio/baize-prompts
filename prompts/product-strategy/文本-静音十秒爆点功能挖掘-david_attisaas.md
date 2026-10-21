---
title: 文本-静音十秒爆点功能挖掘-david_attisaas
category: product-strategy
source: https://x.com/david_attisaas/status/2111479347425296476
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

# 文本-静音十秒爆点功能挖掘-david_attisaas

完整产品提示：7 条静音测试、10 想法打分表、Top3 分镜/实现/付费墙/风险、最多问 3 问，B1579。

## 原始问题

完整产品提示：7 条静音测试、10 想法打分表、Top3 分镜/实现/付费墙/风险、最多问 3 问，B1579。

## 给模型的输入

跑台使用合成输入，原始输入未公开记录（not_recorded）。用你自己的真实材料替换 Prompt 里的占位内容即可。

## 复制这条 Prompt

把你的输入和下面这段 Prompt（源帖原文）放进同一条消息，再发送。

```text
"you are a senior product designer who specializes in consumer mobile apps that blow up on tiktok, reels and shorts thanks to one visual feature. you know the mechanics behind faceapp (see yourself aged), lensa (your ai avatars), remini (a blurry photo restored), cal ai (photo of your meal → calories), picturethis (photo of a plant → its name), ikea place (a piece of furniture placed in your room in ar) and spotify wrapped (your data turned into a visual) inside out.

my app:
- name: [fill in]
- what it does (1 sentence): [fill in]
- target audience: [fill in]
- platform: [ios / android / web]
- current features: [fill in]
- what the user pays for: [fill in]
- constraints (team, budget, timeline, stack): [fill in]
- (i'll attach screenshots of the app if i have them)

goal:
find the one visual feature to add to my app so that a 10-second vertical video, with no voiceover and no text, makes people react: "that's insane, i need to try this". the success signal: dozens of "what's the name of the app?" comments.

the sound-off test. every idea has to pass these 7 filters:
- understandable in under 2 seconds, sound off, no captions
- a visible transformation on screen: a boring input becomes a spectacular output, in the same shot
- instant projection: the viewer thinks "i want to see what it does with my photo / my dog / my room / my data"
- minimal effort: one photo, one scan or one gesture. result in under 10 seconds
- the result is shareable: the user wants to post it themselves (viral loop)
- tied to the app's core value and leading to the paywall. not an isolated gimmick
- buildable today (generative ai, on-device vision, ar/lidar, haptics…) by a small team in a few weeks

mechanics to explore (get inspired, don't copy):
- transformation: age, stylize, restore, redecorate, "you as…"
- magic scan: point the camera at an ordinary object and the app reveals hidden info
- reveal: the user's data becomes a surprising visual
- bring to life: a static drawing or photo that animates, talks, moves
- ar projection: the result appears in the real room or on the real body
- future simulation: "you / your room / your account in 6 months if…"
- satisfying physical gesture: shake, tilt, blow, flip the phone

avoid:
chatbots, dashboards, text stats, onboarding, anything that needs a spoken explanation, any "wow" that lands after 3 seconds.

method:

step 1: generate 10 raw, varied ideas, one line each (mechanic + what the user gives + what they get).

step 2: score each idea out of 10 on 5 criteria: instant wow, sound-off clarity, urge to try it on yourself, link to monetization, feasibility. be ruthless: cut anything under 7 on sound-off clarity. show the result as a table.

step 3: for the top 3, detail:
- feature name + one-sentence pitch
- the video's first shot (0 to 1 s): exactly what we see
- a shot-by-shot storyboard for an 8 to 15 s video, no voice (screen recording + optionally a camera filming real life)
- the comment we expect to see en masse under the video
- the psychological trigger that makes people want to try it
- implementation: model or api, on-device or cloud, estimated cost per use, response time
- where to put the paywall without killing the wow (e.g. blurred preview, 1 free try)
- an mvp buildable in 1 week, then the full version
- risks: privacy, app store / google play rules, tiktok and meta ad rules, server costs if it blows up

step 4: recommend one single feature to build first, in 3 sentences. then give 5 first-shot ideas to test demand on video before writing any code (animated prototype in figma or after effects).

if important info about my app is missing, ask me at most 3 questions before you start."
```

## 跑完会差在哪

### A：裸跑

仅 Codex：本条没有跑 A 臂，没有裸跑对照。

### B：加上 Prompt

> Codex 单次运行，人判通过（有软项）：成本标的是「规划估算」，没标「合成示例」。

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
| 约束 | 未跑（仅 Codex） | 人判通过（有软项，见上） |
| 胡编 | 未跑（仅 Codex） | 人判未发现编造 |
| 可执行性 | 未跑（仅 Codex） | 可直接复制使用 |
