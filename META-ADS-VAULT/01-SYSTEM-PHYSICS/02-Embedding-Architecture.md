# 2 — Embedding Architecture

> **Part of:** [[_MOC-System-Physics|Part I — System Physics]] | [[../00-INDEX/HOME|HOME]]
> **See also:** [[../05-REFERENCE/U-A-C-Triad-Reference|U–A–C Triad Reference]], [[03-Prediction-Heads-and-Multi-Objective-Learning|Prediction Heads]], [[../05-REFERENCE/Glossary-and-Acronyms|Glossary]]

---

## Everything Becomes Representation

Meta learns ads and users through **embeddings**: numeric representations in a high-dimensional space.

The system does not "read your ad" the way a human does. It encodes it as a **multimodal object** that includes:

- Text semantics (meaning, clarity, aggressiveness, claim intensity)
- Image/video content (faces, objects, composition, overlays, style)
- Audio (if present — tone, authority, emotional cadence)
- Temporal structure (video pacing, early retention patterns)
- Metadata (placement, format, optimization objective, device)
- Historical performance priors (smoothed aggregated statistics)

> [!formula] Ad Embedding Formula (conceptual)
> `A = f(Text + Image/Video + Audio + Temporal + Metadata + History)`

Meta learns "the ad" as **Text + Image/Video + Metadata + Historical performance**, fused into a stable latent identity.

---

## 2.1 The U–A–C Triad

At scoring time, Meta evaluates a triple:

| Component | What It Is |
|---|---|
| **U** (User) | Who the person is right now, behaviorally — their embedding |
| **A** (Ad) | What your creative "is" in latent space |
| **C** (Context) | Delivery situation: placement, session state, device, time, density, region/language |

The model estimates outcomes for that triple:

```
P(Action | U, A, C)
P(Negative Feedback | U, A, C)
P(Risk | U, A, C)
P(Future Value | U, A, C)   ← when applicable
```

→ Full reference: [[../05-REFERENCE/U-A-C-Triad-Reference|U–A–C Triad Reference]]

---

## 2.2 Why This Matters for Operators

### "Creative variety" = semantic variety
Creative variety must be measured as **semantic variety** — difference in latent representation — not random surface edits.

Changing a color palette is not creative variety.
Changing the emotional axis is semantic change (and breaks the campaign system).

### Audience targeting → creative-based filtering
As [[../02-STRUCTURAL-STRATEGY/09-Cognitive-Stages-and-Optimization-Contracts|broad targeting]] expands, the creative itself becomes the targeting signal. The ad's embedding filters for users whose behavioral embeddings align with it.

### Fatigue = embedding saturation
Fatigue is not "the user is bored." It is decreasing marginal utility under repeated exposure to the **same latent identity A**, combined with the user's embedding U updating with each exposure.

See [[06-Feedback-Loop-and-Evolution|Feedback Loop & Evolution]] and [[../04-OPERATIONAL-CONTROL/20-Fatigue-Saturation-and-Rotation|Fatigue & Rotation]].

---

## Operator Rules from This Section

> [!rule] Rule: Creative identity is latent
> You do not control your creative's latent identity directly. It emerges from structure, signals, and user reactions. Maintain consistency in inputs to maintain consistency in identity.

> [!rule] Rule: History is a prior
> Poor historical performance (high hide/report, low CVR) increases initial resistance on new ads in the same account. Build quality from the start.

---

#system-physics #embedding #uac
