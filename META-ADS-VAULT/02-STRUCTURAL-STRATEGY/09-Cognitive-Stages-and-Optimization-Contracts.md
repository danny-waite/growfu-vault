# 9 — Cognitive Stages & Optimization Contracts

> **Part of:** [[_MOC-Structural-Strategy|Part II — Structural Strategy]] | [[../00-INDEX/HOME|HOME]]
> **See also:** [[07-Immutable-Global-Variables|Immutable Global Variables]], [[08-User-States-and-Observable-Signals|User States]], [[10-Learning-Continuity-Across-Stages|Learning Continuity]], [[../04-OPERATIONAL-CONTROL/16-Campaign-and-Ad-Set-Architecture|Campaign Architecture]], [[../05-REFERENCE/Glossary-and-Acronyms|Glossary]]

---

## Stages Are Learning Constraints, Not Marketing Theory

**Exploration → Identification → Validation → Decision**

Each stage:
- Has **one objective**
- Uses **one Value Expression Type** ([[../05-REFERENCE/Glossary-and-Acronyms|VE]])
- Uses **one dominant optimization event**
- Allows **one CTA intensity range**
- Uses **specific targeting logic**

---

## 9.1 Hard Rule: Stages Are Never Skipped

> [!rule] Never Skip Stages
> If the user cannot consistently perform an action, declaring that optimization creates:
> - Low event volume
> - High variance
> - Poor learning
> - Increased [[../05-REFERENCE/Glossary-and-Acronyms|CPA]]
> - Instability in delivery
>
> Skipping stages increases system uncertainty. Uncertainty reduces allocation confidence.

**Critical error:** Optimizing for purchase without consistent purchase signal volume.
**Fix:** Move one stage up temporarily until signal density stabilizes. This protects learning.

---

## 9.2 Declared Optimization = Contract with Meta

When you choose an optimization event, you declare to the system: *"This is the behavior I want you to predict and maximize."*

### Main Optimization Events Per Stage

| Stage | Optimization Event |
|---|---|
| **Exploration** | ThruPlay / Video Views |
| **Identification** | [[../05-REFERENCE/Glossary-and-Acronyms|LPV]] (Landing Page Views) |
| **Validation** | Lead |
| **Decision** | Purchase / Value |

---

## 9.3 Targeting Logic Per Stage

> Targeting does not "find customers." It **reduces uncertainty** about who to show the ad to.

| Stage | Targeting Approach |
|---|---|
| **Exploration** | Broad, Advantage+, no heavy retargeting |
| **Identification** | Soft retargeting (viewers, engagers), broad lookalikes |
| **Validation** | Strong retargeting (LPV/leads), smaller lookalikes optional |
| **Decision** | Pure retargeting, short windows, clear exclusions |

> [!rule] Targeting Must Match Cognitive State, Not Aspiration
> Showing a Decision-stage ad (Buy Now) to Exploration-stage users increases rejection signals and wastes budget.

---

## 9.4 CTA Intensity Per Stage

**CTA changes only when state changes. CTA misalignment increases negative signals.**

| Stage | CTA Intensity | Examples |
|---|---|---|
| **Exploration** | Passive / curiosity-based | "See how it works" |
| **Identification** | Informational | "Learn more", "Discover" |
| **Validation** | Commitment signal | "Register", "Get access" |
| **Decision** | Action / purchase | "Buy", "Join", "Start" |

---

## 9.5 Stage Summary Table

| Dimension | Exploration | Identification | Validation | Decision |
|---|---|---|---|---|
| **Objective** | Awareness of problem | Recognition of self | Trust in mechanism | Execute action |
| **VE Type** | INSIGHT / VALIDATION | FRAMEWORK | FRAMEWORK / SYSTEM | SYSTEM |
| **Optimization** | ThruPlay / VV | LPV | Lead | Purchase / Value |
| **Targeting** | Broad / Advantage+ | Soft retargeting | Strong retargeting | Pure retargeting |
| **CTA Level** | Passive | Discover | Register | Buy |
| **AL (Abstraction)** | High-Medium | Medium | Medium-Low | Low |

---

## Connected Notes

- [[08-User-States-and-Observable-Signals|→ User States]] — S0/S1 per stage
- [[10-Learning-Continuity-Across-Stages|→ Learning Continuity]] — preserving learning across transitions
- [[../04-OPERATIONAL-CONTROL/16-Campaign-and-Ad-Set-Architecture|→ Campaign Architecture]] — one campaign = one stage rule
- [[../04-OPERATIONAL-CONTROL/17-Budget-Variance-and-Stability|→ Budget & Stability]] — budget requirements per stage depth

#structural-strategy #cognitive-stages #optimization #funnel
