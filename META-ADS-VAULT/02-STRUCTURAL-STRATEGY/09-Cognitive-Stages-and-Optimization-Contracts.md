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

---

## Verification Status

> This section documents the verification status of key claims and assumptions in this note. Confidence scores reflect the strength of available evidence from Meta official sources, academic research, and industry validation.

| Claim/Assumption | Type | Confidence | Evidence | Impact | Notes |
|-----------------|------|------------|----------|--------|-------|
| 4-stage model (Exploration→Identification→Validation→Decision) | C | N/A | Framework's proprietary cognitive stage taxonomy | Risk: N/A \| Benefit: N/A<br>Framework's own funnel model, not Meta terminology | Framework construct; stages are vault's structure |
| Skipping stages causes low event volume, high variance, poor learning, increased CPA, instability | E | 8 | Insufficient signal volume (<50 events) creates instability; documented delivery degradation; [Bir.ch](https://bir.ch/blog/facebook-ads-not-converting), [Code3](https://code3.com/resources/understanding-the-meta-learning-phase-why-it-matters-for-campaign-performance/) | Risk: CRITICAL \| Benefit: TRANSFORMATIVE<br>Optimizing for unperformable events causes systemic failure. Stage-appropriate events enable functional optimization. | Cross-reference: File 2 campaign=contract (confidence 7-9); core causal mechanism verified |
| Declared optimization = contract with Meta | E | 7 | Optimization event selection determines what Meta optimizes for; low-volume events cause failure; [Great Marketing](https://greatmarketing.ai/blog/is-your-facebook-custom-event-killing-optimization) | Risk: CRITICAL \| Benefit: TRANSFORMATIVE<br>Wrong declaration creates learning failure. Correct event selection enables optimization. | Cross-reference: File 2 verification (confidence 7); "contract" framing is operator model |
| ThruPlay/Video Views for Exploration stage | D | 10 | Official Meta optimization events; [Social Media Examiner](https://www.socialmediaexaminer.com/facebook-thruplay-video-ads-what-marketers-need-to-know/) | Risk: N/A \| Benefit: N/A<br>ThruPlay is documented event | Cross-reference: Glossary verification (confidence 10); stage mapping is framework |
| LPV (Landing Page View) for Identification stage | D | 10 | Official Meta optimization event; "light intent signal"; [Meta Collection Ads](https://www.cendyn.com/blog/metas-collection-ads-reporting-update-lpvs/), [Jon Loomer](https://www.jonloomer.com/split-test-which-optimization-leads-to-the-most-high-quality-traffic/) | Risk: N/A \| Benefit: N/A<br>LPV is documented event | Cross-reference: Glossary verification (confidence 10); stage mapping is framework |
| Lead for Validation stage | D | 10 | Official Meta optimization event | Risk: N/A \| Benefit: N/A<br>Lead is documented event | Meta standard event; stage mapping is framework |
| Purchase/Value for Decision stage | D | 10 | Official Meta optimization events | Risk: N/A \| Benefit: N/A<br>Purchase is documented event | Meta standard events; stage mapping is framework |
| Optimization events must match user's performable actions | E | 9 | Insufficient event volume causes learning failure; move up funnel when volume insufficient; [Bir.ch](https://bir.ch/blog/facebook-ads-not-converting), [AI-Powered Guide](https://lseo.com/paid-media/paid-social-media-marketing/understanding-the-facebook-ads-learning-phase-a-full-guide/) | Risk: CRITICAL \| Benefit: TRANSFORMATIVE<br>Unperformable events = no signals = learning failure. Performable events = signal flow = optimization. | Strongly documented; core learning phase mechanic |
| Broad targeting for Exploration; retargeting progression for later stages | D | 7 | Broad targeting with creative filtering confirmed; retargeting standard practice; [Turba Media](https://www.turbamedia.io/post/broad-targeting-vs-interest-targeting---the-definitive-2025-guide), [LeadEnforce](https://leadenforce.com/blog/interest-targeting-on-facebook-what-still-works-and-what-doesnt) | Risk: MEDIUM \| Benefit: SUBSTANTIAL<br>Wrong targeting approach for stage reduces efficiency. Stage-appropriate targeting improves signal quality. | Practitioner consensus; Advantage+ confirms broad-first approach |
| CTA intensity must match stage (passive→discover→register→buy) | E | 7 | Aggressive CTA in early stages increases hide/report; stage-CTA alignment reduces negative signals; practitioner consensus | Risk: MEDIUM \| Benefit: SUBSTANTIAL<br>CTA-stage mismatch creates quality penalties. Alignment maintains user experience quality. | Logical extension of quality signals (File 3, confidence 8); CTA ranges are framework |
| Targeting reduces uncertainty (not "finds customers") | E | 6 | Targeting helps Meta's prediction confidence; broad targeting with creative signal emerging approach; [Meta Targeting 2025](https://mrbooster.com/meta-targeting-in-2025-whats-changed-and-how-to-stay-ahead/) | Risk: LOW \| Benefit: MODERATE<br>Wrong mental model overemphasizes targeting over creative. Correct understanding balances both. | Operator mental model; creative-as-signal confirmed (File 4, confidence 8) |
| VE types (INSIGHT/VALIDATION/FRAMEWORK/SYSTEM) aligned to stages | C | N/A | Framework's message taxonomy | Risk: N/A \| Benefit: N/A<br>Framework's content structure | Cross-reference: Glossary and File 6 (both N/A); framework classification |
| Abstraction level (AL) varies by stage (high→medium→low) | C | N/A | Framework concept | Risk: N/A \| Benefit: N/A<br>Framework's abstraction guidance | Cross-reference: File 6 verification (confidence 5 for AL concept) |
| One campaign = one stage | C | N/A | Framework's campaign structure rule | Risk: N/A \| Benefit: N/A<br>Framework organizational principle | Framework design; underlying behavior (semantic consistency) verified separately |

**Verification Key:**
- **Type:** A=Factual Technical, B=Operator Mental Model, C=Framework Construct, D=Operational Best Practice, E=Causal Assertion
- **Confidence Scale:** 1-2=Unverified, 3-4=Speculative, 5-6=Reasonably Inferred, 7-8=Well Supported, 9-10=Verified
- **Last Updated:** 2026-02-21

**Important Distinctions:**
- **4-Stage Model (Type C, N/A):** Framework's proprietary funnel structure (Exploration→Identification→Validation→Decision)
- **Optimization Events (Type D, Confidence 10):** Meta's official events (ThruPlay, LPV, Lead, Purchase)
- **Stage→Event Mapping (Framework):** Which event for which stage is framework guidance
- **Underlying Mechanics (Type E, Scored):** Signal volume, learning failure, event performability - HIGHLY VERIFIED

**Key Finding:**
The 4-stage model itself is a framework construct (N/A), BUT the underlying causal mechanism it's built on is STRONGLY VERIFIED:
- Insufficient signal volume causes learning failure (confidence 9)
- Optimizing for unperformable events creates instability (confidence 8)
- Moving up funnel when volume insufficient is documented practice (confidence 9)

The framework provides structure around proven Meta mechanics.

**Sources:**
- [Facebook Ads Not Converting](https://bir.ch/blog/facebook-ads-not-converting)
- [Understanding Meta Learning Phase](https://code3.com/resources/understanding-the-meta-learning-phase-why-it-matters-for-campaign-performance/)
- [Is Your Custom Event Killing Optimization?](https://greatmarketing.ai/blog/is-your-facebook-custom-event-killing-optimization)
- [Broad Targeting vs Interest Targeting 2025](https://www.turbamedia.io/post/broad-targeting-vs-interest-targeting---the-definitive-2025-guide)
- Cross-references to Files 2, 3, 4, 6 for underlying mechanics

---

#structural-strategy #cognitive-stages #optimization #funnel #verification-complete
