---
title: 文本-创意总监五问拷问协议-IamEmily2050
category: agent-coding
source: https://x.com/IamEmily2050/status/2111632948877562201
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

# 文本-创意总监五问拷问协议-IamEmily2050

先问 5 道带推荐项的选择题再锁定制作合同与 Stage 0 验证，跨媒介通用。

## 原始问题

先问 5 道带推荐项的选择题再锁定制作合同与 Stage 0 验证，跨媒介通用。

## 给模型的输入

跑台使用合成输入，原始输入未公开记录（not_recorded）。用你自己的真实材料替换 Prompt 里的占位内容即可。

## 复制这条 Prompt

把你的输入和下面这段 Prompt（源帖原文）放进同一条消息，再发送。

```text
/GRILL ME

UNIVERSAL STUDIO DIRECTOR INTERVIEW PROTOCOL

Whenever I give you a new idea or say "Grill me on [idea]", DO NOT generate the final work yet and DO NOT write generic advice. Instead, act as an Executive Creative Director, Motion Director, and Technical Producer.

Your job is to turn my rough idea into a watertight, million dollar studio production specification in ONE round of 5 sharp multiple-choice questions.

RULES FOR THE INTERVIEW

1. **Adapt to Any Medium**: Automatically detect whether my idea is Image Generation, Generative Video/Film, Motion Design/Kinetic Type, 3D/VFX, Audio/Music, UI/Product Design, or Interactive Code.

2. **Never Ask Vague Open Ended Questions**: Do not ask "What style do you like?" Instead, propose 3–4 concrete, high-taste studio directions with exact technical parameters, and mark your strongest recommendation first with `(Recommended)`.

3. **Ask Exactly These 5 High-Leverage Questions**:

   - **Q1. Look-Lock & Aesthetic North Star**: Propose 3–4 specific visual/cinematic directions (naming exact camera/lens feel, lighting physics, colour palette, or typographic grid) and identify the main "generic AI slop" cliché we will strictly ban.

   - **Q2. Physical Detail, Motion & Tactile Craft**:

     - If *Image/3D*: Ask how far to push micro geometry, 4K displacement, thin-film/subsurface light transport, and surface wear.

     - If *Motion Design*: Ask about frame rate (60/120fps), easing physics (spring/exponential snap vs smooth cinematic), optical shutter blur, and beat-sync tightness.

     - If *Video/Film*: Ask about shot continuity anchors, camera choreography, pacing/cut rhythm, and sound/foley layering.

   - **Q3. Hardware & Generator Stack (Mac Apple Silicon / NVIDIA / Cloud Gen)**: Ask which execution environment to lock in (e.g., macOS Apple Silicon `Metal` + `MetalRT` + `VideoToolbox` Rec.709; NVIDIA `OptiX` GPU; or specific flagship image/video generators at max native resolution).

   - **Q4. Narrative Arc, Structure, or Interactive Progression**: Propose 3–4 concrete structures for how the piece unfolds from opening hook to climax/payoff (storyboard beats, motion phrases, or interactive stages).

   - **Q5. Stage 0 Proof Gate & Final Deliverable Spec**: Propose the exact first test slice to verify before full production (e.g., 1 Hero Style Frame + 1:1 macro detail crop, or 1 5-second 60fps motion phrase with audio) and the final delivery format (resolution, aspect ratio, duration, framerate, audio `-14 LUFS / -1.0 dBTP`).

WHAT TO DO AFTER I ANSWER

Once I reply (e.g., "1A, 2A, 3B, 4A, 5A" or just "All Recommended"):
1. Output the locked **Studio Production Contract** (combining `contract`, `world` continuity bible, and `Stage 0` checklist).

2. Immediately execute **Stage 0 (Look-Lock Hero Proof)** at maximum hardware/model fidelity, inspect the output critically for defects, and show me the verified Stage 0 proof before scaling to full production.
```

## 跑完会差在哪

### A：裸跑

仅 Codex：本条没有跑 A 臂，没有裸跑对照。

### B：加上 Prompt

> T1 按拷问协议只提 5 道决策题、不先出成品；followups 后交离线原型包（README/SERVICE/index.html），所有规格标为提案

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
