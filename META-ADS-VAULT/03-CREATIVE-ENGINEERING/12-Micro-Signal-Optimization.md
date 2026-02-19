# 12 — Micro-Signal Optimization

> **Part of:** [[_MOC-Creative-Engineering|Part III — Creative Engineering]] | [[../00-INDEX/HOME|HOME]]
> **See also:** [[11-Multimodal-Creative-Design|Multimodal Creative Design]], [[14-Structured-Testing-Framework|Structured Testing]], [[../01-SYSTEM-PHYSICS/06-Feedback-Loop-and-Evolution|Feedback Loop]], [[../01-SYSTEM-PHYSICS/03-Prediction-Heads-and-Multi-Objective-Learning|Prediction Heads]], [[../05-REFERENCE/Glossary-and-Acronyms|Glossary]]

---

## The First 2–3 Seconds Determine Embedding Positioning

Before the system has any macro-signal (lead, purchase), it is learning from **micro-signals.** These early behavioral signals are the highest-volume data the system has about how your ad is performing.

> [!rule] The Hook Is a Signal Engineering Problem
> The first 2-3 seconds of a video, or the first line of a static ad, do not just capture human attention. They generate the early retention signals the system uses to position the ad's embedding and allocate initial budget.

---

## Micro-Signal Inventory

| Signal | What It Measures |
|---|---|
| **Hold rate** | % of users who don't scroll past in first 1-3 seconds |
| **Scroll stop** | Whether the creative arrests mid-scroll |
| **Early drop-off** | % who leave within first 3 seconds |
| **Partial completion** | How far through the video / copy users get |
| **View > 3s** | Low-intent attention signal |
| **View > 6s** | Meaningful attention signal — used as optimization event at Exploration stage |
| **Completion rate** | Strongest attention signal for video |

---

## 12.1 What You Must Design For

In the first 2-3 seconds:

1. **Immediate clarity** — the user must understand what this is about without effort
2. **Immediate relevance** — the user must see themselves in the content
3. **Pattern interrupt** — the creative must break scroll-momentum
4. **Cognitive anchor** — an idea or image that earns continued attention

These are not just creative principles. They are **signal generation requirements.**

---

## 12.2 Hook Architecture

A well-engineered hook serves two masters simultaneously:

| For the Human | For the System |
|---|---|
| Triggers recognition or curiosity | Generates hold rate (early retention signal) |
| Establishes relevance immediately | Reduces early drop-off |
| Promises a payoff worth attention | Supports high partial completion rates |
| Aligns with user's current cognitive stage | Consistent with declared optimization event |

> [!rule] Hook Must Be Matched to Stage
> An Exploration-stage hook (curiosity, problem recognition) generates different micro-signals than a Decision-stage hook (urgency, social proof). Using the wrong hook for the stage produces confusing signal data.

---

## 12.3 The Payoff Problem

High micro-signals + low macro-signals = the payoff problem.

If your hook generates strong hold rate and partial completion, but the landing page or offer doesn't fulfill the promise:

- [[../05-REFERENCE/Glossary-and-Acronyms|pCTR]] ↑ + [[../05-REFERENCE/Glossary-and-Acronyms|pCVR]] ↓ = mismatch
- The system detects CTR-CVR dissonance as a quality signal
- Variance increases
- Delivery confidence drops

> [!rule] The Hook Must Pay Off
> Every signal the hook generates must have a path to the macro-signal. Curiosity that is never resolved is not just a bad user experience — it is a delivery problem.

---

## 12.4 Strong Micro-Signals Accelerate Learning

The practical benefit of engineering micro-signals well:

- The system accumulates signal volume **faster** from the same budget
- The learning phase ([[../01-SYSTEM-PHYSICS/05-Delivery-and-Budget-Dynamics|~50 optimization events]]) is reached sooner
- Budget allocation confidence increases earlier
- CPA stability arrives faster

This is why creative quality at the micro-signal level is not an aesthetic preference — it is **a budget efficiency mechanism.**

---

## Micro-Signal Design Principles

- Open with a human behavior or problem recognition (not a brand logo)
- Make the central tension visible in the first 3 seconds
- Use text overlays for muted scroll environments
- Pacing: first moment must be slower/clearer than the rest
- Audio hook must work even for users who only watch the first 3 seconds muted

---

#creative-engineering #micro-signals #hooks #retention
