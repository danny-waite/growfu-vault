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

#operational-control #governance #change-management #observation-window
