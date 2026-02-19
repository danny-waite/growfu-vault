# 4 — Auction Mechanics

> **Part of:** [[_MOC-System-Physics|Part I — System Physics]] | [[../00-INDEX/HOME|HOME]]
> **See also:** [[03-Prediction-Heads-and-Multi-Objective-Learning|Prediction Heads]], [[05-Delivery-and-Budget-Dynamics|Delivery & Budget]], [[../04-OPERATIONAL-CONTROL/19-Competitive-Density-and-Marginal-CPA|Competitive Density]], [[../05-REFERENCE/Glossary-and-Acronyms|Glossary]]

---

## The Three Core Auction Inputs

Meta does not publish an explicit formula. The auction is consistently based on three components:

1. **Bid** — what you are willing to pay
2. **[[../05-REFERENCE/Glossary-and-Acronyms|EAR]]** — Estimated Action Rate (predicted probability the user completes the objective)
3. **Ad Quality / User Experience** — predicted user experience impact

---

## How Ranking Happens (Operator-Accurate Mental Model)

> [!formula] Auction Final Score
> ```
> BusinessScore = Bid × EAR
> QualityPenalty = f(pHide, pReport, expected_negative_feedback, post-click bounce)
> RiskPenalty = g(pRisk, fraud, borderline policy)
>
> FinalScore ≈ BusinessScore × QualityMultiplier − RiskPenalty
> ```

This is not a literally published formula, but it is an **accurate operational model** for decision-making.

---

## 4.1 What Each Component Means

### A) Bid
What you are willing to pay.
Bid affects **win probability**, but not user experience constraints.

> Raising bid can win more auctions but cannot compensate for quality or risk penalties. See [[03-Prediction-Heads-and-Multi-Objective-Learning#3.3 The Most Important Operator Rule|the stability rule]].

### B) EAR (Estimated Action Rate)
The system's predicted probability that the user will complete the objective action if shown the ad.
[[../05-REFERENCE/Glossary-and-Acronyms|EAR]] is conditional on U, A, and C.

Your creative affects EAR by improving:
- **clarity** — the user understands what is being offered
- **relevance** — the user recognizes themselves in the message
- **belief shift** — the user is moved toward the action
- **friction reduction** — the path to action is clear
- **stage alignment** — the action requested matches the cognitive stage

### C) Quality / Experience
Quality is **not** aesthetic quality. It is **predicted user experience impact.**

Key quality signals:
- Probability of hide
- Probability of report
- Expected negative feedback
- Post-click bounce
- High CTR + low CVR (mismatch signal)
- Fatigue by repetition

> [!rule] Post-Click Bounce Is a Real Operational Risk
> Post-click bounce may not be an explicit auction term, but it is a plausible downstream signal affecting conversion probability, dissatisfaction, and future delivery confidence. Treat it as such regardless.

### D) Risk / Integrity
Relates to:
- Fraud/spam/abuse patterns
- Policy proximity (borderline behavior)
- Other integrity constraints

**Practical outcome:** Risk can function as a hard filter, throttling, or score penalty. Approaching policy edges increases system uncertainty and reduces distribution stability.

---

## 4.2 Competitive Reality

The auction is **relative:**

- Your ad is ranked against competitors targeting the same users in similar contexts.
- "Good" is always relative to alternative supply available at that moment.

> [!rule] Differentiation Is Not Optional
> In high-density auctions, you must win with higher **net utility**, not just higher bid. Semantic and visual differentiation is a competitive necessity, not a creative preference.

See [[../04-OPERATIONAL-CONTROL/19-Competitive-Density-and-Marginal-CPA|Competitive Density & Marginal CPA]] for how auction pressure affects your operations.

---

#system-physics #auction #ear #scoring
