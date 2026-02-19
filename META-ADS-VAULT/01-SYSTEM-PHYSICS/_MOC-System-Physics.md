 # Part I — System Physics

> **Map of Content** | [[../00-INDEX/HOME|← HOME]]

---

## Purpose

Before you can make good strategic or creative decisions, you must understand **how Meta's system actually works** at a mechanical level. This part covers the physics of the machine — how it scores, allocates, and learns.

> [!rule] Why This Matters
> You cannot optimize a system you do not understand. Most strategic errors in Meta Ads come from operators treating the platform as if it were a broadcast channel, when it is actually a prediction and allocation engine.

---

## Sections

| # | Note | What It Covers |
|---|---|---|
| 1 | [[01-The-Single-Mental-Model\|The Single Mental Model]] | Meta optimizes user state transitions, not ads. The 4 operational consequences. |
| 2 | [[02-Embedding-Architecture\|Embedding Architecture]] | How ads and users become numeric representations. The U-A-C triad. |
| 3 | [[03-Prediction-Heads-and-Multi-Objective-Learning\|Prediction Heads & Multi-Objective Learning]] | What the system predicts simultaneously. EAR, quality, risk. The utility formula. |
| 4 | [[04-Auction-Mechanics\|Auction Mechanics]] | How impressions are allocated. Bid, EAR, quality, and risk in the final score. |
| 5 | [[05-Delivery-and-Budget-Dynamics\|Delivery & Budget Dynamics]] | How budget paces, how learning phases work, why variance kills delivery. |
| 6 | [[06-Feedback-Loop-and-Evolution\|Feedback Loop & Evolution]] | How signals update the system. Micro vs. macro signals. Creative fatigue physics. |

---

## Key Concepts in This Part

- [[../05-REFERENCE/U-A-C-Triad-Reference|U–A–C Triad]] — The core scoring triple
- [[../05-REFERENCE/Glossary-and-Acronyms|EAR, pCTR, pCVR]] — Prediction head outputs
- Learning phase — the ~50-event threshold for delivery stabilization
- Variance — the delivery killer

---

## Connects To

- [[../05-REFERENCE/Introduction-Learning-System-Philosophy|Introduction — Learning System Philosophy]]
- [[../02-STRUCTURAL-STRATEGY/_MOC-Structural-Strategy|Part II — Structural Strategy]] ← apply physics here

#moc #system-physics
