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

---

## Verification Status

> This section documents the verification status of key claims and assumptions in this note. Confidence scores reflect the strength of available evidence from Meta official sources, academic research, and industry validation.

| Claim/Assumption | Type | Confidence | Evidence | Impact | Notes |
|-----------------|------|------------|----------|--------|-------|
| Multi-objective scoring system (simultaneous predictions) | A | 9 | Meta confirms multi-task learning via Lattice, GEM; [Meta Engineering](https://engineering.fb.com/2024/11/19/data-infrastructure/sequence-learning-personalized-ads-recommendations/), [Meta AI](https://ai.meta.com/blog/ai-ads-performance-efficiency-meta-lattice/) | Risk: MEDIUM \| Benefit: SUBSTANTIAL<br>Single-objective thinking limits strategy. Multi-objective understanding enables balanced optimization. | Cross-reference: Glossary verification (confidence 9); Meta AI research explicit |
| pCTR/pCVR/EAR as action probability predictions | B | 6-8 | Industry understanding; EAR confirmed at confidence 8, pCTR/pCVR at 6 | Risk: LOW \| Benefit: MODERATE<br>Specific prediction head names less critical. Understanding action prediction improves creative strategy. | Cross-reference: Glossary verifications (EAR=8, pCTR/pCVR=6) |
| pHide/pReport/negative feedback as quality predictions | A | 8 | Meta confirms user feedback impacts quality; quality signals documented | Risk: HIGH \| Benefit: MAJOR<br>Ignoring quality predictions causes delivery penalties. Optimizing quality improves auction performance. | Cross-reference: File 3 verification (confidence 8) |
| pRisk for policy/fraud/abuse patterns | A | 7 | Industry consensus on integrity layer; policy proximity affects delivery | Risk: HIGH \| Benefit: MAJOR<br>Policy violations cause severe restrictions. Compliance maintains delivery stability. | Cross-reference: File 3 verification (confidence 7) |
| Goal is "maximize net expected utility under constraints" (not just CTR) | E | 8 | Multi-objective balancing confirmed; user experience prioritized over single metrics | Risk: CRITICAL \| Benefit: TRANSFORMATIVE<br>CTR-only optimization generates quality penalties and delivery failure. Net utility maximization enables sustainable performance. | Synthesis of multi-objective learning and quality priority |
| Expected Utility formula structure | B | 6 | Components verified; structure is operator mental model; balancing confirmed | Risk: MEDIUM \| Benefit: SUBSTANTIAL<br>Wrong mental model misguides optimization priorities. Correct structure enables balanced decision-making. | Cross-reference: Glossary verification (confidence 6); explicitly marked as operator model |
| ExperienceMultiplier decreases with negative feedback | E | 8 | Quality multiplier affects auction; negative feedback impacts delivery | Risk: HIGH \| Benefit: MAJOR<br>High negative feedback degrades all delivery metrics. Minimizing negative signals improves multiplier effect. | Logical extension of quality signals (confidence 8); confirmed mechanism |
| RiskPenalty increases with policy/fraud proximity | E | 7 | Policy violations and fraud patterns cause penalties and throttling | Risk: HIGH \| Benefit: MAJOR<br>Risk signals cause hard delivery restrictions. Staying clear of edges maintains stable delivery. | Cross-reference: File 3 verification (confidence 7) |
| Cannot buy stability with bid (quality/risk cannot be compensated) | E | 8 | "Bad experience can't save high bids"; quality prioritized over bid amount | Risk: CRITICAL \| Benefit: TRANSFORMATIVE<br>Attempting to outbid quality issues wastes budget. Quality-first approach unlocks efficient delivery. | Cross-reference: File 2 and 3 verifications (both confidence 8); critical principle |
| System charges later via higher CPMs, reduced distribution, limited scaling | E | 7 | Account quality history affects costs and delivery; quality degradation compounds | Risk: HIGH \| Benefit: MAJOR<br>Short-term forcing creates long-term inefficiency. Sustainable approach maintains compounding benefits. | Cross-reference: File 4 historical priors (confidence 8); logical consequence |
| High pCTR + low pCVR = dangerous mismatch | E | 7 | CTR-CVR mismatch indicates landing page failure; quality signal to Meta | Risk: MEDIUM \| Benefit: SUBSTANTIAL<br>Mismatch wastes budget on unqualified clicks. Alignment improves conversion efficiency. | Cross-reference: File 3 verification (confidence 7) |
| pCVR requires stage-appropriate creative | E | 7 | Stage alignment improves action probability; misalignment reduces CVR | Risk: CRITICAL \| Benefit: TRANSFORMATIVE<br>Stage-inappropriate creative causes conversion failure. Stage alignment enables functional optimization. | Cross-reference: File 2 verification (confidence 7); stage framework verified in Phase 2 |
| Post-click bounce degrades future delivery confidence | E | 7 | Post-click experience affects delivery and costs; bounce is quality signal | Risk: HIGH \| Benefit: MAJOR<br>Landing page mismatches degrade long-term delivery. Strong post-click experience maintains delivery confidence. | Cross-reference: File 3 verification (confidence 7) |

**Verification Key:**
- **Type:** A=Factual Technical, B=Operator Mental Model, C=Framework Construct, D=Operational Best Practice, E=Causal Assertion
- **Confidence Scale:** 1-2=Unverified, 3-4=Speculative, 5-6=Reasonably Inferred, 7-8=Well Supported, 9-10=Verified
- **Last Updated:** 2026-02-21

**Notes:**
- Most claims in this file synthesize and formalize principles verified in Files 1-4
- Heavy cross-referencing ensures consistency across foundation files
- Operator mental model explicitly acknowledged in file; components individually verified
- Multi-objective learning is Meta's most strongly documented technical architecture feature

**Sources:**
- [Meta's Multi-Task Learning Systems](https://ai.meta.com/blog/ai-ads-performance-efficiency-meta-lattice/)
- [Meta Sequence Learning](https://engineering.fb.com/2024/11/19/data-infrastructure/sequence-learning-personalized-ads-recommendations/)
- Cross-references to Files 1-4 verifications for component claims

---

#system-physics #prediction #ear #multi-objective #verification-complete
