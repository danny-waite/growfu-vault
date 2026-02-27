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

---

## Verification Status

> This section documents the verification status of key claims and assumptions in this note. Confidence scores reflect the strength of available evidence from Meta official sources, academic research, and industry validation.

| Claim/Assumption | Type | Confidence | Evidence | Impact | Notes |
|-----------------|------|------------|----------|--------|-------|
| S0 (Observable Initial State) definition | C | N/A | Framework construct | Risk: N/A \| Benefit: N/A<br>Framework's behavioral state model | Cross-reference: Glossary verification (confidence N/A) |
| S1 (Target State) definition | C | N/A | Framework construct | Risk: N/A \| Benefit: N/A<br>Framework's progression state model | Cross-reference: Glossary verification (confidence N/A) |
| System only sees behavior (not feelings/psychology) | E | 8 | Meta uses behavioral embeddings; user represented by actions/interactions; [Meta Andromeda](https://engineering.fb.com/2024/12/02/production-engineering/meta-andromeda-advantage-automation-next-gen-personalized-ads-retrieval-engine/), [arXiv embeddings](https://arxiv.org/html/2406.05898v1) | Risk: MEDIUM \| Benefit: SUBSTANTIAL<br>Psychological targeting without behavioral signals fails. Behavioral definition enables effective targeting. | Cross-reference: File 4 embedding architecture (confidence 8) |
| User embedding contains behavioral signal profile | B | 8 | Embeddings encode user behavior patterns; sequence learning from interactions; [Meta Engineering](https://engineering.fb.com/2024/11/19/data-infrastructure/sequence-learning-personalized-ads-recommendations/) | Risk: LOW \| Benefit: MODERATE<br>Understanding behavioral representation informs targeting strategy. | Cross-reference: File 4 verification (confidence 8) |
| High CTR + low watch time = clickbait → false learning | E | 7 | CTR-CVR mismatch signals quality issues; noisy signals degrade optimization | Risk: HIGH \| Benefit: MAJOR<br>Clickbait signals poison learning data. Quality signals enable accurate optimization. | Cross-reference: File 3 CTR-CVR mismatch (confidence 7) |
| LPV + bounce <5 seconds = landing mismatch | E | 7 | Post-click bounce affects delivery; mismatch creates negative signals | Risk: HIGH \| Benefit: MAJOR<br>Landing mismatch degrades delivery confidence. Alignment maintains quality. | Cross-reference: File 3 post-click bounce (confidence 7) |
| System optimizes toward what you measure | E | 9 | Optimization event selection determines what Meta predicts; well-documented mechanic | Risk: CRITICAL \| Benefit: TRANSFORMATIVE<br>Measuring wrong metrics optimizes for wrong outcomes. Correct measurement enables effective optimization. | Cross-reference: File 2 campaign=contract (confidence 7-9); File 7 (confidence 9) |
| False positives inject false learning into system | E | 7 | Noisy signals degrade prediction quality; signal quality affects learning stability | Risk: HIGH \| Benefit: MAJOR<br>False positives corrupt learning data. Clean signals enable accurate predictions. | Logical extension of learning phase mechanics; practitioner consensus |
| OF must be decomposed across stages (not every campaign aims at purchase) | C/E | 7 | Framework concept; underlying behavior: stage-appropriate optimization verified (confidence 9) | Risk: CRITICAL \| Benefit: TRANSFORMATIVE<br>Purchase-only optimization ignores funnel stages. Stage decomposition enables functional optimization. | Framework structure (N/A); underlying Meta behavior verified (File 7, confidence 9) |
| Behavioral progression signals confirm/invalidate progress | E | 6 | Quality signals and engagement depth matter beyond optimization event; practitioner understanding | Risk: MEDIUM \| Benefit: SUBSTANTIAL<br>Optimization event alone misses signal quality. Multi-signal monitoring improves campaign health. | Logical extension of multi-objective learning (confidence 9); practitioner practice |
| S0 template fields (primary signal, attention, light intent, rejection, CTA restrictions) | C | N/A | Framework operational template | Risk: N/A \| Benefit: N/A<br>Framework's campaign definition tool | Framework structure for operationalizing S0 concept |
| S1 measured differently per stage (watch time → LPV → lead → purchase) | D | 8 | Progression through optimization events standard practice; stage-event alignment | Risk: MEDIUM \| Benefit: SUBSTANTIAL<br>Universal success metric misses stage progression. Stage-appropriate measurement tracks actual progress. | Cross-reference: File 7 stage-event mapping (confidence 10 for events) |

**Verification Key:**
- **Type:** A=Factual Technical, B=Operator Mental Model, C=Framework Construct, D=Operational Best Practice, E=Causal Assertion
- **Confidence Scale:** 1-2=Unverified, 3-4=Speculative, 5-6=Reasonably Inferred, 7-8=Well Supported, 9-10=Verified
- **Last Updated:** 2026-02-21

**Important Distinctions:**
- **S0/S1 Concepts (Type C, N/A):** Framework's behavioral state model
- **Underlying Mechanics (Type E, Scored):** Meta's behavioral learning, signal quality, false positives - WELL VERIFIED
- **Templates (Type C, N/A):** Framework tools for operationalizing concepts

**Key Finding:**
S0/S1 are framework constructs providing structure, BUT built on strongly verified Meta behavior:
- System uses behavioral embeddings (confidence 8)
- Signal quality affects learning (confidence 7-9)
- Optimization event selection determines what's optimized (confidence 9)

The framework translates verified Meta mechanics into operational structure.

**Sources:**
- [Meta Andromeda: User Embeddings](https://engineering.fb.com/2024/12/02/production-engineering/meta-andromeda-advantage-automation-next-gen-personalized-ads-retrieval-engine/)
- [Async Learned User Embeddings](https://arxiv.org/html/2406.05898v1)
- [Meta Sequence Learning](https://engineering.fb.com/2024/11/19/data-infrastructure/sequence-learning-personalized-ads-recommendations/)
- Cross-references to Files 2, 3, 4, 7 for underlying mechanics

---

#structural-strategy #user-states #s0 #s1 #signals #verification-complete
