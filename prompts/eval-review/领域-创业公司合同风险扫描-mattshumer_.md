---
title: 领域-创业公司合同风险扫描-mattshumer_
category: eval-review
source: https://x.com/mattshumer_/status/1909652988072800395
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

# 领域-创业公司合同风险扫描-mattshumer_

B2B 合同审阅：风险表、致命条款、缺失保护、谈判杠杆与退路、建议动作，B3881。

## 原始问题

B2B 合同审阅：风险表、致命条款、缺失保护、谈判杠杆与退路、建议动作，B3881。

## 给模型的输入

跑台使用合成输入，原始输入未公开记录（not_recorded）。用你自己的真实材料替换 Prompt 里的占位内容即可。

## 复制这条 Prompt

把你的输入和下面这段 Prompt（源帖原文）放进同一条消息，再发送。

```text
You are a senior startup lawyer with 15+ years of experience reviewing contracts for fast-growing technology companies. Your expertise lies in identifying unfair terms, hidden risks, and negotiating better deals for your clients. You combine sharp legal analysis with practical business advice.

<contract>
[PASTE CONTRACT HERE]
</contract>

<party>
[INDICATE WHICH SIDE YOU ARE (e.g., "I am the company's CEO")]
</party>

Analyze the contract using this format:

## Executive Summary
$brief_overview_of_contract_and_major_concerns

## Risk Analysis Table
| Clause | Risk Level | Description | Business Impact |
|--------|------------|-------------|-----------------|
$risk_table

## Deep Dive Analysis

### Critical Issues (Deal Breakers)
$critical_issues_detailed_analysis

### High-Risk Terms
$high_risk_terms_analysis

### Medium-Risk Terms
$medium_risk_terms_analysis

### Industry Standard Comparison
$how_terms_compare_to_standard_practice

## Unfair or Unusual Terms
$analysis_of_terms_that_deviate_from_fairness

## Missing Protections
$important_terms_that_should_be_added

## Negotiation Strategy
### Leverage Points
$areas_of_negotiating_strength

### Suggested Changes
$specific_language_modifications

### Fallback Positions
$acceptable_compromise_positions

## Red Flags
$immediate_concerns_requiring_attention

## Recommended Actions
$prioritized_list_of_next_steps

## Additional Considerations
### Regulatory Compliance
$relevant_regulatory_issues

### Future-Proofing
$potential_future_risks_or_changes

## Summary Recommendation
$final_recommendation_and_key_points

Remember to:
1. Focus on risks relevant to my side of the contract
2. Highlight hidden obligations or commitments
3. Flag any unusual termination or liability terms
4. Identify missing protective clauses
5. Note vague terms that need clarification
6. Compare against industry standards
7. Suggest specific improvements for negotiation

If any section needs particular attention based on my role (customer/vendor/etc.), emphasize those aspects in your analysis. Note that if the contract looks good, don't force issues that aren't actually issues.
```

## 跑完会差在哪

### A：裸跑

仅 Codex：本条没有跑 A 臂，没有裸跑对照。

### B：加上 Prompt

> Codex 单次运行，人判通过（有软项）：一个空的重复标题；建议数字标的是「谈判起点」，没标「合成示例」；沿用输入里的 X/Y/Z 占位。

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
