# U–A–C Triad Reference

> **See also:** [[Glossary-and-Acronyms|Glossary]], [[../01-SYSTEM-PHYSICS/02-Embedding-Architecture|Embedding Architecture]], [[../01-SYSTEM-PHYSICS/04-Auction-Mechanics|Auction Mechanics]], [[../03-CREATIVE-ENGINEERING/11-Multimodal-Creative-Design|Multimodal Creative Design]]

---

## Definition

At scoring time, Meta evaluates a triple:

| Component | Symbol | What It Is |
|---|---|---|
| **User** | U | User embedding — who the person is *right now*, behaviorally |
| **Ad** | A | Ad embedding — what your creative "is" in latent space |
| **Context** | C | Context embedding — delivery situation: placement, session state, device, time, density, region/language |

---

## The Core Prediction

```
P(Action | U, A, C)
```

The model estimates the probability of the optimization event occurring, *given* the specific combination of user, ad, and context.

The system also simultaneously estimates:

```
P(Negative Feedback | U, A, C)
P(Risk | U, A, C)
P(Future Value | U, A, C)   ← when applicable
```

---

## Why This Is Not "Ad Performance"

The U-A-C triad means there is no such thing as an ad that is "good" in isolation.

An ad is good **for a specific (U, A, C) combination.**

> [!rule] No creative is inherently good.
> It is good for a specific (user, context) pairing. A creative that performs well for a narrow, aligned audience may perform poorly when expanded to less-aligned user embeddings.

---

## Operator Implications

### 1. Creative variety = semantic variety
"Creative variety" must be measured as **semantic variety** (difference in latent space), not random surface edits. See [[../03-CREATIVE-ENGINEERING/13-Creative-Identity-and-Portfolio-Architecture|Portfolio Architecture]].

### 2. Audience targeting → creative-based filtering
As broad targeting expands, **the creative itself acts as the targeting signal** — filtering for users whose embeddings match the ad's latent identity.

### 3. Fatigue = embedding saturation
Fatigue is not just repetition. It is decreasing marginal utility under repeated exposure to the same latent identity (A). The user's embedding (U) updates with each exposure, changing P(Action | U, A, C) over time. See [[../04-OPERATIONAL-CONTROL/20-Fatigue-Saturation-and-Rotation|Fatigue & Rotation]].

### 4. Context is not a message variable
Context (C) includes placement, format, device, time. You manage C through ad set structure. You do **not** change the ad message to match context — you change the format. See [[../04-OPERATIONAL-CONTROL/16-Campaign-and-Ad-Set-Architecture|Campaign Architecture]].

---

## What Builds the Ad Embedding (A)

The system encodes your ad as a **multimodal object**:

- Text semantics (meaning, clarity, aggressiveness, claim intensity)
- Image/video content (faces, objects, composition, overlays, style)
- Audio (tone, authority, emotional cadence)
- Temporal structure (video pacing, early retention patterns)
- Metadata (placement, format, optimization objective, device)
- Historical performance priors (smoothed aggregated statistics)

> [!formula] Ad Embedding Inputs
> `A = f(Text + Image/Video + Audio + Temporal + Metadata + History)`

Changing any of these meaningfully shifts A — which means you are now asking the system to learn a different ad identity. See [[../03-CREATIVE-ENGINEERING/11-Multimodal-Creative-Design|Multimodal Creative Design]].

---

#reference #triad #embedding #uac
