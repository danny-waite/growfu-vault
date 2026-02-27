	# 23 — LTV & Unit Economics

> **Part of:** [[_MOC-Operational-Control|Part IV — Operational Control]] | [[../00-INDEX/HOME|HOME]]
> **See also:** [[17-Budget-Variance-and-Stability|Budget & Stability]], [[19-Competitive-Density-and-Marginal-CPA|Marginal CPA]], [[24-Marketing-Metrics-Analysis-Agent|MMAA]], [[../02-STRUCTURAL-STRATEGY/09-Cognitive-Stages-and-Optimization-Contracts|Cognitive Stages]], [[../05-REFERENCE/Glossary-and-Acronyms|Glossary]]

---

## Campaign Performance ≠ Campaign Profitability

Meta's optimization system can deliver excellent [[../05-REFERENCE/Glossary-and-Acronyms|CPA]] (Cost Per Action) while the campaign remains **economically unprofitable**. A campaign with stable $150 CPA that appears "optimized" may be losing money if your product's unit economics cannot support that acquisition cost.

This document bridges Meta platform metrics with **business unit economics** - the foundational layer that determines whether campaigns are economically sustainable.

---

## 23.1 The Missing Layer: Business Viability

### What Meta Optimization Tells You:
- ✅ Is the campaign exiting learning phase?
- ✅ Is CPA stable and improving?
- ✅ Is creative performing well?
- ✅ Are quality signals healthy?

### What Meta Optimization Does NOT Tell You:
- ❌ Is this campaign **profitable**?
- ❌ What is the maximum sustainable [[../05-REFERENCE/Glossary-and-Acronyms|CAC]] (Customer Acquisition Cost)?
- ❌ Should we scale, optimize, or abort based on unit economics?
- ❌ Is the [[../05-REFERENCE/Glossary-and-Acronyms|LTV]]:CAC ratio healthy?

> [!rule] Platform Performance ≠ Business Profitability
> You can have algorithmically optimized campaigns that destroy business value. Without unit economics visibility, you operate blind to actual profitability.

---

## 23.2 Core Unit Economics Framework

### The Viability Equation

```
LTV (Lifetime Value) → Determines Viable CAC Ceiling → Governs Campaign Economics

If: CAC < Viable CAC Ceiling → Campaign is economically sustainable
If: CAC > Viable CAC Ceiling → Campaign destroys value
```

### Critical Metrics

| Metric                              | Definition                                                      | Purpose                                            |
| ----------------------------------- | --------------------------------------------------------------- | -------------------------------------------------- |
| **LTV** (Lifetime Value)            | Total gross profit expected from a customer over their lifetime | Sets the ceiling for sustainable acquisition costs |
| **CAC** (Customer Acquisition Cost) | Total marketing spend required to acquire one customer          | The cost you pay to acquire customers via ads      |
| **Viable CAC Ceiling**              | Maximum sustainable CAC given LTV (typically 30-50% of LTV)     | The hard limit - exceed this and you lose money    |
| **LTV:CAC Ratio**                   | LTV divided by CAC                                              | Health indicator (3:1 or better = healthy)         |
| **Contribution Margin**             | LTV minus CAC                                                   | Profit per customer after acquisition costs        |

---

## 23.3 LTV (Lifetime Value) Calculation

**Challenge:** Most campaigns launch without historical LTV data. You must estimate LTV using available information.

### Method A: Cohort-Based Projection (Preferred)

**Formula:**
```
LTV = (ARPU × Gross Margin %) × (1 / Churn Rate)

Where:
- ARPU = Average Revenue Per User (monthly or annual)
- Gross Margin % = Revenue minus COGS (Cost of Goods Sold)
- Churn Rate = % of customers who leave per period
```

**Example (SaaS Subscription):**
```
ARPU: $50/month
Gross Margin: 80% (high for SaaS)
Monthly Churn: 5%

LTV = ($50 × 0.80) × (1 / 0.05)
LTV = $40 × 20 months
LTV = $800

Confidence: 7/10 (requires churn rate estimate)
```

**When to Use:**
- You have some customer cohort data (even partial)
- You can estimate or have measured churn rates
- Subscription or recurring revenue business models

---

### Method B: First-Year LTV Proxy (Conservative)

**Formula:**
```
LTV = Price × Expected Purchases × Gross Margin %

Alternative:
LTV = AOV × Purchase Frequency × Gross Margin % × Expected Lifetime (years)
```

**Example (E-commerce):**
```
Average Order Value (AOV): $120
Expected purchases per year: 3
Gross Margin: 40%

LTV = $120 × 3 × 0.40
LTV = $144 (first-year LTV only)

Confidence: 5/10 (conservative, excludes years 2+)
```

**When to Use:**
- E-commerce or transactional business models
- No cohort data available
- Need conservative baseline (first-year only)
- Early-stage products without retention data

---

### Method C: Industry Benchmark Proxy (Last Resort)

**Formula:**
```
LTV = Industry Median LTV for Vertical × Price Point Adjustment
```

**Example (B2B SaaS):**
```
Vertical: B2B SaaS (small business segment)
Industry Median LTV: $1,200
Your Price Point: $49/month (vs. industry avg $99/month)

LTV = $1,200 × ($49 / $99)
LTV = $1,200 × 0.49
LTV ≈ $590

Confidence: 4/10 (external benchmark, not your data)
```

**When to Use:**
- No internal data at all (pre-launch)
- Validating other calculation methods
- Ballpark estimates for initial planning

**Industry LTV Benchmarks (Illustrative):**
- **B2B SaaS (SMB):** $600-$2,000
- **B2B SaaS (Enterprise):** $10,000-$100,000+
- **E-commerce (Fashion):** $100-$400
- **E-commerce (Subscription Box):** $200-$800
- **Lead Gen (Financial Services):** $500-$5,000
- **Mobile Apps (Subscription):** $50-$300

---

### LTV Confidence Scoring

**Rate every LTV estimate on confidence scale 1-10:**

| Confidence | Data Basis | Reliability |
|------------|-----------|-------------|
| **9-10** | 12+ months cohort data, measured churn, stable metrics | High - trust this LTV |
| **7-8** | 6-12 months cohort data, estimated churn from industry | Good - use with moderate caution |
| **5-6** | 3-6 months partial data, industry benchmarks + estimates | Medium - conservative ceiling needed |
| **4-5** | Industry benchmarks only, educated guesses | Low - very conservative ceiling |
| **1-3** | Wild guesses, no supporting data | Do not use - gather data first |

> [!rule] Low LTV Confidence = Conservative CAC Ceiling
> If LTV confidence is below 7/10, reduce your Viable CAC Ceiling by 10-20% to account for estimation uncertainty. Overconfident LTV estimates lead to unprofitable campaigns.

---

## 23.4 CAC (Customer Acquisition Cost) Calculation

### Standard Formula

```
CAC = Total Ad Spend / New Customers Acquired

Critical: Only count NEW customers (exclude retargeting existing customers)
```

### Stage-Aware CAC (Framework-Specific)

Because campaigns progress through cognitive stages ([[../02-STRUCTURAL-STRATEGY/09-Cognitive-Stages-and-Optimization-Contracts|File 9]]), CAC must be calculated **per-stage** and **cumulatively**.

**Single-Stage CAC:**
```
CAC_Stage = Ad Spend_Stage / Conversions_Stage

Example (Identification stage):
Spend: $6,000
LPV (Landing Page Views): 50
CAC_Identification = $6,000 / 50 = $120 per LPV
```

**Cumulative Multi-Stage CAC:**
```
CAC_Total = (Spend_Exploration + Spend_Identification + Spend_Validation + Spend_Decision) / Conversions_Decision

Rationale: Exploration and Identification spending are "awareness/consideration tax" that enable Decision conversions.

Example (Full funnel):
Exploration: $2,000 (awareness building)
Identification: $4,000 (50 LPVs)
Validation: $6,000 (30 Leads)
Decision: $8,000 (20 Purchases)

CAC_Total = ($2,000 + $4,000 + $6,000 + $8,000) / 20 Purchases
CAC_Total = $20,000 / 20
CAC_Total = $1,000 per customer
```

> [!rule] Stage-Specific Viability Thresholds
> Not all stages have equal viability requirements:
> - **Exploration:** No viability check (awareness investment, no conversion)
> - **Identification:** CPA_LPV < 30% viable CAC ceiling (early signal)
> - **Validation:** CPA_Lead < 60% viable CAC ceiling (qualified signal)
> - **Decision:** CAC_Total < viable CAC ceiling (final profitability)

---

### Learning Phase vs. Steady-State CAC

**Critical Distinction:** Learning-phase CAC is **noisy and unreliable** for viability assessment.

**Learning Phase CAC** (Days 1-14):
```
CAC_Learning = Ad Spend_Days_1-14 / Conversions_Days_1-14

Characteristics:
- High variance (daily CPA swings of 20-50%)
- Not representative of long-term performance
- Influenced by algorithm exploration
```

**Steady-State CAC** (Days 15+):
```
CAC_SteadyState = Ad Spend_Days_15+ / Conversions_Days_15+

Characteristics:
- Lower variance (daily CPA within ±15%)
- Representative of sustainable performance
- Post-learning phase stability
```

> [!rule] Only Compare Steady-State CAC to Viable Ceiling
> Learning phase requires ~50 optimization events over 7 days ([[17-Budget-Variance-and-Stability|File 17]], confidence 9). High variance during learning is normal. Wait for learning phase exit before making viability assessments.
>
> Using learning-phase CAC for viability decisions creates false positives (campaign flagged as unprofitable due to normal learning variance).

**Variance Benchmarks ([[17-Budget-Variance-and-Stability|File 17]]):**
- Daily CPA variance < 15%: Healthy (steady-state)
- Daily CPA variance 15-30%: Warning (potential instability)
- Daily CPA variance > 30%: Problem (likely still in learning or structural issue)

---

## 23.5 Viable CAC Ceiling Calculation

### The Core Formula

```
Viable CAC Ceiling = LTV × Safety Margin × Confidence Adjustment

Where:
- LTV = Lifetime Value from calculation methods above
- Safety Margin = 30-50% of LTV (industry standard)
- Confidence Adjustment = 0-20% reduction based on LTV confidence
```

### Safety Margin Guidelines

| Margin Level | % of LTV | LTV:CAC Ratio | When to Use |
|--------------|----------|---------------|-------------|
| **Conservative** | 30% | 1:3.3 | New products, uncertain LTV, thin margins |
| **Moderate** | 40% | 1:2.5 | Established products, medium LTV confidence |
| **Aggressive** | 50% | 1:2.0 | High-confidence LTV, strong margins, growth mode |

**Industry Context:**
- **B2B SaaS:** Typically 30-40% (long sales cycles, high LTV uncertainty)
- **E-commerce:** Typically 40-50% (faster feedback loops, clearer LTV)
- **Lead Gen:** Typically 30-40% (downstream conversion uncertainty)

---

### Confidence-Based Adjustment

| LTV Confidence | Adjustment | Rationale |
|----------------|-----------|-----------|
| **7-10** (High) | No adjustment (1.00×) | Trust the LTV estimate |
| **5-6** (Medium) | Reduce ceiling 10% (0.90×) | Add safety buffer for uncertainty |
| **3-4** (Low) | Reduce ceiling 20% (0.80×) | Very conservative due to high uncertainty |

---

### Complete Example

**Scenario:**
```
Business: B2B SaaS, small business segment
LTV: $450 (Method A: cohort projection, 6 months data)
LTV Confidence: 6/10 (medium - partial cohort data)
Safety Margin: 40% (moderate)
```

**Calculation:**
```
Step 1: Base ceiling = $450 × 0.40 = $180
Step 2: Confidence adjustment = 0.90× (reduce 10% for medium confidence)
Step 3: Viable CAC Ceiling = $180 × 0.90 = $162

Result: Maximum sustainable CAC is $162
```

**Interpretation:**
- If actual CAC < $162: Campaign is economically viable
- If actual CAC > $162: Campaign is destroying value
- LTV:CAC Ratio at ceiling: $450 / $162 = 2.78:1 (acceptable, slightly below 3:1 ideal)

---

## 23.6 CAC:LTV Ratio Benchmarks

### Industry Standards

| LTV:CAC Ratio | Assessment | Business Health | Action |
|---------------|------------|-----------------|--------|
| **3:1 or better** | EXCELLENT | High profitability, strong unit economics | Scale aggressively |
| **2:1 to 3:1** | GOOD | Acceptable profitability, sustainable | Scale cautiously |
| **1.5:1 to 2:1** | MARGINAL | Thin margins, limited runway | Optimize before scaling |
| **1:1 to 1.5:1** | POOR | Barely profitable or break-even | Urgent optimization needed |
| **< 1:1** | UNPROFITABLE | Losing money per customer | Abort or pivot |

> [!rule] 3:1 Ratio = Healthy Target
> For every $1 spent acquiring a customer, you should generate at least $3 in lifetime gross profit. This allows for:
> - 33% for customer acquisition
> - 33% for operating expenses (salaries, overhead, etc.)
> - 33% for profit/growth reinvestment

---

### Context-Specific Adjustments

**Venture-Backed Growth Mode:**
- Accept 1.5:1 to 2:1 ratios temporarily
- Prioritize growth over immediate profitability
- Plan to improve ratio as scale increases

**Bootstrapped / Cash-Flow Focused:**
- Require 3:1 or better ratios
- Cannot sustain thin margins without external funding
- Profitability is survival

**Category Creation / Early Market:**
- Accept <1:1 ratios in early days (land grab)
- Have clear path to 3:1+ as market matures
- Dangerous without strong balance sheet

---

## 23.7 Expansion Physics vs. Viability Degradation

**Critical Distinction:** CAC naturally rises with scale ([[19-Competitive-Density-and-Marginal-CPA|File 19]], confidence 8), but this does NOT always signal viability failure.

### Expansion Physics (Expected CAC Rise)

**Mechanism:**
```
Scale ↑ → Audience Expansion → Lower Average P(conversion) → Marginal CAC ↑
```

This is **natural scaling economics**, not failure.

**Pattern Recognition:**

| Signal | Expansion Physics | Viability Degradation |
|--------|-------------------|----------------------|
| **CAC Trend** | Gradual rise over 7-14 days | Sudden spike or continuous acceleration |
| **Budget Context** | Rising **during active scaling** | Rising **without scaling** |
| **Negative Feedback** | Stable (flat hide/report rates) | Rising (quality penalties) |
| **CVR Behavior** | Slight decline (audience expansion) | Significant drop (fatigue/saturation) |
| **CPC Behavior** | Stable or slight rise | Sudden spike (competitive pressure) |

**Example (Expansion Physics):**
```
Day 15: Budget $1,000/day, CAC $120
Day 20: Budget $1,200/day (+20%), CAC $135 (+12.5%)
Day 25: Budget $1,440/day (+20%), CAC $145 (+7.4%)
Day 30: Budget $1,728/day (+20%), CAC $155 (+6.9%)

Diagnosis: EXPANSION PHYSICS
- Gradual CAC rise over 15 days during 3 scaling events
- CAC increases are proportional to budget increases
- No negative feedback signals
- Expected behavior per File 19
```

**Example (Viability Degradation):**
```
Day 15: Budget $1,000/day (stable), CAC $120
Day 18: Budget $1,000/day (stable), CAC $145 (+20.8%)
Day 20: Budget $1,000/day (stable), CAC $165 (+13.8%)
Day 22: Hide rate rising 15% week-over-week

Diagnosis: VIABILITY DEGRADATION
- Sudden CAC spike without scaling
- Rising negative feedback (hide rate)
- Likely creative fatigue or saturation
- Requires intervention (creative rotation, optimization)
```

> [!rule] Context Determines Diagnosis
> Same CAC rise pattern can be healthy (during scaling) or problematic (without scaling). Always check:
> 1. Was budget recently increased? (Check last 7-14 days)
> 2. Are negative feedback signals rising? (Hide rate, report rate)
> 3. Is CVR declining beyond expected expansion rates?

---

## 23.8 Viability Status Levels

### Pre-Launch Viability Decision Matrix

Used **before** launching campaigns to gate unprofitable campaigns.

| Estimated CPA vs. Viable Ceiling | Status | Interpretation | Action |
|----------------------------------|--------|----------------|--------|
| **< 50% of ceiling** | GO (Green Light) | Excellent margin for learning variance | Proceed with confidence |
| **50-80% of ceiling** | CAUTION (Yellow Light) | Moderate margin, close monitoring required | Proceed with conservative budget |
| **> 80% of ceiling** | NO-GO (Red Light) | Insufficient margin for profitability | Recommend pricing/positioning pivot |

**Example:**
```
LTV: $450, Viable CAC Ceiling: $162
Estimated CPA (Identification stage): $120

Analysis:
CPA Utilization: $120 / $162 = 74%
Status: CAUTION (50-80% range)

Interpretation:
Moderate margin. Learning phase variance (±15-30%) could push CAC to 85-100% of ceiling.
Proceed with conservative budget, monitor actual CAC closely post-launch.
```

---

### Post-Launch Viability Status Levels

Used **after** campaigns launch to monitor ongoing profitability.

| CAC Utilization | LTV:CAC Ratio | Status | Action |
|-----------------|---------------|--------|--------|
| **< 50% ceiling** | > 2:1 | HEALTHY | Scale approved; excellent economics |
| **50-70% ceiling** | 1.5:1 to 2:1 | STABLE | Continue monitoring; optimize when possible |
| **70-85% ceiling** | 1.2:1 to 1.5:1 | WARNING | Freeze scaling; prioritize optimization |
| **> 85% ceiling** | < 1.2:1 | CRITICAL | Pause campaign; immediate intervention required |

**Alert Triggers:**

**WARNING Alerts:**
- CAC > 70% of viable ceiling for 3+ consecutive days
- CAC trending up >10% week-over-week (without scaling context)
- LTV:CAC ratio falling below 1.5:1

**CRITICAL Alerts:**
- CAC > 85% of viable ceiling for 2+ consecutive days
- CAC exceeding viable ceiling (>100%)
- LTV:CAC ratio below 1.2:1

---

## 23.9 Optimization Priority Framework

When CAC approaches or exceeds viable ceiling, **what should you optimize first**?

### ROI-Based Prioritization

| Optimization Lever | Typical CAC Impact | Effort | Priority Ranking |
|-------------------|-------------------|--------|------------------|
| **Improve CVR** (landing page, offer, targeting) | -15% to -30% CAC | Medium | **HIGH** (biggest bang) |
| **Reduce CPC** (creative refresh, audience expansion) | -10% to -20% CAC | Low-Medium | **MEDIUM** |
| **Increase LTV** (pricing, upsells, retention) | +20% to +50% ceiling | High | **MEDIUM-HIGH** (long-term) |
| **Change Cognitive Stage** (move up-funnel) | -30% to -50% CAC | Low | **HIGH** (if current stage unviable) |

**Example Calculation (CVR Improvement):**
```
Current State:
CPC: $3.50
CVR: 2.0%
CAC: $3.50 / 0.02 = $175
Viable Ceiling: $162
Utilization: 108% (exceeding ceiling)

Scenario: Improve CVR to 2.5% (+25% improvement)
New CAC: $3.50 / 0.025 = $140
New Utilization: $140 / $162 = 86%
CAC Reduction: -20%

Result: CVR improvement of +0.5 percentage points brings CAC from CRITICAL (108%) to WARNING (86%)
```

---

### Decision Tree

```
CAC > Viable Ceiling?
├─ YES → CRITICAL
│   ├─ Check: Creative fatigue? (File 20)
│   │   ├─ YES → Rotate creative immediately
│   │   └─ NO → Check: CVR declining?
│   │       ├─ YES → Optimize landing page / offer
│   │       └─ NO → Check: CPC spiking?
│   │           ├─ YES → Competitive pressure (File 19)
│   │           └─ NO → Consider pricing increase (raise LTV)
│   │
├─ 70-85% of ceiling → WARNING
│   ├─ Freeze all scaling
│   ├─ Prioritize CVR optimization
│   └─ Monitor daily for CRITICAL breach
│
└─ < 70% of ceiling → HEALTHY/STABLE
    └─ Continue monitoring; scaling approved
```

---

## 23.10 Integration with Framework Components

This unit economics layer integrates with existing framework elements:

### File 9: Cognitive Stages → Stage-Aware CAC

**Connection:**
- Each cognitive stage has different optimization events (ThruPlay, LPV, Lead, Purchase)
- Different stages have different expected CPA ranges
- Multi-stage CAC calculation required for full-funnel campaigns

**Application:**
```
Exploration (ThruPlay): $20 CPA → No viability check (awareness investment)
Identification (LPV): $80 CPA → Check: < 30% viable ceiling ($162 × 0.30 = $48.60) → FAIL
Validation (Lead): $150 CPA → Check: < 60% viable ceiling ($162 × 0.60 = $97.20) → FAIL
Decision (Purchase): $1,000 cumulative CAC → Check: < viable ceiling ($162) → FAIL

Diagnosis: Product not viable for full-funnel campaign at current pricing
Recommendation: Focus on Exploration/Identification only (lead gen), or increase pricing 6×
```

---

### File 17: Budget & Stability → Learning Phase Filtering

**Connection:**
- Learning phase requires ~50 optimization events over 7 days (confidence 9)
- Daily CPA variance <15% is healthy, >30% is problem (confidence 7)
- Budget increases ≤20-30% per adjustment to avoid learning reset (confidence 9)

**Application:**
```
Only use steady-state CAC (post-learning) for viability comparisons
Filter out learning-phase CAC noise (Days 1-14)
Ensure campaign has exited learning before making scale/abort decisions
```

---

### File 19: Marginal CPA → Expansion Physics Detection

**Connection:**
- Marginal CPA rises naturally with scaling (confidence 8)
- Gradual rise over 7-14 days during scaling = expected, not failure

**Application:**
```
Context check: Was CAC rise during active scaling?
├─ YES → Likely expansion physics (expected)
│   ├─ Still check: CAC < 85% ceiling? (absolute limit)
│   └─ Recommendation: Prepare broader framing creative variants
└─ NO → Likely fatigue/saturation/competition (problematic)
    └─ Recommendation: Diagnose root cause, optimize or pause
```

---

## 23.11 Common Mistakes & How to Avoid Them

### Mistake 1: Ignoring LTV Uncertainty

**Error:** Using optimistic LTV estimates without confidence scoring

**Consequence:** Viable CAC ceiling set too high → Unprofitable campaigns appear viable

**Fix:**
- Always assign confidence scores to LTV estimates
- Reduce viable ceiling by 10-20% for low-confidence LTV (5/10 or below)
- Track LTV realization over time to validate estimates

---

### Mistake 2: Comparing Learning-Phase CAC to Ceiling

**Error:** Making viability decisions during Days 1-14 of learning phase

**Consequence:** False positives - campaigns flagged as unprofitable due to normal learning variance

**Fix:**
- Wait for learning phase exit (~50 events, typically Day 14-21)
- Only compare steady-state CAC to viable ceiling
- Use daily CPA variance as readiness signal (<15% = ready for assessment)

---

### Mistake 3: Confusing Expansion Physics with Viability Failure

**Error:** Panicking and cutting budgets when CAC rises during scaling

**Consequence:** Destroying growth momentum during healthy expansion economics

**Fix:**
- Always check: Was budget recently increased? (last 7-14 days)
- Gradual CAC rise **during scaling** = expected (File 19)
- Sudden CAC spike **without scaling** = problematic
- Use absolute ceiling (85%) as hard limit even during expansion

---

### Mistake 4: Setting Viable Ceiling Too Aggressively

**Error:** Using 50% of LTV as ceiling when margins are thin or LTV is uncertain

**Consequence:** Campaigns flagged as unprofitable when they're actually acceptable

**Fix:**
- Use conservative 30% ceiling for:
  - New products (no historical data)
  - Low LTV confidence (<6/10)
  - Thin gross margins (<40%)
  - High uncertainty environments
- Only use aggressive 50% ceiling when:
  - High LTV confidence (8+/10)
  - Strong gross margins (>60%)
  - Proven product-market fit

---

### Mistake 5: Ignoring Stage-Specific Viability

**Error:** Judging full-funnel campaigns only by final Decision-stage CAC

**Consequence:** Missing early viability signals that could prevent wasted spend

**Fix:**
- Check viability at each stage:
  - Identification: CPA_LPV < 30% ceiling (early signal)
  - Validation: CPA_Lead < 60% ceiling (qualified signal)
  - Decision: CAC_Total < ceiling (final viability)
- Abort progression to next stage if current stage fails viability check
- Saves budget by catching unviable economics early in funnel

---

## Verification Status

> This section documents the verification status of key claims and assumptions in this note. Since this file introduces **business unit economics** (not Meta platform mechanics), most claims are established financial/business principles rather than Meta-specific mechanics.

| Claim/Assumption | Type | Confidence | Evidence | Impact | Notes |
|-----------------|------|------------|----------|--------|-------|
| LTV = (ARPU × Gross Margin %) × (1 / Churn Rate) formula | A | 10 | Standard SaaS/subscription LTV formula; widely used in finance, venture capital, and unit economics analysis | Risk: N/A \| Benefit: N/A<br>Foundational business metric | Verified calculation method across industry |
| Viable CAC ceiling = 30-50% of LTV | D | 9 | Industry standard; 3:1 LTV:CAC ratio benchmark across SaaS, e-commerce, and venture capital guidance | Risk: HIGH<br>Wrong ceiling leads to unprofitable campaigns<br>Benefit: TRANSFORMATIVE<br>Correct ceiling prevents value destruction | Widely accepted across industries; 3:1 ratio = healthy |
| Learning-phase CAC is noisy and unreliable | E | 9 | Cross-reference File 17: Learning phase requires ~50 events over 7 days (confidence 9); high variance during learning | Risk: HIGH<br>Using learning CAC for viability creates false positives<br>Benefit: MAJOR<br>Steady-state CAC filtering prevents wrong decisions | Verified in File 17; learning variance well-documented |
| Daily CPA variance <15% = healthy, >30% = problem | D | 7 | Cross-reference File 17 (confidence 7); practitioner best practice, not Meta official | Risk: MEDIUM<br>Wrong thresholds miss instability signals<br>Benefit: SUBSTANTIAL<br>Appropriate monitoring enables early intervention | File 17 verification; practitioner consensus |
| Marginal CPA rises with scaling (expansion physics) | E | 8 | Cross-reference File 19 (confidence 8): "Scale ↑ → Audience alignment ↓ → Marginal CPA ↑" | Risk: HIGH<br>Confusing expansion with failure causes panic cuts<br>Benefit: MAJOR<br>Understanding expansion physics prevents destructive interventions | Verified in File 19; expansion economics documented |
| Gradual rise over 7-14 days during scaling = expansion physics | E | 8 | Cross-reference File 19 (confidence 8); timeframe aligns with scaling stabilization period | Risk: HIGH<br>Misdiagnosis causes wrong interventions<br>Benefit: SUBSTANTIAL<br>Correct diagnosis prevents panic during healthy growth | File 19 verification; pattern recognition critical |
| Stage-specific viability thresholds (30%/60%/100% of ceiling) | C | N/A | Framework construct based on cognitive stage progression (File 9) | Risk: N/A \| Benefit: N/A<br>Framework's staged viability assessment | Framework design; underlying stage mechanics verified in File 9 |
| 3:1 LTV:CAC ratio = healthy target | D | 9 | Standard venture capital and unit economics benchmark; "rule of 40" adjacent principle | Risk: MEDIUM<br>Wrong ratio targets lead to suboptimal scaling decisions<br>Benefit: SUBSTANTIAL<br>Appropriate ratios guide sustainable growth | Industry-wide consensus; venture capital standard |
| CVR improvement has -15% to -30% CAC impact | E | 7 | Mathematical relationship: CAC = CPC / CVR; CVR improvements directly reduce CAC proportionally | Risk: LOW<br>Inaccurate impact estimates affect optimization prioritization<br>Benefit: MODERATE<br>Correct estimates guide optimization focus | Mathematical relationship verified; ranges from practitioner data |
| Confidence-based LTV ceiling adjustment (10-20% reduction) | C | N/A | Framework risk management principle for LTV uncertainty | Risk: N/A \| Benefit: N/A<br>Framework's conservative safety mechanism | Framework construct; addresses LTV estimation uncertainty |

**Verification Key:**
- **Type:** A=Factual Technical, B=Operator Mental Model, C=Framework Construct, D=Operational Best Practice, E=Causal Assertion
- **Confidence Scale:** 1-2=Unverified, 3-4=Speculative, 5-6=Reasonably Inferred, 7-8=Well Supported, 9-10=Verified
- **Last Updated:** 2026-02-27

**Important Distinctions:**
- **Business Metrics (LTV, CAC, ratios):** Type A/D, Confidence 9-10 - Standard financial/business principles
- **Meta Integration (Learning phase, expansion physics):** Type E, Confidence 7-9 - Cross-referenced with Files 17, 19
- **Framework Constructs (Stage thresholds, confidence adjustments):** Type C, N/A - Proprietary framework design

**Key Finding:**
Core unit economics principles (LTV formulas, viable CAC ceiling, 3:1 ratio) are **industry standards** (confidence 9-10). Integration with Meta framework mechanics (learning phase filtering, expansion physics detection) is **well-supported** by Files 17 and 19 (confidence 7-9). Framework-specific constructs (stage viability thresholds, confidence adjustments) are proprietary design choices.

---

#operational-control #unit-economics #ltv #cac #viability #profitability #verification-complete
