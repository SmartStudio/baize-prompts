---
type: image-prompt-factory
created: 2026-09-14
category: image-gen
title: "GPT Image 2.5 · Line 表情包序列帧"
source: "https://x.com/Gorden_Sun/status/2097508341992083824"
fixture: "synthetic 半身角色参考 → 4×4 Line 表情格"
fixture_source: synthetic_codex
model: "gpt-6-astra medium · Codex image_gen"
ran_on: "prompt-lab / Codex image_gen"
ran_at: 2026-09-14
verdict: accepted
gate_complete: true
gate_traceable: true
gate_safe: true
gate_one_pass: true
tags: [image-gen, eval-report, baize-prompts]
---

# 评测报告：GPT Image 2.5 · Line 表情包序列帧

> 开源分享硬门槛：本页必须能直接看见成图。缺图 = 不可 PR。
> 对应提示词：[GPTImage25-Line表情包序列帧](GPTImage25-Line表情包序列帧.md)

## Prompt

```text
为我生成图中角色的卡通Line风格的半身像GIF表情包每一帧的图片，注意头饰和发型要正确。
使用 4行x4列 布局共生成16个小图片。16个小图片为“飞吻”动画的连贯的拆分动作，使用这16张可以组成一个完整的、循环动画，动作流畅逼真，最后一帧应流畅地循环回到第一帧。16张图片里都使用跟图片搭配的字体写着汉字“爱你哦”。16个小图片之间需要有足够留白方便后续切割，每张图片都不要超出自己的区域。
注意不要原图复制，只是使用图片里的人物。背景为纯白色，不要画分割线。图片比例1：1
```

## Fixture

- `fixture`：synthetic 半身角色参考 → 4×4 Line 表情格
- `fixture_source`：`synthetic_codex`（Codex 合成 MAIN）
- `model` / 跑台：gpt-6-astra medium · Codex image_gen（prompt-lab / Codex image_gen）

## 成图（必嵌）

### MAIN-ref（synthetic_codex）

![MAIN-ref](images/GPTImage25-Line表情包序列帧-MAIN-synthetic.png)

### B · 待测 Prompt 输出

![B 成图](images/GPTImage25-Line表情包序列帧-B.png)

## 摘要

通挂：16 格/「爱你哦」/头饰贯穿；飞吻循环△（混入比心等，单动作连贯偏弱）；fixture=synthetic_codex。

## 判定

- 动作：入库
- 开源：可分享（图齐）
- 日期：2026-09-14

## 四维（可选短表）

| 维度 | 可见表现 |
| --- | --- |
| 结构 | 4×4=16 格白底半身网格 |
| 约束 | 汉字与头饰可跟踪 |
| 胡编/扩写 | 飞吻循环混入比心等变体 |
| 可复现 | 格数/字通挂；循环连贯性需人判 |
