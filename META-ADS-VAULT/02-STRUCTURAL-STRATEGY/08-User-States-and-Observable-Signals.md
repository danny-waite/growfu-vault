# 8 — User States & Observable Signals

> **Part of:** [[_MOC-Structural-Strategy|Part II — Structural Strategy]] | [[../00-INDEX/HOME|HOME]]
> **See also:** [[07-Immutable-Global-Variables|Immutable Global Variables]], [[09-Cognitive-Stages-and-Optimization-Contracts|Cognitive Stages]], [[../01-SYSTEM-PHYSICS/06-Feedback-Loop-and-Evolution|Feedback Loop]], [[../05-REFERENCE/Glossary-and-Acronyms|Glossary]]

---

## Translating PS and OF into Machine-Detectable Reality

Your [[../05-REFERENCE/Glossary-and-Acronyms|PS]] (Problem Space) and [[../05-REFERENCE/Glossary-and-Acronyms|OF]] (Outcome Function) are human constructs.

Meta does not "understand" PS. It learns **behavioral patterns.** Therefore, every PS and OF must be translated into observable user states that live inside the User Embedding.

> [!rule] The System Only Sees Behavior
> Most advertisers fail here. They define a problem psychologically but never define it behaviorally. The system can only detect what users *do* — not what they *feel*.

---

## 8.1 Observable Initial State (S0)

[[../05-REFERENCE/Glossary-and-Acronyms|S0]] is the state of the user **BEFORE** your intervention. It must be defined per stage.

**S0 is not a persona description. It is a behavioral signal profile.**

For each stage, define:

### A) What they consume
- Content categories
- Content formats (UGC, expert, luxury, educational)
- Watch time norms
- Ad density tolerance

### B) What they ignore
- Scroll velocity patterns
- Skips under 3 seconds
- Avoidance of certain CTAs

### C) What micro-actions they perform
- View > 3s
- View > 6s
- Save / Comment / Click
- [[../05-REFERENCE/Glossary-and-Acronyms|LPV]] (Landing Page View)
- Scroll depth
- Time on page

### D) What they avoid
- Lead forms
- Checkout
- High commitment CTAs

---

## 8.2 S0 Template (Per Stage)

For each campaign, define explicitly:

| Field | Your Definition |
|---|---|
| Primary signal (main measurable state) | |
| Attention signals | |
| Light intent signals | |
| Rejection signals | |
| CTA restrictions | |

**Example — Exploration Stage:**

| Field | Value |
|---|---|
| Primary signal | Video View > 6s |
| Attention signals | Completion %, Hold rate in first 3 seconds |
| Light intent | Profile click |
| Rejection | Hide, Skip < 1s |
| CTA restriction | No purchase CTA |

---

## 8.3 Target State (S1)

[[../05-REFERENCE/Glossary-and-Acronyms|S1]] is the **measurable progression state** — what the user's behavior looks like after engaging with your creative at this stage.

The [[../05-REFERENCE/Glossary-and-Acronyms|OF]] must be decomposed across stages. Not every campaign aims at purchase. Each stage has its own S1.

| Stage | S1 Definition | Measured By |
|---|---|---|
| **Exploration** | User understood the problem | Watch time, interaction depth |
| **Identification** | User sees themselves reflected | [[../05-REFERENCE/Glossary-and-Acronyms|LPV]], meaningful engagement |
| **Validation** | User trusts the mechanism | Lead, high-intent signal |
| **Decision** | User executes final action | Purchase / Value |

---

## 8.4 Cognitive Progress Signals

You cannot rely only on declared optimization events. You must define:
- Signals that **confirm** progress
- Signals that **invalidate** progress (false positives)

### False Progress Patterns to Detect

| Pattern | What It Signals |
|---|---|
| High CTR + low watch time | Clickbait hook → false learning |
| [[../05-REFERENCE/Glossary-and-Acronyms|LPV]] + bounce < 5 seconds | Landing mismatch → friction spike |
| Fast low-quality leads | No cognitive progression → poor future value |

> [!rule] Noisy Success Is Failure
> A high CTR that doesn't produce watch time or landing engagement is not success. It is false learning being injected into the system. The system will optimize toward what you measure — if you measure CTR alone, you will get clicks that don't convert.

---

## Connected Notes

- [[09-Cognitive-Stages-and-Optimization-Contracts|→ Cognitive Stages]] — stage-by-stage optimization contracts
- [[../04-OPERATIONAL-CONTROL/17-Budget-Variance-and-Stability|→ Budget & Variance]] — how signal quality affects delivery stability
- [[../03-CREATIVE-ENGINEERING/12-Micro-Signal-Optimization|→ Micro-Signal Optimization]] — engineering for early signal capture

#structural-strategy #user-states #s0 #s1 #signals
