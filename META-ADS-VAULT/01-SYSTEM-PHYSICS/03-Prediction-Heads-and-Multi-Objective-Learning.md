# 3 — Prediction Heads & Multi-Objective Learning

> **Part of:** [[_MOC-System-Physics|Part I — System Physics]] | [[../00-INDEX/HOME|HOME]]
> **See also:** [[02-Embedding-Architecture|Embedding Architecture]], [[04-Auction-Mechanics|Auction Mechanics]], [[../05-REFERENCE/Glossary-and-Acronyms|Glossary]]

---

## The System Predicts Multiple Things at Once

Meta's scoring is not single-objective. It simultaneously produces:

| Output | What It Predicts |
|---|---|
| [[../05-REFERENCE/Glossary-and-Acronyms|pCTR]] / [[../05-REFERENCE/Glossary-and-Acronyms|pCVR]] / [[../05-REFERENCE/Glossary-and-Acronyms|EAR]] | Probability of target action |
| pHide / pReport / expected_negative_feedback | Probability of negative user experience |
| pRisk | Policy proximity, fraud, abuse patterns |
| pValue / UV | Future value (when applicable) |

---

## 3.1 What "Multi-Objective" Means in Practice

A creative can simultaneously:

- ↑ Increase P(click)
- ↑ Increase P(hide)
- ↓ Decrease P(conversion)
- ↑ Increase policy proximity risk signals

The system has to balance all of these. So:

> [!rule] Your goal is NOT "maximize CTR."
> Your goal is **maximize net expected utility under constraints.**

---

## 3.2 The Expected Utility Formula (Operator Mental Model)

> [!formula] Expected Utility
> ```
> Expected Utility(U,A,C) =
>   [Bid × P(Action|U,A,C)] × ExperienceMultiplier(U,A,C) − RiskPenalty(U,A,C)
> ```
>
> Where:
> - **ExperienceMultiplier** decreases when predicted negative feedback increases
> - **RiskPenalty** increases when predicted policy/integrity risk increases
> - "Future value" may enter as an additional term when applicable

This is not a published formula. It is an accurate **operator mental model** for reasoning about system behavior.

---

## 3.3 The Most Important Operator Rule

> [!rule] You Cannot Buy Stability With Bid
> If you are generating quality or risk penalties, bid cannot compensate.
>
> Even if you can force short-term delivery, the system will "charge you later" by:
> - raising effective CPMs,
> - reducing distribution,
> - limiting scaling potential.

This means quality signals are not "secondary metrics." They are load-bearing components of the scoring formula.

---

## Key Prediction Head Outputs and Their Creative Implications

| Signal | What Creates It | Creative Implication |
|---|---|---|
| pCTR ↑ | Strong hook, curiosity gap, relevance | Good if CVR follows. Dangerous if CVR doesn't. |
| pCVR ↑ | Clear mechanism, trust, stage alignment | Requires [[../02-STRUCTURAL-STRATEGY/09-Cognitive-Stages-and-Optimization-Contracts|stage-appropriate]] creative |
| pHide ↑ | Interruption without value, aggressive tone | Raises ExperienceMultiplier penalty |
| pReport ↑ | Misleading claims, policy edges | Raises RiskPenalty |
| post-click bounce ↑ | Landing mismatch, slow load, message discontinuity | Degrades future delivery confidence |

---

## Connected Notes

- [[04-Auction-Mechanics|→ Auction Mechanics]] — how these predictions feed the final score
- [[../02-STRUCTURAL-STRATEGY/09-Cognitive-Stages-and-Optimization-Contracts|→ Cognitive Stages]] — stage-appropriate optimization events
- [[../04-OPERATIONAL-CONTROL/17-Budget-Variance-and-Stability|→ Budget & Stability]] — why stability protects prediction quality

#system-physics #prediction #ear #multi-objective
