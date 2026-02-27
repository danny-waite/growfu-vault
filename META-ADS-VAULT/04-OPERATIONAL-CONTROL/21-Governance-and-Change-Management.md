# 21 — Governance & Change Management

> **Part of:** [[_MOC-Operational-Control|Part IV — Operational Control]] | [[../00-INDEX/HOME|HOME]]
> **See also:** [[../02-STRUCTURAL-STRATEGY/10-Learning-Continuity-Across-Stages|Learning Continuity]], [[17-Budget-Variance-and-Stability|Budget & Stability]], [[18-Attribution-and-Feedback-Timing|Attribution Timing]], [[22-Master-Checklists-and-Execution-Templates|Master Checklists]], [[../05-REFERENCE/Glossary-and-Acronyms|Glossary]]

---

## This Section Protects the System from Operator Impulsiveness

The most common source of campaign destruction is not poor creative or poor targeting. It is **premature intervention** — making changes before having sufficient data, or making too many changes at once.

> [!rule] One Variable Change Per Iteration
> Every change resets at least part of the system's prediction confidence. Multiple simultaneous changes make attribution impossible. Govern with discipline.

---

## 21.1 Allowed Changes (Mid-Learning)

### Minor Expression Changes
These stay within [[../05-REFERENCE/Glossary-and-Acronyms|SCR]] and do not alter meaning:
- Hook variation (same thesis, different opening)
- Visual refresh (same message, updated visual)
- Example variation (different case study, same mechanism)

### Context Changes
These adjust delivery parameters without touching the campaign's meaning:
- Attribution window adjustment
- Placement grouping changes
- Audience window adjustment (30-day → 14-day retargeting)

### Budget Changes (with rules)
- Gradual increments ≤ 20-30%
- Only after minimum observation window
- Not during active learning phase instability

---

## 21.2 Forbidden Changes (Mid-Learning)

> [!rule] These Actions Reset Learning
> Do not make these changes during an active learning phase or before the minimum observation window:

| Forbidden Action | Why |
|---|---|
| Changing optimization event | Invalidates all accumulated signal history |
| Changing core thesis / [[../05-REFERENCE/Glossary-and-Acronyms|PS]] or [[../05-REFERENCE/Glossary-and-Acronyms|OF]] | Creates a new system. The old learning is worthless. |
| Changing [[../05-REFERENCE/Glossary-and-Acronyms|EA]] (emotional axis) | Destroys semantic coherence of the creative portfolio |
| Changing cognitive stage | Requires a new campaign — not an edit |
| Drastic budget shifts (> 30%) | Resets pacing confidence and can re-trigger learning phase |
| Adding too many new ads at once | Fragments signal and dilutes learning per creative |

---

## 21.3 Minimum Observation Windows

**Define these before launch.** Do not evaluate before thresholds are met.

| Metric | Minimum Threshold | Notes |
|---|---|---|
| **Impressions** | Define a floor before drawing conclusions | Varies by audience size and stage |
| **Optimization events** | ~50 per ad set (learning phase exit) | This is the most critical threshold |
| **Evaluation period** | Minimum 7 days for stable reading | 14 days preferred for slower-converting stages |
| **Primary KPI** | The single metric that decides the evaluation | Set before launch — do not change mid-evaluation |
| **Diagnostic KPIs** | Secondary metrics to understand *why* | CTR, completion rate, CVR, negative feedback |

> [!rule] Decide Only After Threshold Is Reached
> Evaluating before the threshold is speculation dressed as data. The result is pattern-matching on noise — which leads to changes that destroy the actual signal.

---

## 21.4 Change Log Discipline

For every change made, record:

- Date and time of change
- What was changed
- Why (what signal triggered the decision)
- What outcome was expected
- What was observed (fill in later)

This creates the feedback loop that makes governance improvable over time, and prevents "I think we changed that" ambiguity in post-analysis.

---

## Decision Framework (Before Any Change)

Ask in order:

1. **Have I reached the minimum observation window?** → If no, wait.
2. **Is there a clear signal trend (5+ days), not noise (1-2 days)?** → If no, wait.
3. **Is this an allowed change or a forbidden change?** → If forbidden, do not proceed.
4. **Am I changing one variable or multiple?** → If multiple, split into sequential single changes.
5. **Is the portfolio ready (new creative in pipeline) before I retire the old?** → If no, build first.

---

## Verification Status

> This section documents the verification status of key claims and assumptions in this note. Confidence scores reflect the strength of available evidence from Meta official sources, academic research, and industry validation.

| Claim/Assumption | Type | Confidence | Evidence | Impact | Notes |
|-----------------|------|------------|----------|--------|-------|
| Premature intervention is most common source of campaign destruction | E | 8 | Jon Loomer Digital research: 68% of advertisers make premature adjustments; industry consensus that early edits reset learning | Risk: HIGH<br>Premature changes reset learning phase, transforming temporary instability into permanent underperformance, wasting accumulated signal | Well-documented problem across multiple 2026 sources |
| One variable change per iteration rule | D | 9 | Fundamental A/B testing principle; universal testing methodology; Meta Split Testing designed around isolation | Risk: CRITICAL<br>Multiple simultaneous changes make attribution impossible<br>Benefit: MAJOR<br>Clean attribution enables confident optimization decisions | Scientific method fundamental; cross-referenced from File 14 (confidence 9) |
| Every change resets at least part of system's prediction confidence | B | 8 | Meta learning phase documentation; significant edits reset learning; algorithm must recalibrate after changes | Risk: HIGH<br>Unknowing resets waste previous learning investment, extending time to stability<br>Benefit: SUBSTANTIAL<br>Understanding reset mechanics enables strategic change timing | Verified learning phase behavior |
| Hook/visual/example variations stay within SCR without altering meaning | C | N/A | Framework construct defining "allowed minor changes"; based on semantic consistency preservation | N/A | Framework's own definitional boundary for minor vs. major changes |
| Budget increments ≤ 20-30% recommendation | D | 9 | Meta historical guidance max 30%; 2025-2026 sources: limit to 10-20% per adjustment; >20-30% triggers reset and can raise CPA 25-40% | Risk: HIGH<br>Exceeding threshold resets learning and causes 25-40% CPA spikes<br>Benefit: MAJOR<br>Staying within limits maintains stability during scale | Cross-referenced from Files 16, 17 (confidence 9); strong industry consensus |
| Budget changes only after minimum observation window | D | 8 | Logical extension of 50-event learning threshold; industry best practice to avoid premature intervention | Risk: MEDIUM<br>Early budget changes made on insufficient data waste spend on noise-based decisions<br>Benefit: SUBSTANTIAL<br>Waiting for threshold ensures data-backed scaling decisions | Derived from verified 50-event threshold (File 5, confidence 9) |
| Budget changes not during active learning phase instability | D | 8 | Meta guidance to avoid significant edits during learning; changes compound instability and delay stabilization | Risk: HIGH<br>Changing budget mid-learning extends learning phase indefinitely<br>Benefit: SUBSTANTIAL<br>Waiting for stability exit before scaling prevents performance degradation | Well-documented in 2026 sources as key mistake |
| Changing optimization event invalidates all accumulated signal history | A | 9 | Meta official documentation: changing optimization goal resets learning phase; algorithm must relearn what success looks like | Risk: CRITICAL<br>Destroys weeks of accumulated learning; campaign becomes essentially new<br>Benefit: TRANSFORMATIVE<br>Preserving optimization event maintains all learning investment | Meta platform behavior; cross-referenced from Files 5, 17 |
| Changing core thesis/PS/OF creates new system with worthless old learning | E | 8 | Changing fundamental campaign meaning alters semantic embedding space; prediction heads optimized for different outcome | Risk: CRITICAL<br>Attempting to repurpose campaign wastes budget on incompatible learning<br>Benefit: MAJOR<br>Recognizing need for new campaign prevents futile optimization attempts | Logical extension of verified embedding architecture (File 4, confidence 8) |
| Changing EA destroys semantic coherence of creative portfolio | E | 7 | Creative portfolio operates in consistent emotional embedding space; shifting emotional axis fragments identity | Risk: HIGH<br>Portfolio loses accumulated creative identity signal; Andromeda Entity ID grouping disrupted<br>Benefit: SUBSTANTIAL<br>Emotional consistency accelerates creative learning and identity formation | Built on Andromeda Entity ID mechanics (File 13, confidence 8) |
| Changing cognitive stage requires new campaign | C/E | 7 | Framework rule based on verified stage-optimization alignment; different stages = different audience states = different optimization contracts | Risk: HIGH<br>Forcing stage shift in existing campaign misaligns optimization event with audience readiness<br>Benefit: MAJOR<br>Stage-specific campaigns enable proper optimization event selection | Framework construct built on verified stage mechanics (File 7, confidence 7) |
| Drastic budget shifts (>30%) reset pacing confidence, re-trigger learning | A | 8 | Meta documentation: budget changes >20-30% treated as significant change; triggers learning phase reset; disrupts pacing algorithm | Risk: HIGH<br>Large budget jumps cause extended instability periods and CPA volatility<br>Benefit: SUBSTANTIAL<br>Gradual scaling maintains pacing confidence and prediction accuracy | Multiple 2026 sources confirm 20-30% threshold as critical boundary |
| Adding too many new ads at once fragments signal, dilutes learning | E | 7 | Pre-Andromeda concern; current system (2024+): Andromeda handles multiple creatives better; BUT excessive additions still dilute event density per creative | Risk: MEDIUM<br>Each creative receives fewer events, slowing individual creative optimization<br>Benefit: MODERATE<br>Controlled creative additions ensure sufficient event volume per variation | Nuanced: Andromeda improved multi-creative handling but event density still matters |
| ~50 optimization events per ad set as learning phase exit threshold | A | 9 | Meta official: "about 50" optimization events per ad set per week required to exit learning phase | Risk: CRITICAL<br>Evaluating before 50 events = decisions based on noise, not signal<br>Benefit: TRANSFORMATIVE<br>Waiting for threshold enables confident, data-backed optimization | Cross-referenced from Files 5, 14, 17 (confidence 9); foundational Meta metric |
| 7-day minimum evaluation period | D | 9 | Meta official recommendation: 7-30 days test duration; 7 days minimum industry standard for stable reading | Risk: HIGH<br>Shorter periods capture daily noise rather than stable patterns<br>Benefit: MAJOR<br>Full week captures day-of-week variance and initial learning stabilization | Meta official guidance; cross-referenced from Files 14, 17 (confidence 9) |
| 14 days preferred for slower-converting stages | D | 7 | Practitioner best practice for longer consideration products; allows sufficient conversion lag for attribution | Risk: MEDIUM<br>Judging slow-converting campaigns at 7 days under-counts conversions due to lag<br>Benefit: SUBSTANTIAL<br>Extended window captures delayed conversions, providing accurate performance picture | Logical extension of attribution lag mechanics (File 18, confidence 8) |
| Primary KPI = single metric deciding evaluation | D | 9 | Fundamental best practice: pre-define success metric to prevent p-hacking and selective reporting bias | Risk: HIGH<br>Post-hoc metric selection finds false positives in noise ("Texas sharpshooter fallacy")<br>Benefit: MAJOR<br>Pre-specified metric ensures scientific rigor and honest evaluation | Scientific method requirement; cross-referenced from File 14 (confidence 9) |
| Diagnostic KPIs = secondary metrics to understand "why" | D | 8 | Standard analytical framework: primary metric for decision, diagnostics for understanding causal mechanisms | Risk: LOW<br>Lacking diagnostics limits learning from failed tests<br>Benefit: MODERATE<br>Diagnostics accelerate learning cycle by revealing performance drivers | Industry standard analytical approach |
| Evaluating before threshold = pattern-matching on noise | E | 9 | Statistical principle: insufficient sample size produces high variance; early evaluation mistakes noise for signal | Risk: HIGH<br>Noise-based changes create random walk, never allowing true signal to emerge<br>Benefit: MAJOR<br>Threshold discipline prevents destructive premature intervention cycle | Statistical fundamentals applied to Meta context; widely documented problem |
| Decision Framework 5-step sequence | D | 8 | Structured decision protocol synthesizing verified principles (observation window, signal vs noise, allowed vs forbidden, single variable, creative readiness) | Risk: MEDIUM<br>Skipping steps leads to premature or multi-variable changes<br>Benefit: SUBSTANTIAL<br>Systematic protocol prevents impulsive decisions and maintains campaign integrity | Framework synthesis of individually verified principles |
| Change log creates improvable feedback loop | D | 8 | Standard operational discipline; documented decision history enables post-analysis and prevents "I think we changed that" ambiguity | Risk: LOW<br>Lack of logging prevents learning from past decisions<br>Benefit: MODERATE<br>Change documentation enables systematic improvement over time | Best practice across performance marketing; not Meta-specific |

**Verification Key:**
- **Type:** A=Factual Technical, B=Operator Mental Model, C=Framework Construct, D=Operational Best Practice, E=Causal Assertion
- **Confidence Scale:** 1-2=Unverified, 3-4=Speculative, 5-6=Reasonably Inferred, 7-8=Well Supported, 9-10=Verified
- **Last Updated:** 2026-02-22

---

#operational-control #governance #change-management #observation-window #verification-complete
