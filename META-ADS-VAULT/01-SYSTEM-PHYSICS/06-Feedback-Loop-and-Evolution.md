# 6 — Feedback Loop & Evolution

> **Part of:** [[_MOC-System-Physics|Part I — System Physics]] | [[../00-INDEX/HOME|HOME]]
> **See also:** [[05-Delivery-and-Budget-Dynamics|Delivery & Budget]], [[../02-STRUCTURAL-STRATEGY/08-User-States-and-Observable-Signals|User States]], [[../04-OPERATIONAL-CONTROL/18-Attribution-and-Feedback-Timing|Attribution Timing]], [[../05-REFERENCE/Glossary-and-Acronyms|Glossary]]

---

## The System Updates Users, Ads, and Allocation

Every exposure generates signals. The system processes these signals to update its predictions — about ads, about users, and about how to allocate budget going forward.

---

## Signal Taxonomy

| Signal Type | Examples | Volume |
|---|---|---|
| **Attention signals** | Watch time, completion %, hold rate | High |
| **Light intent signals** | [[../05-REFERENCE/Glossary-and-Acronyms|LPV]], scroll depth, time on page, profile click | Medium |
| **Rejection signals** | Hide, report, negative feedback, skip < 1s | Medium |
| **Deep actions** | Lead, purchase, value | Low |

---

## 6.1 Micro-Signals vs. Macro-Signals

### Micro-signals (high volume) — help the system learn fast:
- early retention (first 3 seconds)
- dwell time
- scroll patterns
- partial completion

### Macro-signals (lower volume) — determine business outcome:
- lead
- purchase
- value

> [!rule] Creative Must Produce Both
> 1. Strong micro-signals in early frames/lines → enables fast learning
> 2. Coherent progression into macro-signals → validates business outcome

A creative that generates strong micro-signals but weak macro-signals is creating **false learning** — the system thinks it's performing, but the business is not moving.

See [[../03-CREATIVE-ENGINEERING/12-Micro-Signal-Optimization|Micro-Signal Optimization]] for engineering tactics.

---

## 6.2 User Embedding Updates (State Evolution)

When users see your creative:
- their response updates their **latent representation** (U embedding),
- future predictions change,
- the same creative can become less effective (**fatigue**) or even harmful (**saturation**).

> **Fatigue** is not only repetition. It is **decreasing marginal value** under updated user state.
> **Saturation** is when repeated exposure produces **rejection signals.**

These are different conditions requiring different interventions. See [[../04-OPERATIONAL-CONTROL/20-Fatigue-Saturation-and-Rotation|Fatigue, Saturation & Rotation]].

---

## 6.3 System Evolution Over Time

Over time, you will observe:
- creative families stabilize → then decay,
- costs rise as you expand to less-aligned users (marginal [[../05-REFERENCE/Glossary-and-Acronyms|CPA]]),
- delivery shifts across surfaces,
- portfolios require rotation.

This is not failure. It is the natural physics of a learning system expanding into marginal user embeddings.

> [!rule] You Need Systematic Infrastructure for Evolution
> - Fatigue/saturation diagnostics (defined thresholds, not gut feel)
> - Rotation protocols (structured, not reactive)
> - Structured creative exploration (new families before old ones die)

See [[../04-OPERATIONAL-CONTROL/20-Fatigue-Saturation-and-Rotation|Fatigue & Rotation Protocol]] and [[../03-CREATIVE-ENGINEERING/13-Creative-Identity-and-Portfolio-Architecture|Portfolio Architecture]].

---

## False Learning Patterns to Diagnose

| Pattern | What It Signals |
|---|---|
| High CTR + low watch time | Clickbait hook → false positive micro-signal |
| [[../05-REFERENCE/Glossary-and-Acronyms|LPV]] + bounce < 5 seconds | Landing mismatch → friction spike |
| Fast low-quality leads | No cognitive progression → poor future value |

---

#system-physics #feedback #signals #fatigue #evolution
