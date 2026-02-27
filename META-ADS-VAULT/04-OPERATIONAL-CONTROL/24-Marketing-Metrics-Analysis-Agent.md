# 24 — Marketing Metrics Analysis Agent (MMAA)

> **Part of:** [[_MOC-Operational-Control|Part IV — Operational Control]] | [[../00-INDEX/HOME|HOME]]
> **See also:** [[23-LTV-and-Unit-Economics|LTV & Unit Economics]], [[17-Budget-Variance-and-Stability|Budget & Stability]], [[19-Competitive-Density-and-Marginal-CPA|Marginal CPA]], [[../02-STRUCTURAL-STRATEGY/09-Cognitive-Stages-and-Optimization-Contracts|Cognitive Stages]], [[../05-REFERENCE/Glossary-and-Acronyms|Glossary]]

---

## From "Algorithmically Optimized" to "Economically Sustainable"

The **Marketing Metrics Analysis Agent (MMAA)** is Sub-System 2.11 of GrowFu v3, designed to bridge the gap between Meta platform performance metrics and business unit economics.

**Purpose:** Assess product/service viability through [[../05-REFERENCE/Glossary-and-Acronyms|LTV]], [[../05-REFERENCE/Glossary-and-Acronyms|CAC]], and CAC:LTV ratios, preventing unprofitable campaigns from launching and detecting viability degradation post-launch.

> [!rule] Core Value Proposition
> Shift from "**Is this campaign performing well?**" (Meta platform metrics) to "**Is this campaign profitable?**" (business unit economics).

---

## 24.1 The Viability Gap

### What Existing GrowFu Sub-Systems Provide:

| Sub-System | What It Tells You |
|------------|-------------------|
| Learning Phase Manager | Is campaign accumulating enough events to exit learning? |
| Creative Intelligence System | Is creative fatigued or saturated? |
| Budget & Scaling Optimizer | What CPA can we expect at scaled budget? |
| Attribution & Signal Quality Monitor | Is signal quality degrading? |
| Reporting & Insights Engine | How is the campaign performing on Meta? |

### What's Missing: Economic Viability

None of the existing sub-systems answer:
- ❌ Is this campaign **profitable** given our product economics?
- ❌ What is the maximum sustainable CAC we can afford?
- ❌ Should we scale this campaign or will scaling destroy value?
- ❌ Is our CAC:LTV ratio healthy or approaching break-even?

**The Gap:** You can have a campaign with stable [[../05-REFERENCE/Glossary-and-Acronyms|CPA]] at $150, exiting learning phase successfully, with no creative fatigue, that the system recommends scaling - **while losing money on every customer acquired**.

---

## 24.2 MMAA Architecture

### Core Components

```
Marketing Metrics Analysis Agent (MMAA)
│
├─ 1. Pre-Launch Viability Analyzer
│   ├─ LTV Estimation Engine
│   ├─ Viable CAC Ceiling Calculator
│   ├─ Industry Benchmark Aggregator
│   └─ GO/CAUTION/NO-GO Decision Engine
│
├─ 2. Post-Launch Monitoring Engine
│   ├─ Real-Time CAC Calculator (stage-aware)
│   ├─ Learning Phase Filter (steady-state CAC only)
│   ├─ Viability Status Tracker (HEALTHY/WARNING/CRITICAL)
│   └─ Alert Engine
│
├─ 3. Unit Economics Intelligence Synthesizer
│   ├─ Multi-Stage Cumulative CAC Tracker
│   ├─ LTV Realization Tracker (business data integration)
│   ├─ Contribution Margin Calculator
│   └─ CAC:LTV Ratio Monitor
│
├─ 4. Viability Decision Engine
│   ├─ Threshold Comparison Logic
│   ├─ Trend Analysis (improving/stable/degrading)
│   ├─ Expansion Physics Detector
│   └─ Governance Trigger (auto-pause on CRITICAL)
│
└─ 5. Strategic Recommendation Generator (LLM-powered)
    ├─ Claude Opus 4.6 (nuanced viability reasoning)
    ├─ Optimization Priority Ranker
    └─ Executive Insight Generator (GPT-4)
```

---

## 24.3 Integration with GrowFu v3 Sub-Systems

MMAA integrates with all 10 existing sub-systems:

### 1. Campaign Definition Engine → Pre-Launch Gate

**Integration Type:** Synchronous blocking gate
**Purpose:** Prevent unprofitable campaigns from launching

**Flow:**
```
User completes 9 Immutable Variables (PS, OF, BR, CS, VE, EA, AL, CTA-R, SCR)
    ↓
Campaign Definition Engine: Variables validated
    ↓
MMAA: Pre-Launch Viability Assessment
    ├─ User provides: LTV estimate, confidence score
    ├─ MMAA calculates: Viable CAC ceiling
    ├─ MMAA estimates: Expected CPA for cognitive stage
    ├─ MMAA determines: GO / CAUTION / NO-GO
    ↓
Campaign Definition Engine:
    ├─ GO → Proceed with campaign creation
    ├─ CAUTION → Proceed with warnings + conservative budget
    └─ NO-GO → Block campaign creation, recommend pivot
```

**Data Exchange:**
- **MMAA receives:** PS, OF, BR, CS (cognitive stage), VE, EA, estimated budget, optimization event
- **MMAA provides:** Viability status, viable CAC ceiling, risk factors, recommendations

---

### 2. Budget & Scaling Optimizer ↔ Viability-Informed Scaling

**Integration Type:** Bidirectional
**Purpose:** Ensure scaling stays within unit economics constraints

**Flow:**
```
Budget Optimizer: Recommends scaling action (20% budget increase)
    ↓
MMAA: Check current CAC utilization
    ├─ CAC < 70% ceiling → Approve scaling
    ├─ CAC 70-85% ceiling → Freeze scaling (WARNING zone)
    └─ CAC > 85% ceiling → Deny scaling + recommend optimization
    ↓
Budget Optimizer:
    ├─ Approved → Execute scaling
    └─ Denied → Hold current budget, prioritize optimization
```

**Data Exchange:**
- **MMAA receives:** Predicted CPA at scaled budget, scaling percentage, timeframe
- **MMAA provides:** Scaling approval/denial, viability margin, safe budget ceiling

**Expansion Physics Integration:**
- MMAA queries Budget Optimizer for recent scaling history (last 7-14 days)
- If CAC rising **during active scaling** → Diagnose as expansion physics (expected)
- If CAC rising **without scaling** → Diagnose as fatigue/saturation (problematic)
- Cross-reference [[19-Competitive-Density-and-Marginal-CPA|File 19]] mechanics

---

### 3. Attribution & Signal Quality Monitor → Performance Data Stream

**Integration Type:** Upstream provider (real-time stream)
**Purpose:** Provide actual CPA, CVR, and spend data for CAC calculation

**Flow:**
```
Meta Ads Integration Layer (every 15 minutes)
    ↓
Attribution & Signal Quality Monitor
    ├─ Normalize: CPA, CVR, CTR, spend, conversions
    ├─ Validate: Attribution window, signal quality
    └─ Stream: Kafka topic meta_ads_performance
    ↓
MMAA: Real-Time CAC Calculation
    ├─ Calculate: Actual CAC (spend / conversions)
    ├─ Filter: Learning phase CAC (use steady-state only)
    ├─ Compare: CAC vs. viable ceiling
    └─ Store: Unit economics snapshot (TimescaleDB)
```

**Data Exchange:**
- **MMAA receives:** Actual CPA, CVR, spend, conversions, attribution window, signal quality metrics
- **MMAA provides:** None (consumer only)

---

### 4. Reporting & Insights Engine ← Viability Dashboard

**Integration Type:** Downstream consumer
**Purpose:** Display viability metrics and unit economics insights

**Dashboard Components:**
```
Viability Overview Card:
├─ Current Status: HEALTHY / STABLE / WARNING / CRITICAL
├─ CAC Utilization: 72% of viable ceiling ($145 / $200)
├─ LTV:CAC Ratio: 2.1:1 (target: 3:1)
├─ Contribution Margin: $55 per customer
└─ Trend: IMPROVING ↑ (+5% week-over-week)

Real-Time Metrics:
├─ Actual CAC: $145 (7-day avg)
├─ Viable CAC Ceiling: $200
├─ Margin to Ceiling: $55 (38% buffer)
└─ LTV Estimate: $450 (confidence: 7/10)

Strategic Recommendations:
├─ [APPROVED] Scaling approved - CAC stable below 75% ceiling
├─ [ACTION] Monitor CVR closely - slight decline detected
└─ [INFO] LTV realization tracking available in 30 days
```

**Data Exchange:**
- **MMAA receives:** None (provider only)
- **MMAA provides:** Viability status, CAC utilization, LTV:CAC ratio, contribution margin, trend, alerts, recommendations

---

### 5. Learning Phase Manager → Context Provider

**Integration Type:** Upstream provider (context)
**Purpose:** Filter out learning-phase CAC noise from viability assessments

**Rationale:**
Learning phase requires ~50 optimization events over 7 days ([[17-Budget-Variance-and-Stability|File 17]], confidence 9). Learning-phase CAC has high variance (20-50% daily swings) and is not representative of steady-state performance.

**Flow:**
```
MMAA receives: Performance data from Meta
    ↓
Learning Phase Manager: Is campaign in learning phase?
    ├─ YES → Days since launch: 10, Events: 35/50
    │   └─ MMAA: Tag as learning phase, do NOT compare to viable ceiling
    │
    └─ NO → Days since launch: 21, Events: 85/50 (exited)
        └─ MMAA: Use steady-state CAC for viability comparison
```

**Data Exchange:**
- **MMAA receives:** Learning phase status, days since launch, event accumulation progress, exit date
- **MMAA provides:** None (consumer only)

**Daily CPA Variance Check ([[17-Budget-Variance-and-Stability|File 17]]):**
- < 15% daily variance: Steady-state confirmed (ready for viability assessment)
- 15-30% daily variance: Transitioning (use with caution)
- \> 30% daily variance: High noise (likely still in learning, delay assessment)

---

### 6. Creative Intelligence System → Optimization Insights

**Integration Type:** Upstream provider (diagnostic context)
**Purpose:** Identify creative-driven CAC degradation (fatigue, saturation)

**Flow:**
```
MMAA: Detects rising CAC (+15% week-over-week without scaling)
    ↓
Creative Intelligence System: Is creative fatigue detected?
    ├─ YES → CTR -8%, completion rate -12%, frequency 3.2
    │   └─ MMAA Diagnosis: Fatigue-driven CAC rise
    │       └─ Recommendation: Rotate creative (File 20 guidance)
    │
    └─ NO → CTR stable, frequency 1.8
        └─ MMAA Diagnosis: Non-creative issue (targeting, saturation, competition)
            └─ Recommendation: Optimize CVR (landing page, offer)
```

**Data Exchange:**
- **MMAA receives:** Creative performance data, fatigue signals (CTR decline, frequency), portfolio status
- **MMAA provides:** None (consumer only)

---

### 7. Governance & Change Management Engine ← Auto-Pause Trigger

**Integration Type:** Downstream consumer (alert receiver)
**Purpose:** Auto-pause campaigns when CAC exceeds CRITICAL threshold

**Flow:**
```
MMAA: Detects CRITICAL viability breach
    ├─ CAC > 85% ceiling for 2+ consecutive days
    └─ CAC $188 exceeds ceiling $180 (104% utilization)
    ↓
MMAA: Generate CRITICAL alert
    ├─ Severity: CRITICAL
    ├─ Alert Type: CAC_EXCEEDED_CEILING
    ├─ Action: PAUSE
    └─ Reason: "CAC $188 exceeds 85% of viable ceiling $180 for 2 days. Unit economics unsustainable."
    ↓
Webhook POST to Governance Engine:
{
  "campaign_id": 12345,
  "action": "PAUSE",
  "reason": "CAC exceeds viable ceiling",
  "triggered_by": "MMAA",
  "severity": "CRITICAL",
  "allow_override": false
}
    ↓
Governance Engine: Auto-pause campaign + log change
```

**Data Exchange:**
- **MMAA receives:** None (provider only)
- **MMAA provides:** CRITICAL alerts with governance actions (PAUSE)

**WARNING Alerts (No Auto-Pause):**
- CAC > 70% ceiling for 3+ days → Webhook to Reporting Engine only
- CAC trending up >10% week-over-week → Dashboard alert only
- No governance action triggered (operator decides)

---

### 8. Meta Ads Integration Layer → Primary Data Source

**Integration Type:** Upstream provider (real-time stream)
**Purpose:** Provide raw performance metrics from Meta Ads API

**Flow:**
```
Meta Ads API (every 15 minutes)
    ↓
Meta Ads Integration Layer
    ├─ Fetch: Campaign performance data
    ├─ Normalize: CPC, CPA, spend, conversions, impressions, CTR, CVR
    └─ Publish: Kafka topic meta_ads_performance
    ↓
MMAA Kafka Consumer: Process metrics
    ├─ Calculate: CAC, CAC utilization, LTV:CAC ratio
    ├─ Determine: Viability status, trend
    ├─ Check: Alert triggers
    └─ Store: TimescaleDB hypertable unit_economics_snapshots
```

**Data Exchange:**
- **MMAA receives:** CPC, CPA, spend, conversions, impressions, CTR, CVR (every 15 minutes)
- **MMAA provides:** None (consumer only)

---

### 9. User States & Cognitive Stages Database → Stage Context

**Integration Type:** Upstream provider (stage mapping)
**Purpose:** Enable stage-aware CAC calculation and stage-specific viability thresholds

**Rationale:**
Campaigns progress through cognitive stages ([[../02-STRUCTURAL-STRATEGY/09-Cognitive-Stages-and-Optimization-Contracts|File 9]]):
Exploration → Identification → Validation → Decision

Each stage has different optimization events and expected CPA ranges.

**Flow:**
```
MMAA: Calculate CAC for campaign
    ↓
User States DB: Which cognitive stage is this campaign?
    ├─ Stage: Identification (LPV optimization)
    └─ Optimization Event: LPV (Landing Page Views)
    ↓
MMAA: Apply stage-specific viability threshold
    ├─ Exploration (ThruPlay): No viability check (awareness investment)
    ├─ Identification (LPV): CPA_LPV < 30% viable ceiling
    ├─ Validation (Lead): CPA_Lead < 60% viable ceiling
    └─ Decision (Purchase): Cumulative CAC < viable ceiling
```

**Multi-Stage CAC Example:**
```
Campaign progresses through all 4 stages:
Exploration: $2,000 spend (awareness)
Identification: $4,000 spend, 50 LPV → CAC_LPV = $80
Validation: $6,000 spend, 30 Leads → CAC_Lead = $333 cumulative
Decision: $8,000 spend, 20 Purchases → CAC_Total = $1,000 cumulative

Viable CAC Ceiling: $800

Viability Checks:
✓ Identification: $80 < $240 (30% of $800) → Early viability signal PASSED
✗ Validation: $333 > $480 (60% of $800) → Qualified viability FAILED
✗ Decision: $1,000 > $800 → Final viability FAILED

Recommendation: Abort Decision stage; product not viable at current pricing
Alternative: Increase pricing to raise LTV above $1,250
```

**Data Exchange:**
- **MMAA receives:** Campaign stage (Exploration/Identification/Validation/Decision), optimization event
- **MMAA provides:** None (consumer only)

---

### 10. Semantic Consistency Engine (Indirect Benefit)

**Integration Type:** Indirect (no direct data exchange)
**Purpose:** Creative consistency enables stable CAC measurement

**Rationale:**
Semantic inconsistency destroys learning continuity, causing CAC variance (cross-reference [[../01-SYSTEM-PHYSICS/02-Embedding-Architecture|File 2]]). By ensuring creative maintains consistent semantic identity (SCR compliance), the Semantic Consistency Engine indirectly supports stable CAC measurement.

**Connection:**
- Inconsistent creative → High learning variance → CAC swings 30%+ daily → Cannot assess viability
- Consistent creative → Stable learning → CAC variance <15% daily → Reliable viability assessment

**Data Exchange:** None (indirect benefit through variance reduction)

---

## 24.4 Pre-Launch Viability Gating

### Purpose
Prevent unprofitable campaigns from launching by comparing estimated CPA to viable CAC ceiling **before** spending any budget.

### Process Flow

**Step 1: User Provides LTV Estimate**
```
Input Form:
├─ LTV Calculation Method:
│   ├─ Method A: Cohort Projection (ARPU, Gross Margin, Churn Rate)
│   ├─ Method B: First-Year Proxy (AOV, Purchase Frequency, Margin)
│   └─ Method C: Industry Benchmark (Vertical, Price Point)
│
├─ LTV Estimate: $450
├─ LTV Confidence Score: 6/10 (medium confidence)
└─ Safety Margin: 40% (moderate)
```

See [[23-LTV-and-Unit-Economics|File 23]] for LTV calculation methodologies.

---

**Step 2: MMAA Calculates Viable CAC Ceiling**
```
Viable CAC Ceiling = LTV × Safety Margin × Confidence Adjustment

Example:
LTV: $450
Safety Margin: 40%
LTV Confidence: 6/10 → Confidence Adjustment: 0.90 (reduce 10%)

Calculation:
Base Ceiling: $450 × 0.40 = $180
Adjusted Ceiling: $180 × 0.90 = $162

Result: Viable CAC Ceiling = $162
```

---

**Step 3: MMAA Estimates Expected CPA**

**Industry Benchmark Approach:**
```
Expected CPA = Median CPA_Industry_Vertical × Stage_Multiplier × Competitive_Density_Factor

Example (B2B SaaS, Identification stage):
Median CPA (B2B SaaS, Identification): $80
Stage Multiplier: 1.2 (Identification higher than Exploration)
Competitive Density: 1.3 (Q4 spike)

Expected CPA = $80 × 1.2 × 1.3 = $124.80
```

**Stage-Specific CPA Ranges (B2B SaaS):**
| Stage | Optimization Event | Typical CPA Range |
|-------|-------------------|------------------|
| Exploration | ThruPlay / Video Views | $15-$40 |
| Identification | LPV (Landing Page Views) | $60-$120 |
| Validation | Lead | $80-$180 |
| Decision | Purchase / Value | $150-$400+ |

---

**Step 4: MMAA Determines Viability Status**

**Decision Matrix:**

| Estimated CPA vs. Viable Ceiling | Status | Action |
|----------------------------------|--------|--------|
| < 50% of ceiling | **GO** | Green light - proceed with confidence |
| 50-80% of ceiling | **CAUTION** | Yellow light - proceed with conservative budget |
| > 80% of ceiling | **NO-GO** | Red light - recommend pivot |

**Example Assessment:**
```
Viable CAC Ceiling: $162
Estimated CPA: $120
Utilization: $120 / $162 = 74%

Status: CAUTION (50-80% range)

Reasoning (Claude Opus 4.6 synthesis):
"LTV of $450 supports viable CAC ceiling of $162 (36% after confidence adjustment).
Estimated CPA of $120 is 74% of ceiling, leaving moderate margin. However, LTV confidence
is only 6/10 (estimated, not historical data), which increases risk. Learning phase
variance (File 17) could push CAC to 80-85% of ceiling. Identification stage CPA of
$120 is within healthy range ($60-$120 for B2B SaaS)."

Risk Factors:
1. LTV is estimated without historical data (MEDIUM severity)
   Mitigation: Implement LTV realization tracking after launch
2. Thin margin to viable CAC ceiling (74% utilization) (MEDIUM severity)
   Mitigation: Start with conservative budget; monitor actual CAC closely
3. Learning phase variance could push CAC above 85% threshold (LOW severity)
   Mitigation: Maintain budget discipline (≤20-30% increases per File 17)

Recommendations:
1. PROCEED with CAUTION - approve Identification stage campaign
2. Target minimum 50 LPV conversions at $120 CPA = $6,000 budget
3. Monitor actual CAC daily; if exceeds $145 (90% ceiling) for 3+ days post-learning,
   pause and optimize CVR
4. Implement LTV realization tracking immediately to validate $450 estimate within 3 months

Confidence: 75/100
```

---

**Step 5: Campaign Definition Engine Action**
```
├─ GO Status → Proceed with campaign creation, recommended budget provided
├─ CAUTION Status → Proceed with warnings, conservative budget, daily monitoring required
└─ NO-GO Status → Block campaign creation, display reasoning + recommendations:
    ├─ "Consider pricing increase to raise LTV"
    ├─ "Move to upper-funnel stage (Identification instead of Validation)"
    └─ "Optimize targeting/creative to reduce estimated CPA"
```

---

## 24.5 Post-Launch Monitoring

### Purpose
Track actual CAC vs. viable CAC ceiling in real-time, detect viability degradation, and trigger alerts/governance actions.

### Real-Time Processing Pipeline

```
Meta Ads API (every 15 minutes)
    ↓
Meta Ads Integration Layer (normalize data)
    ↓
Kafka Topic: meta_ads_performance
    ↓
MMAA Kafka Consumer (Python microservice)
    ├─ Parse: campaign_id, CPC, CPA, spend, conversions, CVR
    ├─ Query: viable_cac_ceiling (from viability_assessments table)
    ├─ Check: Learning phase status (from Learning Phase Manager)
    │   ├─ In learning? → Tag snapshot, do NOT trigger alerts
    │   └─ Exited learning? → Proceed with viability assessment
    ├─ Calculate:
    │   ├─ Actual CAC = spend / conversions
    │   ├─ CAC Utilization = actual_cac / viable_cac_ceiling
    │   ├─ LTV:CAC Ratio = ltv_estimate / actual_cac
    │   └─ Contribution Margin = ltv_estimate - actual_cac
    ├─ Determine:
    │   ├─ Viability Status (HEALTHY/STABLE/WARNING/CRITICAL)
    │   └─ Viability Trend (IMPROVING/STABLE/DEGRADING)
    ├─ Check: Alert triggers (utilization > 70%, trend degrading)
    └─ Store: TimescaleDB hypertable unit_economics_snapshots
    ↓
Alert Dispatcher (if alerts triggered)
    ├─ WARNING → Webhook to Reporting Engine (dashboard alert)
    └─ CRITICAL → Webhook to Governance Engine (auto-pause) + Reporting Engine
```

---

### Viability Status Levels

| CAC Utilization | LTV:CAC Ratio | Status | Action |
|-----------------|---------------|--------|--------|
| < 50% ceiling | > 2:1 | **HEALTHY** | Scale approved; excellent economics |
| 50-70% ceiling | 1.5:1 to 2:1 | **STABLE** | Continue monitoring; optimize when possible |
| 70-85% ceiling | 1.2:1 to 1.5:1 | **WARNING** | Freeze scaling; prioritize optimization |
| > 85% ceiling | < 1.2:1 | **CRITICAL** | Pause campaign; immediate intervention required |

---

### Alert Logic

**WARNING Triggers (Dashboard alerts only):**
```python
def check_warning_alerts(actual_cac, viable_cac_ceiling, days_above_threshold, cac_weekly_trend):
    alerts = []
    utilization = actual_cac / viable_cac_ceiling

    # Approaching ceiling
    if utilization > 0.70 and days_above_threshold >= 3:
        alerts.append({
            "severity": "WARNING",
            "alert_type": "CAC_APPROACHING_CEILING",
            "message": f"CAC at {utilization*100:.0f}% of viable ceiling for {days_above_threshold} days",
            "action": "Freeze scaling; investigate CPA drivers; prioritize CVR optimization"
        })

    # Degrading trend
    if cac_weekly_trend > 0.10:  # 10% increase week-over-week
        alerts.append({
            "severity": "WARNING",
            "alert_type": "CAC_TRENDING_UP",
            "message": f"CAC trending up {cac_weekly_trend*100:.0f}% week-over-week",
            "action": "Diagnose: creative fatigue (File 20), saturation, or competitive density spike (File 19)"
        })

    return alerts
```

**CRITICAL Triggers (Governance auto-pause):**
```python
def check_critical_alerts(actual_cac, viable_cac_ceiling, days_above_threshold):
    alerts = []
    utilization = actual_cac / viable_cac_ceiling

    # Exceeded ceiling
    if utilization > 0.85 and days_above_threshold >= 2:
        alerts.append({
            "severity": "CRITICAL",
            "alert_type": "CAC_EXCEEDED_CEILING",
            "message": f"CAC at {utilization*100:.0f}% of viable ceiling for {days_above_threshold} days. Unit economics unsustainable.",
            "action": "AUTO-PAUSE CAMPAIGN via Governance Engine",
            "governance_action": "PAUSE",
            "governance_reason": f"CAC ${actual_cac:.2f} exceeds 85% of viable ceiling ${viable_cac_ceiling:.2f}"
        })

    return alerts
```

---

### Expansion Physics Detection

**Critical Feature:** Distinguish expected CAC rise during scaling ([[19-Competitive-Density-and-Marginal-CPA|File 19]]) from viability degradation.

**Detection Logic:**
```python
def detect_expansion_physics(campaign_id, cac_history, budget_history):
    """
    Returns:
    - "EXPANSION_PHYSICS" if CAC rise is due to expected scaling dynamics
    - "VIABILITY_DEGRADATION" if CAC rise is problematic
    """

    # Check: Was budget scaled in last 7-14 days?
    recent_scaling_events = get_scaling_events(campaign_id, days=14)

    if len(recent_scaling_events) > 0:
        # Budget was scaled recently
        cac_rise_start = recent_scaling_events[0].date
        cac_rise_duration = days_since(cac_rise_start)
        cac_rise_rate = calculate_rise_rate(cac_history, cac_rise_start)

        # Check: Gradual rise over 7-14 days?
        if 7 <= cac_rise_duration <= 14 and cac_rise_rate < 0.20:  # <20% rise
            # Check: Negative feedback stable?
            negative_feedback_trend = get_negative_feedback_trend(campaign_id)

            if negative_feedback_trend < 0.05:  # <5% increase in hide/report rates
                return {
                    "diagnosis": "EXPANSION_PHYSICS",
                    "reasoning": "Gradual CAC rise over 7-14 days during active scaling. File 19: Expected marginal CPA increase. Negative feedback stable.",
                    "recommendation": "Monitor but continue scaling. Prepare broader framing creative variants.",
                    "suppress_warning": True  # Don't trigger WARNING alert for expansion physics
                }

    # If not expansion physics, it's viability degradation
    return {
        "diagnosis": "VIABILITY_DEGRADATION",
        "reasoning": "CAC rising without recent scaling, or rising too rapidly, or negative feedback increasing.",
        "recommendation": "Diagnose: creative fatigue (File 20), saturation, competitive pressure (File 19). Optimize or pause.",
        "suppress_warning": False
    }
```

**Pattern Recognition:**

| Signal | Expansion Physics | Viability Degradation |
|--------|-------------------|----------------------|
| CAC Trend | Gradual rise 7-14 days | Sudden spike or continuous acceleration |
| Budget Context | Rising **during scaling** | Rising **without scaling** |
| Negative Feedback | Stable (flat hide/report) | Rising (quality penalties) |
| CVR Behavior | Slight decline (expansion) | Significant drop (fatigue) |
| CPC Behavior | Stable or slight rise | Sudden spike (competition) |

---

## 24.6 LLM-Powered Intelligence

### Component 1: Pre-Launch Viability Reasoning Synthesizer

**Model:** Claude Opus 4.6 (best reasoning)
**Purpose:** Generate nuanced viability assessments with framework-aligned reasoning

**Why LLM vs. Rule Engine:**
- Viability requires **context-dependent judgment** beyond simple thresholds
- Same 75% utilization could be GO (high LTV confidence, early-stage) or CAUTION (low confidence, competitive industry)
- LLMs synthesize multiple factors: LTV confidence, stage, industry, competitive density, learning phase status
- Natural language reasoning is more actionable than "Status: CAUTION (75% utilization)"

**Prompt Template:**
```
You are a GrowFu viability analyst. Synthesize the following unit economics data
into a clear viability assessment with reasoning.

DATA:
- LTV: $450 (confidence: 6/10 - estimated, not historical)
- Viable CAC Ceiling: $162 (36% of LTV with confidence adjustment)
- Estimated CPA: $120
- CPA Utilization: 74%
- Cognitive Stage: Identification (LPV optimization)
- Industry: B2B SaaS

FRAMEWORK CONTEXT:
- File 17: Learning phase requires ~50 optimization events over 7 days
- File 17: Daily CPA variance <15% is healthy, >30% is problem
- File 19: Marginal CPA rises with scaling (expansion physics, not failure)
- File 9: Identification stage optimizes for LPV; typical CPA range $60-$120

TASK:
1. Determine viability status (GO, CAUTION, NO-GO)
2. Provide clear reasoning (3-5 sentences)
3. Identify 2-3 key risk factors with severity and mitigation
4. Recommend 2-3 actionable next steps
5. Assign confidence score (1-100)

Output as JSON.
```

**Output Structure:**
```json
{
  "viability_status": "CAUTION",
  "confidence": 75,
  "reasoning": "...",
  "risk_factors": [
    {
      "risk": "LTV is estimated without historical data",
      "severity": "MEDIUM",
      "mitigation": "Implement LTV realization tracking after launch"
    }
  ],
  "recommendations": [
    "PROCEED with CAUTION - approve Identification stage campaign",
    "Target minimum 50 LPV conversions at $120 CPA = $6,000 budget"
  ]
}
```

---

### Component 2: Post-Launch Strategic Recommendation Generator

**Model:** GPT-4 (narrative generation)
**Purpose:** Generate executive-level strategic recommendations based on viability trends

**Prompt Template:**
```
You are a marketing strategist advising on campaign viability.

CURRENT VIABILITY:
- Status: WARNING
- Actual CAC: $155
- Viable CAC Ceiling: $162
- Utilization: 96%
- LTV:CAC Ratio: 1.04:1 (industry benchmark: 3:1 healthy)
- Trend: DEGRADING (CAC +12% week-over-week)

PERFORMANCE DATA (Last 14 Days):
- CPA 7-day avg: $155 (up from $138)
- CVR 7-day avg: 2.1% (down from 2.5%)
- Learning Phase: EXITED (Day 21)
- Budget scaled 3 times in last 10 days (File 17: too aggressive?)

FRAMEWORK CONTEXT:
- File 19: Gradual CPA rise during scaling = expansion physics (expected)
- File 19: Spike within 1-3 days of budget increase = too aggressive scaling
- File 17: Budget increases ≤20-30% per adjustment to avoid learning reset

TASK:
Generate 3-5 strategic recommendations prioritized by impact:
1. What should the operator do IMMEDIATELY?
2. What optimizations would have highest ROI?
3. Should they scale, pause, or optimize in place?
4. Are there business model adjustments to consider (pricing, LTV improvement)?

Format as executive bullet points (non-technical language).
```

**Output Format:**
```
IMMEDIATE ACTIONS REQUIRED:

1. **FREEZE ALL SCALING IMMEDIATELY** - CAC at 96% of viable ceiling with degrading trend.

2. **Roll back last budget increase** - Scaled 3 times in 10 days, violating File 17
   guidance (max 20-30% every 48-72 hours).

3. **Focus on CVR optimization** - CVR dropped from 2.5% to 2.1% (-16%). Improving CVR
   back to 2.5% would reduce CAC from $155 to $130 (-16% improvement).

OPTIMIZATION PRIORITIES (HIGH ROI):

4. **Creative refresh for fatigue** - Campaign is Day 21 post-launch. Rotation recommended.

5. **Budget discipline moving forward** - Once CPA stabilizes below $145, resume scaling
   at maximum 20% increments with 72-hour wait periods.

BUSINESS MODEL CONSIDERATIONS:

6. **Consider pricing increase** - LTV:CAC ratio of 1.04:1 is extremely thin. Even a 10%
   price increase would improve viable CAC ceiling to $178, giving breathing room.
```

---

## 24.7 Data Model

### PostgreSQL Tables

**1. viability_assessments (Pre-Launch)**
```sql
CREATE TABLE viability_assessments (
    id SERIAL PRIMARY KEY,
    campaign_definition_id INTEGER REFERENCES campaign_definitions(id),
    assessment_date TIMESTAMP DEFAULT NOW(),

    -- LTV Inputs
    ltv_estimate DECIMAL(10,2),
    ltv_calculation_method VARCHAR(255),
    ltv_confidence_score INTEGER, -- 1-10

    -- CAC Calculations
    viable_cac_ceiling DECIMAL(10,2),
    cac_ceiling_ratio DECIMAL(5,2), -- e.g., 0.40 for 40%
    estimated_cpa DECIMAL(10,2),

    -- Viability Decision
    viability_status VARCHAR(20), -- GO, CAUTION, NO-GO
    confidence_score INTEGER, -- 1-100
    reasoning TEXT,
    recommendations JSONB,
    risk_factors JSONB,

    created_at TIMESTAMP DEFAULT NOW()
);
```

**2. unit_economics_snapshots (Post-Launch - TimescaleDB Hypertable)**
```sql
CREATE TABLE unit_economics_snapshots (
    id SERIAL PRIMARY KEY,
    campaign_id INTEGER REFERENCES campaigns(id),
    snapshot_date TIMESTAMP DEFAULT NOW(),

    -- Actual Performance
    actual_cac DECIMAL(10,2),
    actual_cpc DECIMAL(10,2),
    actual_cvr DECIMAL(5,4),
    total_spend DECIMAL(10,2),
    total_conversions INTEGER,

    -- Viability Metrics
    viable_cac_ceiling DECIMAL(10,2),
    cac_utilization DECIMAL(5,2), -- e.g., 0.75 for 75%
    ltv_cac_ratio DECIMAL(5,2),
    contribution_margin DECIMAL(10,2),

    -- Status
    viability_status VARCHAR(20), -- HEALTHY, STABLE, WARNING, CRITICAL
    viability_trend VARCHAR(20), -- IMPROVING, STABLE, DEGRADING

    -- Context
    learning_phase_status VARCHAR(20),
    days_since_launch INTEGER,
    expansion_physics_detected BOOLEAN,

    created_at TIMESTAMP DEFAULT NOW()
);

-- Convert to TimescaleDB hypertable for time-series optimization
SELECT create_hypertable('unit_economics_snapshots', 'snapshot_date');
```

**3. viability_alerts**
```sql
CREATE TABLE viability_alerts (
    id SERIAL PRIMARY KEY,
    campaign_id INTEGER REFERENCES campaigns(id),
    alert_type VARCHAR(50), -- CAC_APPROACHING_CEILING, CAC_EXCEEDED_CEILING, etc.
    severity VARCHAR(20), -- WARNING, CRITICAL
    message TEXT,
    triggered_at TIMESTAMP DEFAULT NOW(),
    resolved_at TIMESTAMP,
    resolution_notes TEXT
);
```

---

## 24.8 Success Metrics

### System Quality Metrics

**Viability Prediction Accuracy (Pre-Launch):**
- **Target:** >80% accuracy
- **Measurement:** % of GO/NO-GO assessments matching actual 30-day profitability

**CAC Forecast Accuracy (Pre-Launch):**
- **Target:** ±15% accuracy
- **Measurement:** Estimated CPA vs. actual steady-state CPA (Day 15-30 average)

**Alert Precision (Post-Launch):**
- **Target:** >70% actionable alerts
- **Measurement:** % of WARNING/CRITICAL alerts leading to operator intervention

### Business Impact Metrics

**Unprofitable Campaign Prevention:**
- **Target:** >90% prevention rate
- **Measurement:** % of campaigns with predicted negative ROI caught pre-launch

**Scaling Safety:**
- **Target:** 0 critical viability breaches during scaling
- **Measurement:** # of campaigns scaled into unprofitable territory

**Time to Viability Decision:**
- **Target:** <20 minutes (pre-launch assessment)
- **Measurement:** Time from LTV submission to GO/CAUTION/NO-GO decision

### Operator Experience Metrics

**Confidence in Launch Decisions:**
- **Target:** >85% confidence score
- **Measurement:** User surveys: "How confident were you in the pre-launch viability assessment?"

**Reduction in Manual Analysis:**
- **Target:** >70% time savings
- **Measurement:** Time spent on manual unit economics calculations before vs. after MMAA

---

## Verification Status

> This section documents the verification status of key claims and assumptions in this note. Confidence scores reflect the strength of available evidence from Meta official sources, industry standards, and framework integration.

| Claim/Assumption | Type | Confidence | Evidence | Impact | Notes |
|-----------------|------|------------|----------|--------|-------|
| MMAA bridges gap between platform metrics and business economics | B | N/A | Operator mental model; business unit economics are external to Meta | Risk: N/A \| Benefit: N/A<br>Framework design principle | Framework construct; addresses business need |
| Pre-launch viability gating prevents unprofitable campaigns | E | 8 | Business unit economics: campaigns with CAC > LTV destroy value; standard financial principle | Risk: HIGH<br>Launching unprofitable campaigns wastes budget<br>Benefit: TRANSFORMATIVE<br>Preventing unprofitable launches saves significant budget | Standard business practice; high business impact |
| Learning-phase CAC filtering reduces false positives | E | 9 | Cross-reference File 17: Learning phase high variance (confidence 9); using noisy CAC creates wrong conclusions | Risk: HIGH<br>False positives cause wrong abort decisions<br>Benefit: MAJOR<br>Steady-state filtering prevents premature abandonment | Verified in File 17; critical for accurate assessment |
| Expansion physics detection prevents panic cuts during scaling | E | 8 | Cross-reference File 19: Marginal CPA rises with scaling (confidence 8); gradual rise during scaling = expected | Risk: HIGH<br>Misdiagnosing expansion as failure destroys growth<br>Benefit: MAJOR<br>Correct diagnosis enables continued scaling | Verified in File 19; prevents operator error |
| Stage-aware CAC calculation enables early viability signals | E | 7 | Cross-reference File 9: Multi-stage progression (confidence 8); early-stage viability predicts final economics | Risk: MEDIUM<br>Late-stage viability failure wastes all prior spend<br>Benefit: SUBSTANTIAL<br>Early signals prevent wasted spend on unviable funnels | File 9 integration; framework design |
| Claude Opus 4.6 provides superior reasoning vs. rule engine | A | 9 | LLM reasoning capabilities documented; context-dependent judgment beyond thresholds | Risk: LOW<br>Rule engine provides simpler but less nuanced assessment<br>Benefit: MODERATE<br>LLM synthesis improves operator understanding | LLM capabilities verified; UX improvement |
| Governance auto-pause on CRITICAL prevents financial damage | E | 8 | Business unit economics: CAC > 85% ceiling = near break-even or unprofitable; automation prevents oversight | Risk: MEDIUM<br>Without auto-pause, campaigns can run unprofitably for days<br>Benefit: SUBSTANTIAL<br>Auto-pause limits financial exposure | Standard governance practice; risk management |
| 3:1 LTV:CAC ratio = healthy target benchmark | D | 9 | Cross-reference File 23 (confidence 9); industry standard across SaaS, e-commerce, venture capital | Risk: MEDIUM<br>Wrong ratio targets lead to suboptimal decisions<br>Benefit: SUBSTANTIAL<br>Appropriate ratios guide sustainable growth | Industry-wide consensus; File 23 verification |
| Real-time monitoring enables early viability degradation detection | E | 8 | Time-series monitoring standard practice; early detection prevents significant losses | Risk: HIGH<br>Delayed detection allows prolonged unprofitable operation<br>Benefit: MAJOR<br>Early alerts enable timely intervention | Standard monitoring practice; high business value |
| Multi-stage cumulative CAC reveals full-funnel economics | E | 7 | Cross-reference File 9: Multi-stage progression (confidence 8); cumulative CAC = true acquisition cost | Risk: MEDIUM<br>Single-stage CAC misses upstream awareness costs<br>Benefit: SUBSTANTIAL<br>Cumulative CAC shows true unit economics | File 9 integration; framework design |

**Verification Key:**
- **Type:** A=Factual Technical, B=Operator Mental Model, C=Framework Construct, D=Operational Best Practice, E=Causal Assertion
- **Confidence Scale:** 1-2=Unverified, 3-4=Speculative, 5-6=Reasonably Inferred, 7-8=Well Supported, 9-10=Verified
- **Last Updated:** 2026-02-27

**Important Distinctions:**
- **Business Unit Economics Principles (Type D/E, Confidence 8-9):** Standard financial/business practices (LTV, CAC, viability gating)
- **Meta Framework Integration (Type E, Confidence 7-9):** Cross-referenced with Files 9, 17, 19 for learning phase, expansion physics, stage mechanics
- **Framework Constructs (Type B/C, N/A):** MMAA design principles and operator mental models

**Key Finding:**
MMAA design integrates **verified business unit economics principles** (confidence 8-9) with **verified Meta framework mechanics** from Files 9, 17, 19 (confidence 7-9). Core integration points (learning phase filtering, expansion physics detection, stage-aware CAC) are well-supported by existing framework verification.

---

#operational-control #mmaa #unit-economics #viability #profitability #agent-design #verification-complete
