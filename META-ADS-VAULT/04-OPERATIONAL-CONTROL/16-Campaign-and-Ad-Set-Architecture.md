# 16 — Campaign & Ad Set Architecture

> **Part of:** [[_MOC-Operational-Control|Part IV — Operational Control]] | [[../00-INDEX/HOME|HOME]]
> **See also:** [[../02-STRUCTURAL-STRATEGY/07-Immutable-Global-Variables|Immutable Variables]], [[../02-STRUCTURAL-STRATEGY/09-Cognitive-Stages-and-Optimization-Contracts|Cognitive Stages]], [[17-Budget-Variance-and-Stability|Budget & Stability]], [[../01-SYSTEM-PHYSICS/04-Auction-Mechanics|Auction Mechanics]], [[../05-REFERENCE/Glossary-and-Acronyms|Glossary]]

---

## Where Most Advanced Advertisers Unknowingly Destroy Learning

Architecture decisions are irreversible mid-learning. Getting structure wrong means you must restart — which means lost budget and time. Get structure right before launch.

---

## 16.1 Campaign Structure Rule

> [!rule] One Campaign = One Learning System
> A campaign must contain exactly:
> - **One Cognitive Stage** ([[../05-REFERENCE/Glossary-and-Acronyms|CS]])
> - **One Optimization Event**
> - **One dominant Value Expression Type** ([[../05-REFERENCE/Glossary-and-Acronyms|VE]])
> - **One Emotional Axis** ([[../05-REFERENCE/Glossary-and-Acronyms|EA]])
> - **One Core Promise** ([[../05-REFERENCE/Glossary-and-Acronyms|SCR]])

If you mix these inside one campaign, you create **semantic ambiguity**, which reduces learnability.

The system cannot learn to predict performance for a campaign that sometimes means one thing and sometimes means another.

---

## 16.2 Ad Set Design Logic

Ad sets vary **CONTEXT**, not **MESSAGE.**

### Ad sets MAY vary:
- Recency windows (e.g., 30-day vs. 7-day retargeting)
- Geography
- Device
- Placement grouping
- Signal cluster (e.g., [[../05-REFERENCE/Glossary-and-Acronyms|LPV]] 30d vs. LPV 7d)

### Ad sets MUST NOT vary:
- [[../05-REFERENCE/Glossary-and-Acronyms|PS]]
- [[../05-REFERENCE/Glossary-and-Acronyms|OF]]
- [[../05-REFERENCE/Glossary-and-Acronyms|VE]]
- [[../05-REFERENCE/Glossary-and-Acronyms|EA]]
- Core thesis

> [!rule] If Ad Sets Vary Message, It Is Not Variation — It Is a Different System
> Two ad sets pointing at different core promises are two different campaigns that have been incorrectly collapsed into one. Separate them.

---

## 16.3 Fragmentation Risk

Too many ad sets cause:

| Problem | Effect |
|---|---|
| Insufficient event density per ad set | Prolonged learning phase |
| Budget dilution | No single ad set reaches learning threshold |
| Higher [[../05-REFERENCE/Glossary-and-Acronyms|CPA]] volatility | System cannot confidently allocate |
| False attribution | Poor performance blamed on creative, not structure |

> [!rule] Concentration Accelerates Learning. Fragmentation Delays It.
> Start with fewer ad sets. Add complexity only when there is a specific, justified reason — not because more segmentation "feels more precise."

---

## Architecture Principles Summary

| Principle | Rule |
|---|---|
| Campaign scope | One stage, one objective, one thesis |
| Ad set scope | Context variation only — never message variation |
| Ad set count | As few as possible to maintain signal density |
| Creative count per ad set | 3-5 (enough variety without splitting signal) |
| Audience overlap | Use exclusions to prevent cannibalization between stages |

---

## Stage-Architecture Matrix

| Stage | Campaign Goal | Ad Set Logic | Audience |
|---|---|---|---|
| Exploration | ThruPlay / Video Views | Broad / Advantage+ | Cold |
| Identification | [[../05-REFERENCE/Glossary-and-Acronyms|LPV]] | Engagers / Viewers | Warm (soft retargeting) |
| Validation | Lead | LPV, strong retargeting | Hot |
| Decision | Purchase | Short-window retargeting | Hottest |

---

#operational-control #campaign-architecture #ad-set #fragmentation
