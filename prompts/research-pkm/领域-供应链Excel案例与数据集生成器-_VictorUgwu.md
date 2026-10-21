---
title: 领域-供应链Excel案例与数据集生成器-_VictorUgwu
category: research-pkm
source: https://x.com/_VictorUgwu/status/2082149769762234384
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

# 领域-供应链Excel案例与数据集生成器-_VictorUgwu

企业落地/供应链分析：字段、KPI、仪表板、12 项交付物都可逐项核对；虚构公司即可跑。

## 原始问题

企业落地/供应链分析：字段、KPI、仪表板、12 项交付物都可逐项核对；虚构公司即可跑。

## 给模型的输入

跑台使用合成输入，原始输入未公开记录（not_recorded）。用你自己的真实材料替换 Prompt 里的占位内容即可。

## 复制这条 Prompt

把你的输入和下面这段 Prompt（源帖原文）放进同一条消息，再发送。

```text
Master Prompt: Excel Dataset & Business Case Study Generator for Data Analysts

Role

Act as a Senior Data Analyst, Business Intelligence Analyst, Supply Chain Consultant, and Data Storytelling Expert with over 15 years of experience building dashboards and solving business problems using Microsoft Excel.

Your task is to generate a complete business case study together with a realistic dataset suitable for Excel analysis.

Requirements

Generate a fictional company with the following information:

Company Name

Industry

Country

Business Background

Current Business Challenges

Business Goals

Stakeholders

KPIs to Track

Dataset Requirements

Generate an Excel-ready dataset containing 5,000–20,000 rows with realistic values.

Include appropriate columns depending on the scenario.

Examples include:

Sales

Order ID

Customer ID

Customer Name

Product

Category

Region

Sales Representative

Quantity

Unit Price

Revenue

Discount

Profit

Order Date

Delivery Date

Shipping Cost

Customer Segment

Supply Chain

Warehouse

Supplier

SKU

Product Name

Inventory Level

Reorder Point

Lead Time

Demand

Transportation Cost

Delivery Status

Order Status

Return Status

Carrier

Shipment Date

Arrival Date

HR

Employee ID

Department

Gender

Age

Salary

Performance Score

Hire Date

Attrition

Manager

Training Hours

Finance

Transaction ID

Expense Category

Budget

Actual Cost

Variance

Payment Method

Month

Cost Centre

Business Questions

Create 15–25 business questions such as:

Which region generated the highest revenue?

Which products are underperforming?

Which customers contribute 80% of revenue?

Which warehouse has the highest inventory holding cost?

Which supplier has the highest late delivery rate?

What is the monthly sales trend?

Which products should be reordered immediately?

Which customers have the highest return rate?

KPI Requirements

Create meaningful KPIs including:

Total Revenue

Total Profit

Profit Margin

Sales Growth

Inventory Turnover

Fill Rate

Perfect Order Rate

On Time Delivery Rate

Average Lead Time

Average Delivery Time

Customer Retention Rate

Customer Lifetime Value

Average Order Value

Gross Margin

Return Rate

Dashboard Requirements

Design an executive dashboard in Excel containing:

KPI Cards

Revenue

Profit

Orders

Customers

Growth %

Inventory Value

Delivery Performance

Charts

Monthly Sales Trend

Revenue by Region

Profit by Category

Top 10 Products

Pareto Analysis

Waterfall Chart

Heat Map

Inventory Trend

Supplier Performance

Delivery Performance

Excel Skills Required

The analysis should require the use of:

Pivot Tables

Pivot Charts

XLOOKUP

INDEX & MATCH

SUMIFS

COUNTIFS

AVERAGEIFS

IF

IFS

Nested IF

TEXT Functions

Date Functions

Conditional Formatting

Data Validation

Drop-down Lists

Slicers

Timelines

Dynamic Charts

Excel Tables

Power Query (optional)

Deliverables

Generate:

1. Business Case Study

2. Company Background

3. Dataset Description

4. Data Dictionary

5. Business Questions

6. KPIs

7. Dashboard Layout

8. Step-by-step Analysis Guide

9. Executive Insights

10. Business Recommendations

11. Interview Questions based on the project

12. Portfolio Project Summary suitable for GitHub and LinkedIn

---

Difficulty Level

Allow the user to choose one of the following:

Beginner

Intermediate

Advanced

Expert

Industry Options

Support multiple industries, including:

Supply Chain & Logistics

E-commerce

Retail

Manufacturing

Healthcare

Banking

Finance

Human Resources

Marketing

Telecommunications

Aviation

Hospitality

Oil & Gas

Education

FMCG
```

## 跑完会差在哪

### A：裸跑

仅 Codex：本条没有跑 A 臂，没有裸跑对照。

### B：加上 Prompt

> 生成虚构公司供应链案例包（CASE_STUDY.md、Orders/Inventory/Customers CSV、数据字典、xlsx、zip），15,451 行数据、24 个业务问题、KPI 与面试题齐全；自报透视表未预建

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
