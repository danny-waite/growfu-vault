# 22 — Master Checklists & Execution Templates

> **Part of:** [[_MOC-Operational-Control|Part IV — Operational Control]] | [[../00-INDEX/HOME|HOME]]
> **The operational anchor of this vault. Start here for daily campaign management.**

---

## How to Use This Note

This note consolidates all operational checklists and the Campaign Definition Sheet into one place. Use it as:
- **Pre-launch checklist** before any new campaign goes live
- **Change checklist** before any modification to a live campaign
- **Scaling checklist** before any significant budget increase
- **Campaign definition sheet** as a template for every new system

---

## 22.1 Campaign Definition Sheet

Complete all fields before creating any creative or campaign structure.

### System Identity

| Field | Your Definition |
|---|---|
| **1. Problem Space ([[../05-REFERENCE/Glossary-and-Acronyms\|PS]])** | |
| PS: 1-sentence definition | |
| PS: Observable symptom 1 | |
| PS: Observable symptom 2 | |
| PS: Observable symptom 3 | |
| **2. Outcome Function ([[../05-REFERENCE/Glossary-and-Acronyms\|OF]])** | Observable state transition (behavioral change): |
| **3. Brand Role ([[../05-REFERENCE/Glossary-and-Acronyms\|BR]])** | Direction: / Intensity: / Position: |

### Campaign Configuration

| Field | Your Definition |
|---|---|
| **4. Cognitive Stage ([[../05-REFERENCE/Glossary-and-Acronyms\|CS]])** | Exploration / Identification / Validation / Decision |
| **5. Optimization Event** | ThruPlay / LPV / Lead / Purchase / Value |
| **6. Value Expression Type ([[../05-REFERENCE/Glossary-and-Acronyms\|VE]])** | INSIGHT / VALIDATION / FRAMEWORK / SYSTEM |
| **7. Emotional Axis ([[../05-REFERENCE/Glossary-and-Acronyms\|EA]])** | [From state] → [To state] |
| **8. Abstraction Level ([[../05-REFERENCE/Glossary-and-Acronyms\|AL]])** | High / Medium / Low |
| **9. CTA Intensity Range ([[../05-REFERENCE/Glossary-and-Acronyms\|CTA-R]])** | [Min intensity] to [Max intensity] |

### Semantic Rules

| Field | Your Definition |
|---|---|
| **10. Semantic Consistency Rules ([[../05-REFERENCE/Glossary-and-Acronyms\|SCR]])** | |
| Core promise (must appear in all creatives) | |
| Required language (words/phrases to always use) | |
| Forbidden claims (what cannot be promised) | |
| Immutable theme | |

### User State Model

| Field | Your Definition |
|---|---|
| **11. Observable S0** (initial user behavior) | |
| **12. Target S1** (measurable progression state) | |
| **13. Progress Signals** (confirm S0→S1 transition) | |
| **14. False Positive Signals** (noise to ignore) | |

### Campaign Architecture

| Field | Your Definition |
|---|---|
| **15. Contexts (Ad Sets)** | What context variation will ad sets represent? |
| **16. Creative Families** | How many distinct creative approaches will you build? |
| **17. Allowed Variations** | What may vary within the portfolio? |

### Governance

| Field | Your Definition |
|---|---|
| **18. Governance Rules** | What changes require review before executing? |
| **19. Fatigue Threshold** | What signals trigger rotation review? |
| **20. Scaling Plan** | At what CPA stability + event density do you scale? By how much? |

---

## 22.2 Ad-Level Checklist

Run this before every ad goes live.

- [ ] Same thesis as campaign [[../05-REFERENCE/Glossary-and-Acronyms|PS]] and [[../05-REFERENCE/Glossary-and-Acronyms|OF]]
- [ ] Same [[../05-REFERENCE/Glossary-and-Acronyms|VE]] as campaign
- [ ] Same [[../05-REFERENCE/Glossary-and-Acronyms|EA]] as campaign
- [ ] CTA within declared [[../05-REFERENCE/Glossary-and-Acronyms|CTA-R]] range
- [ ] Hook aligns with landing page (no mismatch in implied promise)
- [ ] No exaggerated or forbidden claims ([[../05-REFERENCE/Glossary-and-Acronyms|SCR]] compliant)
- [ ] Early retention anchor clear in first 3 seconds
- [ ] Format aligned with declared placements
- [ ] Variation is within portfolio tolerance (not a new identity)

Reference: [[../03-CREATIVE-ENGINEERING/11-Multimodal-Creative-Design|Multimodal Creative Design]] · [[../02-STRUCTURAL-STRATEGY/07-Immutable-Global-Variables|Immutable Variables]]

---

## 22.3 Pre-Launch Campaign Checklist

Run this before any new campaign launches.

**Structure**
- [ ] Campaign Definition Sheet (Section 22.1 above) completed
- [ ] One campaign = one [[../02-STRUCTURAL-STRATEGY/09-Cognitive-Stages-and-Optimization-Contracts|cognitive stage]]
- [ ] Optimization event matches stage
- [ ] Ad sets vary context only (not message)
- [ ] Audience exclusions in place (no cannibalization between stages)

**Creative**
- [ ] Minimum 3 creatives ready (sufficient for learning without over-fragmentation)
- [ ] All creatives pass Ad-Level Checklist (22.2)
- [ ] Creative identity is consistent across portfolio
- [ ] Landing page checked for message continuity

**Budget**
- [ ] Budget sufficient for ~50 optimization events in reasonable time window
- [ ] Budget is set, not starting too high (allow learning before scaling)

**Governance**
- [ ] Minimum observation window defined (impressions + events + days)
- [ ] Primary KPI and diagnostic KPIs defined
- [ ] Fatigue threshold defined

Reference: [[16-Campaign-and-Ad-Set-Architecture|Campaign Architecture]] · [[17-Budget-Variance-and-Stability|Budget & Stability]] · [[21-Governance-and-Change-Management|Governance]]

---

## 22.4 Scaling Checklist

Run this before any significant budget increase.

- [ ] Stage fully stabilized? (Performance plateau, not declining)
- [ ] Event density sufficient? (Learning phase exited — ~50+ events accumulated)
- [ ] [[../05-REFERENCE/Glossary-and-Acronyms|CPA]] stable across 7+ consecutive days?
- [ ] No rising negative feedback signals in past 5 days?
- [ ] Budget increase planned at ≤ 30% increment?
- [ ] Portfolio diversity sufficient? (Not dependent on a single creative)
- [ ] Broader framing / generalization variants ready if CPA rises post-scale?

Reference: [[../03-CREATIVE-ENGINEERING/15-Scaling-Adaptation|Scaling Adaptation]] · [[19-Competitive-Density-and-Marginal-CPA|Marginal CPA]]

---

## 22.5 Change Management Checklist

Run this before any modification to a live campaign.

- [ ] Minimum observation window reached?
- [ ] Signal trend held for 5+ days (not 1-2 day noise)?
- [ ] Is this an allowed change (not a forbidden change)? → See [[21-Governance-and-Change-Management|Governance]]
- [ ] Changing only one variable?
- [ ] New creative in pipeline if rotating out an existing creative?
- [ ] Change logged with date, reason, expected outcome?

---

#operational-control #checklists #templates #execution
