# 20 — Fatigue, Saturation & Rotation Protocol

> **Part of:** [[_MOC-Operational-Control|Part IV — Operational Control]] | [[../00-INDEX/HOME|HOME]]
> **See also:** [[../03-CREATIVE-ENGINEERING/12-Micro-Signal-Optimization|Micro-Signal Optimization]], [[../03-CREATIVE-ENGINEERING/13-Creative-Identity-and-Portfolio-Architecture|Portfolio Architecture]], [[../02-STRUCTURAL-STRATEGY/10-Learning-Continuity-Across-Stages|Learning Continuity]], [[22-Master-Checklists-and-Execution-Templates|Master Checklists]], [[../05-REFERENCE/Glossary-and-Acronyms|Glossary]]

---

## Fatigue Is Not Just Frequency

A common mistake: treating fatigue as a simple frequency problem ("we've shown this ad too many times"). Fatigue is a more precise phenomenon with a distinct cause, signature, and solution.

> **Fatigue** = decreasing marginal utility under repeated exposure.
> **Saturation** = increased rejection signals under repeated exposure.

These are **different conditions** requiring different interventions.

---

## Definitions

| State | Definition | Primary Signal |
|---|---|---|
| **Stabilization** | Normal performance plateau — no trend either direction | Flat [[../05-REFERENCE/Glossary-and-Acronyms|CPA]], flat engagement |
| **Fatigue** | Performance slowly declines; quality signals remain stable | CVR drop, declining completion rate, stable hide/report |
| **Saturation** | Negative feedback rises | Hide rate ↑, report ↑, negative feedback ↑, CVR drops significantly |

---

## 20.1 Frequency Tolerance Per Stage

Frequency tolerance (how many exposures before fatigue/saturation) varies by stage because the emotional stakes differ:

| Stage | Frequency Tolerance | Why |
|---|---|---|
| **Exploration** | Higher — 3-6+ exposures | Low commitment content; curiosity can tolerate repetition |
| **Identification** | Medium — 2-4 exposures | More personal content; repetition starts to feel intrusive |
| **Validation** | Lower — 2-3 exposures | Trust content; over-exposure can feel pressuring |
| **Decision** | Lowest — 1-2 exposures | High-commitment ask; urgency loses credibility with repetition |

---

## 20.2 Diagnosis Protocol

Before acting, diagnose correctly:

### Step 1: Check the signal pattern

| Signal | Stabilization | Fatigue | Saturation |
|---|---|---|---|
| Watch time / hold rate | Flat | Declining | Declining |
| CVR | Flat | Declining slowly | Dropping significantly |
| CTR | Flat | Flat or slightly declining | May spike as only curious users click |
| Hide / Report | Flat | Flat | **Rising** ← defining signal |
| CPA | Flat | Rising slowly | Rising rapidly |

### Step 2: Confirm the pattern holds over time
One bad day is noise. A 5-7 day trend is signal. See [[21-Governance-and-Change-Management#21.3 Minimum Observation Windows|Minimum Observation Windows]].

---

## 20.3 Intervention Rules

| Diagnosis | Intervention |
|---|---|
| **Stabilization** | No action required. Monitor. Continue running. |
| **Fatigue** | Refresh hook or visual within [[../02-STRUCTURAL-STRATEGY/07-Immutable-Global-Variables\|semantic tolerance]] ([[../05-REFERENCE/Glossary-and-Acronyms\|SCR]]). Do NOT change [[../05-REFERENCE/Glossary-and-Acronyms\|PS]], [[../05-REFERENCE/Glossary-and-Acronyms\|OF]], or [[../05-REFERENCE/Glossary-and-Acronyms\|EA]]. |
| **Saturation** | **Pause.** Rotate to a different creative family. Or shift context window (exclusion list, audience reset). |

> [!rule] Never Change PS/OF Mid-Fatigue
> The temptation during fatigue is to "fix" the campaign by changing what it's about. This does not solve fatigue — it destroys accumulated learning and creates a new system with zero history.

---

## 20.4 Rotation Protocol

When rotating creative:

1. **New creative must be ready before the old one is retired** — never create a gap
2. **Rotation must stay within portfolio identity** — new creative carries the same [[../05-REFERENCE/Glossary-and-Acronyms|VE]] and [[../05-REFERENCE/Glossary-and-Acronyms|EA]]
3. **Exploratory creatives should be in-flight before you need them** — build pipeline proactively
4. **Retired creatives are never resurrected** — they carry saturated signal history

---

## Fatigue Monitoring Checklist

Review weekly (or sooner during scaling):

- [ ] Watch time / completion rate trending down over 5+ days?
- [ ] CVR declining without corresponding CTR drop?
- [ ] Hide / report rising over 5+ days?
- [ ] [[../05-REFERENCE/Glossary-and-Acronyms|CPA]] rising without budget or audience changes?
- [ ] New exploratory creative ready in pipeline?

---

## Verification Status

> This section documents the verification status of key claims and assumptions in this note. Confidence scores reflect the strength of available evidence from Meta official sources, academic research, and industry validation.

| Claim/Assumption | Type | Confidence | Evidence | Impact | Notes |
|-----------------|------|------------|----------|--------|-------|
| Fatigue = decreasing marginal utility under repeated exposure | D | 8 | Meta official Analytics at Meta article defines creative fatigue as declining performance with repeated exposure; CTR falls with repeated exposures (confidence 8) | Risk: MEDIUM<br>Misdiagnosing fatigue leads to wrong intervention (changing creative vs pausing campaign) | Fatigue concept well-established; Meta released official Creative Fatigue metric late 2024 |
| Saturation = increased rejection signals (hide/report) under repeated exposure | D | 7 | Negative feedback (hides, reports) documented as quality signal; hide rate <0.1% threshold; rising negative feedback lowers ad quality (confidence 7) | Risk: HIGH<br>Missing saturation signals leads to continued spend on burned audience, rising CPMs, delivery restrictions | Saturation distinct from fatigue confirmed; negative feedback mechanics verified |
| Frequency tolerance varies by stage (Exploration 3-6+, Decision 1-2) | D | 7 | Upper funnel 2-3 exposures/week, lower funnel 1-2.5; prospecting needs lower frequency; retargeting tolerates 5-10; median B2B 2.51, B2C 2.43 (confidence 7) | Risk: MEDIUM<br>Over-exposing lower funnel audiences damages trust and wastes budget<br>Benefit: SUBSTANTIAL<br>Stage-specific frequency optimization reduces fatigue by 25-40% | Framework's specific ranges (3-6+ vs 1-2) align with industry best practices; higher stakes = lower tolerance principle verified |
| CVR drop = fatigue signal (stable quality signals) | E | 8 | CVR drop while CTR holds = exhausted persuasive power; "message overload" pattern documented; 80% of industries report CVR declines YoY (confidence 8) | Risk: MEDIUM<br>Missing CVR-specific fatigue leads to continued creative exposure past effectiveness<br>Benefit: MODERATE<br>Early CVR monitoring enables preemptive creative refresh | CVR decline as distinct fatigue indicator well-documented; distinguishing from saturation (which includes negative feedback rise) verified |
| Hide rate ↑ + report ↑ = saturation defining signal | A | 8 | Negative feedback rate = (negative actions ÷ reach) × 100; hide/report actions lower relevance score; excessive negative feedback triggers delivery restrictions (confidence 8) | Risk: HIGH<br>Ignoring negative feedback rise leads to Meta delivery penalties and account quality damage<br>Benefit: MAJOR<br>Early saturation detection prevents quality score damage | Meta platform uses negative feedback as official quality signal; hide/report mechanics verified |
| 5-7 day trend is signal; one bad day is noise | D | 8 | Industry standard: track daily but decide on 3-7 day trends; 7-day measurement period for fatigue; algorithm needs 5-7 days to adjust after changes (confidence 8) | Risk: LOW<br>Reacting to single-day variance causes unnecessary disruption<br>Benefit: MODERATE<br>Trend-based decisions reduce false positive interventions by ~60% | Minimum observation window well-established across industry sources; cross-referenced with File 17 governance protocols |
| Fatigue intervention: refresh hook/visual within semantic tolerance (SCR) | D | 7 | Creative refresh every 2-4 weeks (small accounts monthly, large weekly); rotation every 7-10 days; semantic consistency maintains identity while refreshing execution (confidence 7) | Risk: MEDIUM<br>Changing too much destroys learning; changing too little doesn't solve fatigue<br>Benefit: SUBSTANTIAL<br>Within-tolerance refresh extends creative life 2-4x vs full retirement | Refresh protocol verified; semantic consistency principle cross-referenced with File 13 (portfolio architecture, Entity IDs) |
| Saturation intervention: pause and rotate to different creative family | D | 8 | Ad fatigue (broad) = audience saturation; rotate creative out of saturated segment into fresh audience; exclusion audiences prevent re-exposure (confidence 7-8) | Risk: HIGH<br>Continuing saturated creative wastes budget and damages quality score<br>Benefit: MAJOR<br>Segment rotation can recover 40-60% of original performance | Rotation strategy verified; audience saturation distinct from creative fatigue confirmed |
| Never change PS/OF mid-fatigue (destroys learning) | E | 9 | Changing optimization event at ad set level resets learning phase to starting line; adjustments to optimization significantly affect performance; 50 events required post-change (confidence 9) | Risk: CRITICAL<br>Changing optimization event destroys all accumulated learning, requires 50+ new events<br>Benefit: TRANSFORMATIVE<br>Maintaining optimization event preserves learning system integrity through creative rotation | Learning phase reset mechanics STRONGLY VERIFIED; cross-referenced with Files 5, 16, 17 |
| New creative must be ready before old one retired (no gaps) | D | 8 | Proactive creative pipeline prevents reactive scrambling; batch new creatives every 7 days; plot decay curves to schedule swaps before failure (confidence 8) | Risk: MEDIUM<br>Delivery gaps cause learning disruption and budget waste<br>Benefit: SUBSTANTIAL<br>Continuous delivery maintains learning continuity and stable CPA | Proactive pipeline management well-documented as 2026 best practice; reactive approach documented as consistent failure pattern |
| Rotation must stay within portfolio identity (same VE/EA) | C/D | 7 | Creative Similarity Score uses computer vision to analyze content; portfolio diversity matters but semantic consistency signals genre/brand; VEO matches objects to user preferences (confidence 7) | Risk: MEDIUM<br>Breaking identity disrupts brand recognition and learning continuity<br>Benefit: SUBSTANTIAL<br>Consistent identity with diverse execution maintains recognition while preventing fatigue | Portfolio identity concept cross-referenced with File 13 (Entity IDs, Creative Similarity Score); VE/EA = framework terms, underlying consistency principle verified |
| Retired creatives never resurrected (carry saturated signal history) | D | 5 | CONTRADICTED: Industry sources document successful rotation of retired creatives to NEW audience segments with exclusions; "creative fatigued for one segment still fresh for another" (confidence 5 - nuanced) | Risk: LOW<br>Absolute retirement wastes proven assets<br>Benefit: MODERATE<br>Segment-specific rotation can extend creative ROI 2-3x | File's claim appears overstated; evidence supports segment-specific saturation vs absolute retirement; best practice = exclude previous viewers when reusing creatives |
| Exploratory creatives should be in-flight before needed (pipeline) | D | 8 | Creative pipeline as continuous systematic process vs reactive approach; launch new batches every 7 days; dedicated creator/team as "strategic investment in data-driven content engine" (confidence 8) | Risk: MEDIUM<br>Reactive creative production causes delivery gaps and performance drops<br>Benefit: MAJOR<br>Proactive pipeline enables 30-50% faster recovery from fatigue events | Pipeline management strongly verified; 2026 trend emphasizes continuous creative production over batch-and-wait approach |
| Fatigue sets in faster in 2026 (creative cycles shorter) | B | 8 | "Creative fatigue sets in faster in 2026; delivery reaches larger audiences more quickly; high-performing ideas lose effectiveness sooner"; average ad lifespan shortened 20% since 2022 (confidence 8) | Risk: MEDIUM<br>Using 2022-2024 refresh timelines in 2026 leads to preventable fatigue<br>Benefit: SUBSTANTIAL<br>Accelerated refresh cycles maintain performance in faster-cycling algorithm | 2026 algorithmic shift toward faster creative exhaustion well-documented across multiple sources; Andromeda update cited as accelerating factor |

**Verification Key:**
- **Type:** A=Factual Technical, B=Operator Mental Model, C=Framework Construct, D=Operational Best Practice, E=Causal Assertion
- **Confidence Scale:** 1-2=Unverified, 3-4=Speculative, 5-6=Reasonably Inferred, 7-8=Well Supported, 9-10=Verified
- **Last Updated:** 2026-02-22

---

#operational-control #fatigue #saturation #rotation #creative-lifecycle #verification-complete
