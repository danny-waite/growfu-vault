# 7 — Immutable Global Variables

> **Part of:** [[_MOC-Structural-Strategy|Part II — Structural Strategy]] | [[../00-INDEX/HOME|HOME]]
> **See also:** [[../05-REFERENCE/Glossary-and-Acronyms|Glossary]], [[08-User-States-and-Observable-Signals|User States]], [[09-Cognitive-Stages-and-Optimization-Contracts|Cognitive Stages]], [[../03-CREATIVE-ENGINEERING/11-Multimodal-Creative-Design|Multimodal Creative Design]]

---

## The Structural Controls That Govern Learning

These variables are **not "per ad."** They define the learning system.

They exist to prevent the most common failure:
> Random variation that changes meaning, destroys learnability, and creates false learning.

Lock all 9 variables before creating any creative or campaign.

---

## 7.1 Problem Space (PS)

[[../05-REFERENCE/Glossary-and-Acronyms|PS]] is a recurring human error — cognitive, emotional, or behavioral.

**Requirements:**
- Identify the dominant structural cause (do not blame the user).
- Define it as a repeatable, observable pattern.

**PS must be expressible as:**
- 1 sentence definition
- 3 observable symptoms (behaviors)

> Example: "Operators launch ads without defining structural variables first [PS], resulting in inconsistent creative briefing [symptom 1], poor learning [symptom 2], and wasted budget [symptom 3]."

---

## 7.2 Outcome Function (OF)

[[../05-REFERENCE/Glossary-and-Acronyms|OF]] is **not aspiration.** It is an observable state transition.

**Requirements:**
- Describe what the user *does* differently after your intervention.
- Express as change in behavior, criteria, or action.

> Not: "Users will feel more confident."
> Yes: "Users will evaluate options using a defined framework rather than guessing."

---

## 7.3 Brand Role (BR)

[[../05-REFERENCE/Glossary-and-Acronyms|BR]] is the functional brand–user relationship, defined by:

| Dimension | Options |
|---|---|
| Direction | Unidirectional / Bidirectional |
| Intensity | Low / Medium / High |
| Position | Above / Beside / Behind |

**BR governs:**
- what proof is required,
- how strong the CTA can be,
- what tone is credible.

> A brand positioned "beside" the user (peer/guide) cannot use authoritative top-down tone. A brand positioned "above" cannot use casual peer tone.

---

## 7.4 Cognitive Stage (CS)

[[../05-REFERENCE/Glossary-and-Acronyms|CS]] defines where the user is in their learning journey:

**Stages:** Exploration → Identification → Validation → Decision

CS determines:
- objective,
- acceptable message type,
- acceptable CTA,
- optimization event,
- targeting style.

→ Full detail: [[09-Cognitive-Stages-and-Optimization-Contracts|Cognitive Stages & Optimization Contracts]]

---

## 7.5 Value Expression Type (VE)

[[../05-REFERENCE/Glossary-and-Acronyms|VE]] defines the type of message. **Closed set — one per campaign:**

| # | VE | Stage Alignment |
|---|---|---|
| 1 | **INSIGHT** — reframes the problem | Exploration |
| 2 | **VALIDATION** — normalizes the error | Exploration / Identification |
| 3 | **FRAMEWORK** — organizes the problem | Identification |
| 4 | **SYSTEM** — step-by-step execution | Validation / Decision |

> [!rule] One campaign = one dominant VE.
> Mixing VE types inside a campaign creates semantic ambiguity. The system cannot learn what kind of creative this is.

---

## 7.6 Emotional Axis (EA)

[[../05-REFERENCE/Glossary-and-Acronyms|EA]] defines the emotional transition the creative facilitates.

Examples:
- confusion → clarity
- insecurity → confidence
- overwhelm → control

**Rules:**
- Defined per campaign.
- **Never mixed within a campaign.**

> A campaign cannot simultaneously move users from "overwhelm → control" and "fear → hope." Pick one axis and hold it.

---

## 7.7 Abstraction Level (AL)

[[../05-REFERENCE/Glossary-and-Acronyms|AL]] controls how conceptual vs. concrete the creative is.

| Content Type | AL Range |
|---|---|
| Content (organic) | High / Medium |
| Ads | Medium / Low |

AL ensures your ad stays learnable and stage-appropriate. Early-stage (Exploration) ads can be more abstract. Decision-stage ads must be concrete and action-oriented.

---

## 7.8 CTA Intensity Range (CTA-R)

[[../05-REFERENCE/Glossary-and-Acronyms|CTA-R]] defines how strong you can push the call-to-action without breaking coherence.

Constrained by:
- Stage (the dominant constraint)
- Brand role
- Trust level established

See [[09-Cognitive-Stages-and-Optimization-Contracts#9.4 CTA Intensity per Stage|CTA intensity per stage]] for ranges.

---

## 7.9 Semantic Consistency Rules (SCR)

[[../05-REFERENCE/Glossary-and-Acronyms|SCR]] defines what **cannot change** without creating a new system:

- Core promise
- Language (specific words and phrases)
- Immutable theme
- Claim limits (what cannot be promised)

> Example SCR: "We never claim a specific revenue figure. We never imply the process is effortless. All creatives use the word 'system.'"

---

## The Non-Negotiable System Rule

> [!rule] The System Identity Rule
> **If PS, OF, or BR change, it is not an iteration. It is another system.**
>
> Start over. Do not try to "evolve" a system by changing its foundational inputs. Create a new one and let the old one finish its lifecycle.

---

## Variable Stability Matrix

| Variable | Can Vary Between Campaigns? | Can Vary Within Campaign? |
|---|---|---|
| PS | No | No |
| OF | No | No |
| BR | No | No |
| CS | No (set per campaign) | No |
| VE | No (set per campaign) | No |
| EA | No (set per campaign) | No |
| AL | Narrow range | Narrow range |
| CTA-R | Per stage | Constrained range |
| SCR | No | No |

---

## Verification Status

> This section documents the verification status of key claims and assumptions in this note. Confidence scores reflect the strength of available evidence from Meta official sources, academic research, and industry validation.

| Claim/Assumption | Type | Confidence | Evidence | Impact | Notes |
|-----------------|------|------------|----------|--------|-------|
| PS/OF/BR/CS/VE/EA/AL/CTA-R/SCR definitions | C | N/A | Framework's proprietary taxonomy | Risk: N/A \| Benefit: N/A<br>Framework's own structural system, not Meta terms | Cross-reference: Glossary verification (confidence N/A) |
| Random variation destroys learnability | E | 7 | Semantic consistency helps learning accumulation; Meta's sequence learning uses semantic/contextual info; [Meta Engineering](https://engineering.fb.com/2024/11/19/data-infrastructure/sequence-learning-personalized-ads-recommendations/) | Risk: HIGH \| Benefit: MAJOR<br>Semantic inconsistency slows learning and increases costs. Consistency accelerates signal accumulation. | Cross-reference: File 2 verification (confidence 7); File 4 semantic variety |
| Mixing VE types creates semantic ambiguity for the system | E | 7 | Embedding-based systems learn semantic identity; inconsistency prevents stable representation; [Reboot IQ](https://rebootiq.com/meta-ads-audience-strategy/) | Risk: HIGH \| Benefit: MAJOR<br>Semantic ambiguity confuses ad embedding and degrades learning. Clear semantic identity enables effective learning. | Logical extension of embedding architecture (File 4, confidence 7) |
| System cannot learn "what kind of creative this is" if semantics change | E | 7 | Ad embedding encodes semantic meaning; changing semantics changes latent identity; practitioner consensus on consistency | Risk: HIGH \| Benefit: MAJOR<br>Unstable creative identity prevents learning accumulation. Stable identity enables knowledge compounding. | Cross-reference: File 4 creative identity (confidence 7) |
| If PS/OF/BR change, it is another system (not iteration) | C/E | 7 | Framework rule; underlying behavior: changing core semantics resets learning; semantic consistency research | Risk: HIGH \| Benefit: MAJOR<br>Treating system change as iteration wastes previous learning. Clean separation preserves each system's knowledge. | Framework rule (N/A) built on Meta behavior (semantic consistency = confidence 7) |
| One campaign = one VE (closed set) | C | N/A | Framework design rule | Risk: N/A \| Benefit: N/A<br>Framework's campaign structure | Framework organizational principle |
| One EA per campaign (never mixed) | C | N/A | Framework design rule | Risk: N/A \| Benefit: N/A<br>Framework's emotional axis discipline | Framework organizational principle |
| Stage determines optimization event, CTA, message type | E | 7 | Stage-appropriate optimization enables signal volume; verified in File 2 (confidence 7) | Risk: CRITICAL \| Benefit: TRANSFORMATIVE<br>Stage-inappropriate events cause learning failure. Stage alignment enables functional optimization. | Cross-reference: File 2 campaign=contract (confidence 7); detailed in File 7 |
| Brand role governs proof requirements, CTA strength, tone | C | N/A | Framework construct for brand positioning | Risk: N/A \| Benefit: N/A<br>Framework's brand relationship model | Framework-specific concept; not Meta terminology |
| AL (Abstraction Level) affects learnability and stage-appropriateness | C/E | 5 | Framework concept; stage-appropriateness principle plausible but unverified for abstraction specifically | Risk: LOW \| Benefit: MODERATE<br>Wrong abstraction level may reduce clarity. Appropriate level improves message comprehension. | Framework construct; abstraction-learning relationship speculative |
| CTA intensity constrained by stage, brand role, trust | C/E | 7 | Stage alignment verified; CTA mismatch creates negative signals; practitioner consensus | Risk: MEDIUM \| Benefit: SUBSTANTIAL<br>Aggressive CTA in early stages increases hide/report signals. Stage-appropriate CTA maintains quality. | CTA ranges are framework; stage-CTA alignment principle verified |
| Variable stability prevents learning destruction | E | 7 | Semantic/structural consistency supports learning; changing fundamentals resets signals | Risk: HIGH \| Benefit: MAJOR<br>Variable instability destroys accumulated learning. Stability compounds knowledge over time. | Synthesis of semantic consistency principle (confidence 7) |

**Verification Key:**
- **Type:** A=Factual Technical, B=Operator Mental Model, C=Framework Construct, D=Operational Best Practice, E=Causal Assertion
- **Confidence Scale:** 1-2=Unverified, 3-4=Speculative, 5-6=Reasonably Inferred, 7-8=Well Supported, 9-10=Verified
- **Last Updated:** 2026-02-21

**Important Distinctions:**
- **Framework Definitions (Type C, N/A):** PS, OF, BR, CS, VE, EA, AL, CTA-R, SCR are the vault's own taxonomy
- **Meta System Behavior (Type E, Scored):** Claims about how Meta's system responds when these principles are violated
- **Underlying Mechanics:** Built on verified principles: semantic consistency (File 2, 4), stage alignment (File 2), embedding architecture (File 4)

**Notes:**
- This file is primarily framework design, establishing proprietary structural controls
- The 9 variables themselves are not Meta concepts (confidence N/A)
- BUT: The behavioral claims about consistency, learnability, and semantic stability ARE verifiable against Meta's system
- High cross-referencing to foundation files where underlying mechanics were verified

**Sources:**
- [Meta Sequence Learning and Semantic Information](https://engineering.fb.com/2024/11/19/data-infrastructure/sequence-learning-personalized-ads-recommendations/)
- [Meta Ads Audience Strategy: Creative as Signal](https://rebootiq.com/meta-ads-audience-strategy/)
- Cross-references to Files 2, 4 for semantic consistency and embedding architecture

---

#structural-strategy #immutable-variables #ps #of #br #ve #ea #verification-complete
