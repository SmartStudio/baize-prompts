---
title: 文本-两段式股票分析师公司报告-RoshanStocks
category: research-pkm
source: https://x.com/RoshanStocks/status/2056650667289411732
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

# 文本-两段式股票分析师公司报告-RoshanStocks

投资研究长模板：知情者简报 + 深度拆解两半、逐节规则与格式规则，可核对，B148。

## 原始问题

投资研究长模板：知情者简报 + 深度拆解两半、逐节规则与格式规则，可核对，B148。

## 给模型的输入

跑台使用合成输入，原始输入未公开记录（not_recorded）。用你自己的真实材料替换 Prompt 里的占位内容即可。

## 复制这条 Prompt

把你的输入和下面这段 Prompt（源帖原文）放进同一条消息，再发送。

```text
Company name: [Company Name]

Sector: [Sector / Industry]

You are a equity analyst. Produce a structured investor-grade analyst report on this company in EXACTLY TWO HALVES as described below. Auto-adjust every section to the company's actual business model, sector dynamics, and available disclosures. Do not produce a generic answer for any section. Every claim must be specific, quantified where possible, and peer-linked.

────────────────────────────────────────

HALF 1 — THE INFORMED INVESTOR BRIEF

────────────────────────────────────────

H1.0 — COMPANY HISTORY (max 5 bullets)

- Founded [year] — original business model in one line
- Key structural pivot(s): product / geography / technology / ownership
- What is fundamentally different today vs 5 years ago?
- One-line on promoter / key ownership change if it altered business direction

Rule: Only include changes that materially altered business economics. No storytelling.

H1.1 — WHAT DOES THIS COMPANY DO (Kid-Friendly, max 10 bullets)

- Explain the business in plain language — no jargon, no abbreviations
- Who are its customers (in simple words)?
- How does it make money?
- Name its 2–3 main business segments in plain words
- One line on its scale / relevance

Rule: A smart 14-year-old must understand after reading this.

H1.2 — LAST QUARTER / LATEST RESULTS SNAPSHOT

- Revenue, EBITDA, PAT: absolute number + YoY % + QoQ % (one line each)
- What surprised vs market expectations? (positive and negative)
- Which specific segment drove the quarterly delta
- 1–2 most important things from management commentary
- Balance sheet / cash flow flag if material
- One-line verdict: did the investment thesis hold or get dented?

Rule: Only mention what changes the investment view.

H1.3 — NEXT 1–2 QUARTERS — WHAT TO EXPECT

- Revenue trajectory: flat / accelerating / decelerating — and specific reason
- Margin trajectory: expansion or compression — with specific driver named
- One key event to watch (capacity commissioning / order conversion / regulatory trigger)
- One risk that could disappoint next quarter
- Where your view diverges from consensus (if it does), and why

Rule: Frame as specific triggers only.

────────────────────────────────────────

HALF 2 — FULL COMPANY DEEP DIVE

────────────────────────────────────────

2.1 — BUSINESS SEGMENTS & ECONOMICS

- List each segment: what it makes/does, who it sells to
- For each segment: EBITDA margin range OR per-unit economics (₹/ton / ₹/unit / %)
- Cyclicality: project-based / recurring / spot-priced per segment
- Certifications / regulatory approvals that create entry barriers per segment
- Where is this company stronger or weaker than peers — per segment 

2.1 — BUSINESS SEGMENTS & ECONOMICS

For each segment list the following in order:

A. WHAT IT DOES & WHO IT SELLS TO

   - Product / service description in one line
   - Named customers, grouped by segment (not a flat list)
   - After the customer list: one line on what having these customers signals
     (approval depth / switching cost / margin quality / revenue visibility)

   Example format:

   Aerospace — Airbus, Boeing, Dassault, HAL, Spirit AeroSystems
   → Signals: AS9100 + NADCAP certified, program-linked revenue, avg. tenure 5+ yrs

   Hydraulics — Cummins, JCB, John Deere, Mahindra, Eicher
   → Signals: IATF 16949 certified, annual contract + spot, higher volume / lower margin

B. CERTIFICATIONS & APPROVALS (only barriers, not vanity badges)

   For each certification: [Name] — [one line: who you cannot sell to without it]

   Examples of format:

   - AS9100 Rev D — cannot supply Boeing, Airbus, Lockheed Martin, HAL without this
   - NADCAP (Heat Treat / NDT) — process-level approval for flight-critical parts; ~30 Indian holders
   - IATF 16949 — mandatory for Tier 1 supply to global auto OEMs
   - USFDA facility approval — each plant approved separately; 2–4 yr cycle; unlocks US pharma pricing
   - SQAE / DRDO vendor registration — mandatory for Indian defence supply; 2–5 yr approval cycle
   - R2 / e-Stewards (recycling) — required by ESG-conscious global buyers of recycled content

   Rule: Skip ISO 9001 unless a peer lacks it. Only list certifications that restrict competition.

C. IP, TECHNOLOGY & PROPRIETARY KNOW-HOW

   - Patent count + jurisdiction (India / US / EU) — compare vs peers
   - Proprietary process or formulation (if any) — one line on what it enables
   - Licensed technology source + expiry risk (if licensed from a third party)
   - Co-development / JDA with customer — signals technical credibility + future program lock-in
   - Design capability: does company design the part or manufacture to customer drawing?
     (Design capability = pricing power + stickiness vs job-shop = commoditised)
   - R&D spend % of revenue — compare vs peers and sector norm

D. AWARDS & VENDOR STATUS (only commercially meaningful ones)

   - Preferred / Strategic Vendor designation from named OEM — what it means for order flow
   - Sole-source designation (if any) — the highest form of customer lock-in
   - Approved Vendor List (AVL) inclusions — prerequisite to quote; not trivial to achieve

   Skip: CSR awards, generic industry rankings, export certificates unless tied to revenue proof

E. CAPEX QUALITY & ASSET PROFILE

   - Key equipment OEM / origin (German / Japanese / domestic) — signals capability ceiling
   - Automation / robotics level vs peers — impact on per-unit cost and quality consistency
   - Cleanroom / controlled environment (if applicable) — hard-to-replicate barrier
   - Tooling ownership vs leased — owned tooling = customer switching cost

F. SEGMENT ECONOMICS

   - EBITDA margin range OR per-unit economics (₹/ton / ₹/unit / %) — quantified
   - Revenue cyclicality: project-based / recurring / spot-priced
   - Where this company is stronger or weaker vs peers — per segment, not overall

2.2 — REVENUE MIX (MANDATORY — MUST QUANTIFY)

- Segment-wise revenue split in %
- Geography split: India domestic / exports / overseas subsidiaries in %
- Top customer concentration (single client %, top-5 % if disclosed)
- How has the mix shifted over 3 years? What drove it?
- Is current mix better-quality or worse vs peers — and why?
- What mix shift is underway and what it implies for blended margins

Rule: Never say "diversified mix." Quantify it. Example: "33% of volumes at ₹28,000/ton EBITDA via overseas ops; 67% domestic at ₹18,000–19,000/ton."

2.3 — PROFITABILITY MIX

- EBITDA margin or per-unit economics per segment — quantified
- Which segment cross-subsidises which
- Blended margin today and directional impact of mix shift
- Peer margin level: name specific peers + specific reason why this company is higher or lower
- One structural reason why the margin difference is durable or at risk

2.4 — OPERATIONS & CAPACITY (skip if not manufacturing / asset-heavy)

- Each major plant: location + what it produces + installed capacity
- Current utilization % per plant or blended
- Which plant drives margins vs which drives volume
- Capex announced: location, quantum, commissioning quarter
- Post-expansion revenue potential at full utilization
- Capacity profile vs peers: who has more, better-located, or flexible capacity

2.5 — COST STRUCTURE

- Top 3 cost heads as % of revenue — quantified
- Raw material sourcing: spot vs contracted vs captive — and margin stability implication
- Fixed vs variable split — margin impact in a 10–15% volume downcycle
- Structural cost advantage vs peers: name it, quantify where possible
- Structural cost disadvantage vs peers: name it, quantify where possible

2.6 — BUSINESS DRIVERS (SPECIFIC TO THIS COMPANY — NOT GENERIC)

- Primary revenue driver: order book / spot volumes / capacity ramp / pricing
- Order book: size, timeline, revenue recognition pace (if applicable)
- Cyclical / structural / program-linked — with 3-year evidence
- Pricing power: pass-through of cost changes — fully / partially / with lag
- Revenue visibility vs peers: quarters locked in

2.7 — GROWTH TRIGGERS (2–3 YEAR VIEW)

- Each trigger: what it is + expected revenue/volume impact in ₹ or %
- Capacity expansion: commissioning quarter, incremental revenue at full utilization
- New segment / geography: market size, addressable share, timeline
- Industry tailwind: market size (₹ Cr / $ Bn, CAGR), company's current and target share
- Order pipeline / government tender / L1 wins (if applicable)
- Is this company better or worse positioned vs peers to capture these — and why

2.8 — RISKS (SPECIFIC TO THIS COMPANY — NOT GENERIC)

- Execution risk: historical slippages, pattern
- Customer concentration: top client %, switching dynamics
- Working capital: D/E, receivable days, cash conversion vs peers
- Margin collapse scenario: which cost or mix change hits EBITDA fastest
- Regulatory / policy / environmental risk: specific rule or body, not generic
- Name one peer that can outcompete on a specific dimension — explain how

Rule: No lazy risks. Name the competitor and the dimension.

────────────────────────────────────────

2.9 — PEER COMPARISON

────────────────────────────────────────

List ALL relevant peers across three tiers. For each peer, give:

  — Company name + exchange:ticker
  — ONE specific dimension where it is Superior / Inferior / Comparable to [Company Name]
  — Quantify: use per-unit economics, margin bps, D/E ratio, debtor days, or capacity numbers
  — Do NOT say "higher margins" — say why: mechanism, mix, geography, integration, feedstock

TIER 1 — CLOSEST INDIAN LISTED PEERS

(Same product, same end-market, direct segment overlap)

List all relevant companies. For each:

  [Company (TICKER)] — Superior/Inferior/Comparable — [one specific quantified dimension of difference and the structural reason behind it]

TIER 2 — BROADER INDIAN LISTED PEERS

(Same sector or adjacent — partial overlap in product, customer, or value chain)

List all relevant companies. For each:

  [Company (TICKER)] — Superior/Inferior/Comparable — [one specific quantified dimension of difference and the structural reason behind it]

TIER 3 — INTERNATIONAL / GLOBAL PEERS

(Global players in same or adjacent space — for technology, scale, and margin benchmarking)

List all major global players. For each:

  [Company (EXCHANGE:TICKER)] — Superior/Inferior/Comparable — [scale, integration, or margin difference with structural reason]

MANDATORY STANDARD: Do not say "higher margins." Say: "EBITDA/ton is ₹X,000 for [company] vs ₹Y,000 for [peer] because [specific structural reason]." Apply this to every metric: margins, working capital, revenue mix, balance sheet.

────────────────────────────────────────

2.10 — WHAT TO TRACK (5–7 KPIs ONLY)

────────────────────────────────────────

- Only metrics that change investment view if they move
- Tie each KPI to a strength or risk identified above
- Include: volume / realization / mix indicator
- Include: capacity utilization trend
- Include: order book trend (if applicable)
- Include: 1 balance sheet metric (net debt/EBITDA or working capital days)
- Include: 1 industry cycle indicator (commodity price / policy event / demand index)
- State a threshold for each: e.g., "watch if EBITDA/ton falls below ₹X — signals mix deterioration"

────────────────────────────────────────

END WITH:

👉 Key Insight: One line on what STRUCTURALLY drives this company's economics above or below peers.

────────────────────────────────────────

FORMAT RULES:

- Bullet points throughout — no paragraphs
- Bold only section headers
- Include ₹ / $ / % / units — no vague qualitative claims
- Strengths and weaknesses embedded inside each section (not separately)
- Skip inapplicable sections silently
- No repeated information across sections
- Half 1: max 6 bullets per section — short and crisp
- Half 2: detailed, specific, company-unique — not generic template text
```

## 跑完会差在哪

### A：裸跑

仅 Codex：本条没有跑 A 臂，没有裸跑对照。

### B：加上 Prompt

> Codex 单次运行通过人判。

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
