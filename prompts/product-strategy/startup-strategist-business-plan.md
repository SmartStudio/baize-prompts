---
title: 把商业点子压成能验证的 90 天计划
category: product-strategy
source: https://x.com/gudanglifehack/status/2093191483000230086
ran_on: prompt-lab / Codex+agy
ran_at: 2026-09-04
model: agy gemini-3.8-flash-high high
input_status: rebuilt_from_ab_excerpt
excerpt_a: runs/ab/2026-09-04-bizplan-agy-A.md
excerpt_b: runs/ab/2026-09-04-bizplan-agy-B.md
gate_complete: true
gate_traceable: true
gate_safe: true
gate_one_pass: true
---

# 把商业点子压成能验证的 90 天计划

点子可以很快，市场数字和收入不能靠模型补。

## 原始问题

用户给了一个通过 Maps 找客户、先建站再谈价的想法。普通回答也能写计划，却可能自拟结构、补未经来源支持的比例，还不一定挑战「先完整建站」这个高成本假设。

测试要看 Prompt 能不能守住 15 节结构，把事实和假设分开，并把第一步拉回需求验证。

## 给模型的输入

这段输入根据 A/B 摘录重建，不是官方逐字原文。原始 Maps 段没有保存，目标地区、客户类型、预算、收费方式和现有资源都缺失。

```text
我想通过 Maps 找潜在客户，先为对方完整建站，再联系对方谈价格。请把这个想法做成商业计划。

[缺失：目标地区、客户类型、预算、收费方式、团队能力和原始 Maps 段全文。]
```

## 复制这条 Prompt

先贴商业想法，再贴下面这段 Prompt。原文最后要求等待 idea；两段同发时，模型可以直接开始。

```text
Act as an experienced startup strategist and business consultant.

I will give you a business idea. Your job is to turn it into a practical, realistic, step-by-step business plan.

Analyze the idea and create the plan using this structure:

1. BUSINESS OVERVIEW
Explain the business in simple terms.

2. PROBLEM
What customer problem does this business solve?

3. SOLUTION
How exactly does the product or service solve that problem?

4. TARGET CUSTOMER
Define:
- Ideal customer
- Customer demographics
- Customer needs
- Buying behavior
- Why they would pay

5. VALUE PROPOSITION
Create a clear and compelling reason why customers should choose this business.

6. COMPETITION
Identify the main competitors or alternatives and explain how this business can differentiate itself.

7. BUSINESS MODEL
Explain how the business will make money.

Recommend the most suitable pricing and revenue model.

8. MARKETING STRATEGY
Create a practical customer acquisition strategy using suitable channels such as:
- SEO
- Social media
- Content marketing
- Paid advertising
- Email
- Partnerships
- Cold outreach
- Referrals

9. SALES STRATEGY
Explain how to turn prospects into paying customers.

10. MVP
Design the simplest version of the product or service that can be launched quickly to test demand.

11. LAUNCH PLAN
Create a step-by-step launch plan for:

Week 1
Week 2
Week 3
Week 4

12. FINANCIAL MODEL
Identify:
- Startup costs
- Monthly operating costs
- Revenue sources
- Pricing
- Break-even considerations

Do not invent financial numbers. If information is missing, clearly state what assumptions are required.

13. RISKS
Identify the biggest risks and explain how to reduce them.

14. GROWTH STRATEGY
Explain how the business could grow from the first 10 customers to 100, then 1,000+ customers.

15. 90-DAY ACTION PLAN
Create a practical 90-day roadmap with clear priorities and milestones.

Finally, give me:

🎯 BIGGEST OPPORTUNITY
⚠️ BIGGEST RISK
💰 BEST REVENUE MODEL
🚀 BEST CUSTOMER ACQUISITION CHANNEL
🧪 FIRST THING TO VALIDATE
📋 FIRST 5 ACTIONS I SHOULD TAKE

Important:
- Do not blindly agree with my idea.
- Challenge unrealistic assumptions.
- Separate facts from assumptions.
- Do not invent statistics or market data.
- Keep the plan practical rather than theoretical.
- Prioritize actions that can be completed with limited resources.

Wait for me to provide my business idea.
```

## 跑完会差在哪

完整运行文件当前不在工作区。下面照录 raw 里的真实评测摘录，不冒充模型完整输出。

### A：裸跑

A 使用中性「请完成任务」。

> 自拟中文 15 节（执行摘要→KPI），**未**对齐英文 15 节契约
>
> 本轮未见硬美元/ARR；仍有「90% 搜索来自手机」等未给来源比例

### B：加上 Prompt

> 对齐 BUSINESS OVERVIEW→90-DAY + 六条收尾
>
> §12 明确不编宏观市场数据，列科目/假设；挑战「先完整建站再谈价」

A 也给出了可执行 SOP，但结构没命中，还补了一个没有来源的 90% 比例。B 按 15 节和六条收尾输出，财务只列科目与所需假设，也把「先完整建站」拉回验证。B 的 `fabricated_market_stats=no` 是运行记录自报，仍需人工复核正文。

## 什么时候别用

用户还没给具体 idea 时，这条 Prompt 只该等待。需要投资决策、正式财务预测或受监管行业判断时，不能把这份计划当尽调。

## 人要检查什么

把每个市场判断标成事实或假设，删除无来源数字。再检查定价、获客成本、交付能力和 90 天里程碑是否符合真实资源。第一批客户验证前，别先批量建完整网站。

## 四维评测

| 维度 | A：裸跑 | B：加上 Prompt |
| --- | --- | --- |
| 结构 | 自拟 15 节，未命中指定契约 | 命中 15 节和六条收尾 |
| 约束 | 没有禁止统计胡编的硬约束 | 财务缺数据就列假设，并挑战高成本前提 |
| 胡编 | 出现无来源的 90% 比例 | 摘录内未见硬美元或 ARR |
| 可执行性 | 有 SOP，但验收口径不统一 | 可按固定结构检查并先做需求验证 |
