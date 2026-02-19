# 1 — The Single Mental Model

> **Part of:** [[_MOC-System-Physics|Part I — System Physics]] | [[../00-INDEX/HOME|HOME]]
> **See also:** [[../05-REFERENCE/Glossary-and-Acronyms|Glossary]], [[02-Embedding-Architecture|Embedding Architecture]]

---

## Core Definition

> [!rule] The Mental Model You Must Operate With
> Meta does not optimize isolated ads.
> It optimizes **user state transitions** by maximizing **expected value** of future interaction under constraints.

Meta does not "choose ads."
It allocates impressions by optimizing predicted outcomes under constraints.

---

## Expected Value Is a Function Of

- **Probability of action** — Predicted/Estimated Action Rate (e.g., pCTR / pCVR / [[../05-REFERENCE/Glossary-and-Acronyms|EAR]])
- **Quality** — risk of negative user experience
- **Risk / Integrity** — fraud, policy proximity, abuse patterns
- **Future user value** — when applicable

---

## The 4 Operational Consequences

### 1. Everything is conditional
No creative is inherently "good." It is good for a specific (user, context) pairing.

See [[../05-REFERENCE/U-A-C-Triad-Reference|U–A–C Triad Reference]] for the full model.

### 2. The system rewards learnability
Stable semantics and stable measurement allow faster and safer allocation.

> A campaign with consistent [[../05-REFERENCE/Glossary-and-Acronyms|SCR]] will accumulate learning faster than one that varies its core promise every few days.

### 3. Quality and risk are not "secondary"
You can buy impressions with bid, but **you cannot buy stability if you generate quality or risk penalties.**

See [[03-Prediction-Heads-and-Multi-Objective-Learning|Prediction Heads]] for the multi-objective balancing act.

### 4. A campaign is a contract
Your declared optimization tells Meta what outcome you intend to maximize. If you declare an outcome the user **cannot yet consistently perform**, you create:
- unstable learning
- degraded delivery

> [!rule] Campaign = Contract with Meta
> Declare only an optimization event the user at the current [[../05-REFERENCE/Glossary-and-Acronyms|CS|Cognitive Stage]] can consistently perform. If signal volume is insufficient, move one stage up temporarily.

See [[../02-STRUCTURAL-STRATEGY/09-Cognitive-Stages-and-Optimization-Contracts|Cognitive Stages & Optimization Contracts]] for stage-appropriate optimization events.

---

## Implications for Operators

| Belief to Abandon | Replace With |
|---|---|
| "This is a good ad" | "This ad works for a specific U, A, C combination" |
| "Maximize CTR" | "Maximize net expected utility under constraints" |
| "Iterate by changing anything" | "Iterate within semantic tolerance of PS/OF/BR" |
| "More budget = more performance" | "Budget buys learning. Learning requires stable signals." |

---

#system-physics #mental-model
