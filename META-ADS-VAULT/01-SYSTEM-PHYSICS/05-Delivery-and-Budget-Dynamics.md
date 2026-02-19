# 5 — Delivery & Budget Dynamics

> **Part of:** [[_MOC-System-Physics|Part I — System Physics]] | [[../00-INDEX/HOME|HOME]]
> **See also:** [[04-Auction-Mechanics|Auction Mechanics]], [[06-Feedback-Loop-and-Evolution|Feedback Loop]], [[../04-OPERATIONAL-CONTROL/17-Budget-Variance-and-Stability|Budget & Stability]], [[../05-REFERENCE/Glossary-and-Acronyms|Glossary]]

---

## Why Great Creatives Sometimes Do Not Scale

Auction selection answers: *"Who wins this impression?"*
Delivery answers: *"How do we allocate budget over time and across ads/ad sets?"*

These are different systems. Winning auctions does not guarantee delivery efficiency.

Delivery is influenced by:
- Learning phase status
- Signal volume
- Variance / stability
- Pacing requirements
- Recent performance confidence
- Account-level constraints (trust, policy history, etc.)

---

## 5.1 The Learning Phase Constraint

Your system must generate enough optimized events to stabilize prediction.

> A widely used operational threshold is ~**50 optimization events per ad set**, but the exact implementation is internal to Meta.

> [!rule] Fragmentation Kills Learning
> If you fragment too many ad sets, you starve learning everywhere.
> If you change too many variables at once, you reset meaning and destroy attribution.

See [[../04-OPERATIONAL-CONTROL/16-Campaign-and-Ad-Set-Architecture|Campaign Architecture]] for concentration rules.

---

## 5.2 Pacing (Spend Smoothing)

The system must pace spend:
- across the day,
- across opportunities,
- without exhausting the audience too early,
- while pursuing the optimization objective.

**If your performance is volatile, pacing confidence drops.**

The system cannot smoothly distribute budget if it cannot predict where the next conversion will come from.

---

## 5.3 Variance as a Delivery Killer

High variance means:
- unstable conversion velocity,
- inconsistent post-click behavior,
- inconsistent quality signals.

**Delivery implication:** The system allocates **less budget** to unstable ads because it cannot predict marginal returns confidently.

> [!rule] Stability Is a Creative Requirement
> Variance is not just a media buying problem. It is a creative engineering problem.
>
> Hooks that generate curiosity without payoff → CTR spikes + CVR collapse = variance.
> Variance signals uncertainty. Uncertainty reduces allocation confidence.

---

## 5.4 Budget Buys Learning, Not Results

> [!rule] Early Spend Is Partly Education Cost
> Early spend is partly "education cost" for the model.
> If you do not protect learning with **semantic stability**, that spend becomes wasted noise.

Implications:
- Do not launch campaigns you are not ready to let run.
- Do not change the creative during the learning phase.
- Do not make large budget cuts mid-learning.

See [[../04-OPERATIONAL-CONTROL/17-Budget-Variance-and-Stability|Budget, Variance & Stability]] for operational rules on budget management.

---

## Connected Notes

- [[../04-OPERATIONAL-CONTROL/16-Campaign-and-Ad-Set-Architecture|→ Campaign Architecture]] — how to concentrate signal density
- [[../04-OPERATIONAL-CONTROL/17-Budget-Variance-and-Stability|→ Budget & Stability]] — operational rules for budget management
- [[../02-STRUCTURAL-STRATEGY/10-Learning-Continuity-Across-Stages|→ Learning Continuity]] — protecting learning across stage transitions

#system-physics #delivery #budget #learning-phase #variance
