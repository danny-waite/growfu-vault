# Glossary & Acronyms

> Single source of truth for all terminology used in the [[../00-INDEX/HOME|META ADS SYSTEM ENGINEERING FRAMEWORK]].

---

## Core Acronyms

| Acronym | Full Name | Definition | Primary Note |
|---|---|---|---|
| **PS** | Problem Space | The recurring human error (cognitive, emotional, behavioral) your system addresses. Must be expressible as 1 sentence + 3 observable symptoms. | [[../02-STRUCTURAL-STRATEGY/07-Immutable-Global-Variables\|07 — Immutable Global Variables]] |
| **OF** | Outcome Function | An observable state transition — what the user *does* differently after your intervention. Not aspiration; a behavioral change. | [[../02-STRUCTURAL-STRATEGY/07-Immutable-Global-Variables\|07 — Immutable Global Variables]] |
| **BR** | Brand Role | The functional brand–user relationship: direction (uni/bidirectional), intensity (low/medium/high), position (above/beside/behind). | [[../02-STRUCTURAL-STRATEGY/07-Immutable-Global-Variables\|07 — Immutable Global Variables]] |
| **CS** | Cognitive Stage | The user's current stage in the learning journey: Exploration → Identification → Validation → Decision. | [[../02-STRUCTURAL-STRATEGY/09-Cognitive-Stages-and-Optimization-Contracts\|09 — Cognitive Stages]] |
| **VE** | Value Expression Type | The type of message delivered. Closed set: INSIGHT / VALIDATION / FRAMEWORK / SYSTEM. One per campaign. | [[../02-STRUCTURAL-STRATEGY/07-Immutable-Global-Variables\|07 — Immutable Global Variables]] |
| **EA** | Emotional Axis | The emotional transition the creative facilitates (e.g., confusion → clarity). Defined per campaign; never mixed. | [[../02-STRUCTURAL-STRATEGY/07-Immutable-Global-Variables\|07 — Immutable Global Variables]] |
| **AL** | Abstraction Level | How conceptual vs. concrete the creative is. Content: high/medium. Ads: medium/low. | [[../02-STRUCTURAL-STRATEGY/07-Immutable-Global-Variables\|07 — Immutable Global Variables]] |
| **CTA-R** | CTA Intensity Range | The allowable strength of the call-to-action given stage, brand role, and trust constraints. | [[../02-STRUCTURAL-STRATEGY/07-Immutable-Global-Variables\|07 — Immutable Global Variables]] |
| **SCR** | Semantic Consistency Rules | What cannot change without creating a new system: core promise, language, immutable theme, claim limits. | [[../02-STRUCTURAL-STRATEGY/07-Immutable-Global-Variables\|07 — Immutable Global Variables]] |
| **S0** | Observable Initial State | The behavioral signal profile of the user *before* your intervention. Defined per stage. | [[../02-STRUCTURAL-STRATEGY/08-User-States-and-Observable-Signals\|08 — User States]] |
| **S1** | Target State | The measurable progression state — what the user's behavior looks like *after* engaging with your creative at a given stage. | [[../02-STRUCTURAL-STRATEGY/08-User-States-and-Observable-Signals\|08 — User States]] |
| **EAR** | Estimated Action Rate | Meta's predicted probability that a user will complete the declared optimization event if shown the ad. Conditional on U, A, and C. | [[../01-SYSTEM-PHYSICS/03-Prediction-Heads-and-Multi-Objective-Learning\|03 — Prediction Heads]] |
| **U-A-C** | User–Ad–Context Triad | The three-component scoring triple Meta evaluates at auction time. See dedicated reference. | [[U-A-C-Triad-Reference\|U-A-C Triad Reference]] |
| **pCTR** | Predicted Click-Through Rate | One prediction head output; the system's estimate of click probability given U, A, C. | [[../01-SYSTEM-PHYSICS/03-Prediction-Heads-and-Multi-Objective-Learning\|03 — Prediction Heads]] |
| **pCVR** | Predicted Conversion Rate | System's estimate of conversion probability given U, A, C. | [[../01-SYSTEM-PHYSICS/03-Prediction-Heads-and-Multi-Objective-Learning\|03 — Prediction Heads]] |
| **LPV** | Landing Page View | A Meta optimization event; user loads the landing page after clicking. Used as a light intent signal at Identification stage. | [[../02-STRUCTURAL-STRATEGY/09-Cognitive-Stages-and-Optimization-Contracts\|09 — Cognitive Stages]] |
| **CPA** | Cost Per Action | The cost to acquire one optimization event. Rises naturally with scale (marginal CPA dynamics). | [[../04-OPERATIONAL-CONTROL/19-Competitive-Density-and-Marginal-CPA\|19 — Marginal CPA]] |
| **MOC** | Map of Content | An index/hub note in this Obsidian vault that organizes a section and links to its child notes. | [[../00-INDEX/HOME\|HOME]] |

---

## Key Formulas

**Expected Utility (operator mental model):**
```
Expected Utility(U,A,C) =
  [Bid × P(Action|U,A,C)] × ExperienceMultiplier(U,A,C) − RiskPenalty(U,A,C)
```

**Auction Final Score (operator mental model):**
```
FinalScore ≈ BusinessScore × QualityMultiplier − RiskPenalty
BusinessScore = Bid × EAR
QualityPenalty = f(pHide, pReport, expected_negative_feedback, post-click bounce)
RiskPenalty = g(pRisk, fraud, borderline policy)
```

---

## Value Expression Types (VE) — Closed Set

| VE | Name | Stage |
|---|---|---|
| 1 | INSIGHT | Exploration |
| 2 | VALIDATION | Exploration / Identification |
| 3 | FRAMEWORK | Identification |
| 4 | SYSTEM | Validation / Decision |

---

*Every note in this vault links here on first use of any acronym.*

#reference #glossary
