# Glossary & Acronyms

> Single source of truth for all terminology used in the [[../00-INDEX/HOME|META ADS SYSTEM ENGINEERING FRAMEWORK]].

---

## Core Acronyms

| Acronym | Full Name | Definition | Primary Note |
|---|---|---|---|
| **PS** | Problem Space | The recurring human error (cognitive, emotional, behavioral) your system addresses. Must be expressible as 1 sentence + 3 observable symptoms. | [[../02-STRUCTURAL-STRATEGY/07-Immutable-Global-Variables\|07 — Immutable Global Variables]] |
| **OF** | Outcome Function | An observable state transition — what the user *does* differently after your intervention. Not aspiration; a behavioral change. | [[../02-STRUCTURAL-STRATEGY/07-Immutable-Global-Variables\|07 — Immutable Global Variables]] |
| **BR** | Brand Role | The functional brand–user relationship: direction (uni/bidirectional), intensity (low/medium/high), position (above/beside/behind). | [[../02-STRUCTURAL-STRATEGY/07-Immutable-Global-Variables\|07 — Immutable Global Variables]] |
| **CS** | Cognitive Stage | The user's current stage in the learning journey: Exploration → Identification → Validation → Decision. | [[../02-STRUCTURAL-STRATEGY/09-Cognitive-Stages-and-Optimization-Contracts\|09 — Cognitive Stages]] |
| **VE** | Value Expression Type | The type of message delivered. Closed set: INSIGHT / VALIDATION / FRAMEWORK / SYSTEM. One per campaign. | [[../02-STRUCTURAL-STRATEGY/07-Immutable-Global-Variables\|07 — Immutable Global Variables]] |
| **EA** | Emotional Axis | The emotional transition the creative facilitates (e.g., confusion → clarity). Defined per campaign; never mixed. | [[../02-STRUCTURAL-STRATEGY/07-Immutable-Global-Variables\|07 — Immutable Global Variables]] |
| **AL** | Abstraction Level | How conceptual vs. concrete the creative is. Content: high/medium. Ads: medium/low. | [[../02-STRUCTURAL-STRATEGY/07-Immutable-Global-Variables\|07 — Immutable Global Variables]] |
| **CTA-R** | CTA Intensity Range | The allowable strength of the call-to-action given stage, brand role, and trust constraints. | [[../02-STRUCTURAL-STRATEGY/07-Immutable-Global-Variables\|07 — Immutable Global Variables]] |
| **SCR** | Semantic Consistency Rules | What cannot change without creating a new system: core promise, language, immutable theme, claim limits. | [[../02-STRUCTURAL-STRATEGY/07-Immutable-Global-Variables\|07 — Immutable Global Variables]] |
| **S0** | Observable Initial State | The behavioral signal profile of the user *before* your intervention. Defined per stage. | [[../02-STRUCTURAL-STRATEGY/08-User-States-and-Observable-Signals\|08 — User States]] |
| **S1** | Target State | The measurable progression state — what the user's behavior looks like *after* engaging with your creative at a given stage. | [[../02-STRUCTURAL-STRATEGY/08-User-States-and-Observable-Signals\|08 — User States]] |
| **EAR** | Estimated Action Rate | Meta's predicted probability that a user will complete the declared optimization event if shown the ad. Conditional on U, A, and C. | [[../01-SYSTEM-PHYSICS/03-Prediction-Heads-and-Multi-Objective-Learning\|03 — Prediction Heads]] |
| **U-A-C** | User–Ad–Context Triad | The three-component scoring triple Meta evaluates at auction time. See dedicated reference. | [[U-A-C-Triad-Reference\|U-A-C Triad Reference]] |
| **pCTR** | Predicted Click-Through Rate | One prediction head output; the system's estimate of click probability given U, A, C. | [[../01-SYSTEM-PHYSICS/03-Prediction-Heads-and-Multi-Objective-Learning\|03 — Prediction Heads]] |
| **pCVR** | Predicted Conversion Rate | System's estimate of conversion probability given U, A, C. | [[../01-SYSTEM-PHYSICS/03-Prediction-Heads-and-Multi-Objective-Learning\|03 — Prediction Heads]] |
| **LPV** | Landing Page View | A Meta optimization event; user loads the landing page after clicking. Used as a light intent signal at Identification stage. | [[../02-STRUCTURAL-STRATEGY/09-Cognitive-Stages-and-Optimization-Contracts\|09 — Cognitive Stages]] |
| **CPA** | Cost Per Action | The cost to acquire one optimization event. Rises naturally with scale (marginal CPA dynamics). | [[../04-OPERATIONAL-CONTROL/19-Competitive-Density-and-Marginal-CPA\|19 — Marginal CPA]] |
| **MMAA** | Marketing Metrics Analysis Agent | Sub-System 2.11 of GrowFu v3 that assesses campaign profitability through LTV, CAC, and CAC:LTV ratios. Provides pre-launch viability gating and post-launch monitoring. | [[../04-OPERATIONAL-CONTROL/24-Marketing-Metrics-Analysis-Agent\|24 — MMAA]] |
| **LTV** | Lifetime Value | Total gross profit expected from a customer over their lifetime. Sets the ceiling for sustainable acquisition costs. Calculated via cohort projection, first-year proxy, or industry benchmarks. | [[../04-OPERATIONAL-CONTROL/23-LTV-and-Unit-Economics\|23 — LTV & Unit Economics]] |
| **CAC** | Customer Acquisition Cost | Total marketing spend required to acquire one customer. In GrowFu framework, calculated both per-stage and cumulatively across cognitive stages (Exploration → Decision). | [[../04-OPERATIONAL-CONTROL/23-LTV-and-Unit-Economics\|23 — LTV & Unit Economics]] |
| **Viable CAC Ceiling** | — | Maximum sustainable CAC given LTV (typically 30-50% of LTV). Calculated as: LTV × Safety Margin × Confidence Adjustment. Campaigns with CAC > viable ceiling destroy business value. | [[../04-OPERATIONAL-CONTROL/23-LTV-and-Unit-Economics\|23 — LTV & Unit Economics]] |
| **CAC:LTV Ratio** | — | Unit economics health metric (LTV divided by CAC). 3:1 or better = healthy; 2:1 to 3:1 = acceptable; 1:1 to 2:1 = marginal; <1:1 = unprofitable. | [[../04-OPERATIONAL-CONTROL/23-LTV-and-Unit-Economics\|23 — LTV & Unit Economics]] |
| **Expansion Physics** | — | Natural marginal CPA rise during scaling as budget expands into progressively less-aligned user embeddings. Pattern: Gradual rise over 7-14 days during active scaling (expected, not failure). Distinguished from viability degradation (CAC rise without scaling). | [[../04-OPERATIONAL-CONTROL/19-Competitive-Density-and-Marginal-CPA\|19 — Marginal CPA]] |
| **MOC** | Map of Content | An index/hub note in this Obsidian vault that organizes a section and links to its child notes. | [[../00-INDEX/HOME\|HOME]] |

---

## Key Formulas

**Expected Utility (operator mental model):**
```
Expected Utility(U,A,C) =
  [Bid × P(Action|U,A,C)] × ExperienceMultiplier(U,A,C) − RiskPenalty(U,A,C)
```

**Auction Final Score (operator mental model):**
```
FinalScore ≈ BusinessScore × QualityMultiplier − RiskPenalty
BusinessScore = Bid × EAR
QualityPenalty = f(pHide, pReport, expected_negative_feedback, post-click bounce)
RiskPenalty = g(pRisk, fraud, borderline policy)
```

---

## Value Expression Types (VE) — Closed Set

| VE | Name | Stage |
|---|---|---|
| 1 | INSIGHT | Exploration |
| 2 | VALIDATION | Exploration / Identification |
| 3 | FRAMEWORK | Identification |
| 4 | SYSTEM | Validation / Decision |

---

*Every note in this vault links here on first use of any acronym.*

---

## Verification Status

> This section documents the verification status of key claims and assumptions in this note. Confidence scores reflect the strength of available evidence from Meta official sources, academic research, and industry validation.

| Claim/Assumption | Type | Confidence | Evidence | Impact | Notes |
|-----------------|------|------------|----------|--------|-------|
| EAR (Estimated Action Rate) exists as auction component | A | 8 | Multiple industry sources confirm Meta uses EAR; [Bind Media](https://bind.media/insights/what-can-we-learn-from-how-the-meta-ads-auction-works), [Ads Analysis](https://adsanalysis.io/meta-advertising-101-mastering-estimated-action-rate-and-ad-quality-rank-for-better-campaign-performance/) | Risk: HIGH \| Benefit: MAJOR<br>Misunderstanding auction mechanics leads to wrong optimization priorities. Understanding EAR enables effective creative and targeting strategy. | Not explicitly documented by Meta, but widely confirmed by industry |
| U-A-C Triad (User-Ad-Context) as scoring inputs | B | 8 | Auction components confirmed via [LeadEnforce](https://leadenforce.com/blog/crack-the-code-what-you-need-to-know-about-the-facebook-ad-auction), [Disruptive Digital](https://disruptivedigital.agency/demystifying-the-meta-auction-how-to-win-more-ad-placements-on-facebook-and-instagram-2/) | Risk: MEDIUM \| Benefit: SUBSTANTIAL<br>Wrong mental model creates suboptimal creative decisions. Correct understanding improves ad relevance and quality. | Components verified; triad structure is operator model |
| pCTR (Predicted Click-Through Rate) as prediction head | B | 6 | Industry understanding of ML systems; Meta AI research confirms multi-task learning [Meta Engineering](https://engineering.fb.com/2024/07/10/data-infrastructure/machine-learning-ml-prediction-robustness-meta/) | Risk: LOW \| Benefit: MODERATE<br>Specific prediction head names not critical for operations. Understanding multi-objective prediction improves creative strategy. | Term used in industry; Meta confirms multi-objective learning but not specific head names |
| pCVR (Predicted Conversion Rate) as prediction head | B | 6 | Same as pCTR; Meta's multi-task learning systems [Meta Lattice](https://ai.meta.com/blog/ai-ads-performance-efficiency-meta-lattice/) | Risk: LOW \| Benefit: MODERATE<br>Similar to pCTR; understanding conversion prediction helps optimization event selection. | Industry term; multi-task learning confirmed |
| LPV (Landing Page View) optimization event | A | 10 | Official Meta optimization event; [Meta Collection Ads update](https://www.cendyn.com/blog/metas-collection-ads-reporting-update-lpvs/), [Jon Loomer testing](https://www.jonloomer.com/split-test-which-optimization-leads-to-the-most-high-quality-traffic/) | Risk: N/A \| Benefit: N/A<br>Factual; LPV is documented Meta event | Confirmed official event; definition updated June 2025 |
| CPA (Cost Per Action) definition | A | 10 | Standard industry term; [WebFX](https://www.webfx.com/social-media/pricing/how-much-does-facebook-advertising-cost/), [DashThis](https://dashthis.com/kpi-examples/facebook-cpa/) | Risk: N/A \| Benefit: N/A<br>Universal metric definition | Standard advertising terminology |
| ThruPlay optimization event (15 sec threshold) | A | 10 | Official Meta event; [Social Media Examiner](https://www.socialmediaexaminer.com/facebook-thruplay-video-ads-what-marketers-need-to-know/), [Graphed](https://www.graphed.com/blog/what-are-facebook-ad-thruplays) | Risk: N/A \| Benefit: N/A<br>Documented Meta optimization event | Official event; ≥15 seconds or completion |
| Learning phase ~50 optimization events | A | 9 | Meta Help Center states "about 50" events over 7 days; [Code3](https://code3.com/resources/understanding-the-meta-learning-phase-why-it-matters-for-campaign-performance/), [Lebesgue](https://lebesgue.io/facebook-ads/facebook-ads-learning-phase-what-you-need-to-know-2024-update) | Risk: HIGH \| Benefit: MAJOR<br>Wrong threshold causes premature changes disrupting learning. Correct threshold enables stable optimization. | Meta explicitly confirms "about 50" |
| Auction formula structure (Bid × EAR × Quality) | B | 6 | Components verified; formula structure is operator model; [LinkedIn](https://www.linkedin.com/pulse/facebook-meta-ads-auction-how-works-sarfraz-razzaq), [Marin Software](https://www.marinsoftware.com/blog/how-to-structure-for-scale-on-facebook-the-ad-auction-and-delivery-system-explained) | Risk: MEDIUM \| Benefit: SUBSTANTIAL<br>Wrong formula mental model leads to misaligned optimization. Correct understanding guides bid, creative, and quality balance. | Explicitly marked as operator mental model; Bid, EAR, Quality individually confirmed |
| Quality signals (pHide, pReport, negative feedback) | A | 8 | Meta confirms ad quality based on user feedback; [Meta Performance Scoring](https://madgicx.com/blog/meta-ads-performance-scoring), [Conv3rt](https://conv3rt.co.uk/articles/how-does-the-meta-ads-auction-system-work/) | Risk: HIGH \| Benefit: MAJOR<br>Ignoring quality signals causes auction penalties and delivery throttling. Optimizing for quality improves delivery efficiency. | Meta confirms quality metrics; specific components widely documented |
| Risk penalty mechanisms (fraud, policy proximity) | A | 7 | Industry consensus on integrity constraints; [Meta auction sources](https://www.marinsoftware.com/blog/how-to-structure-for-scale-on-facebook-the-ad-auction-and-delivery-system-explained) | Risk: HIGH \| Benefit: MAJOR<br>Policy violations cause severe delivery restrictions. Staying clear of policy edges maintains stable delivery. | Meta confirms integrity layer; specific penalty structure inferred |
| Multi-objective learning in Meta's ad system | A | 9 | Meta AI confirms via Meta Lattice, GEM, multi-task learning; [Meta Engineering](https://engineering.fb.com/2024/11/19/data-infrastructure/sequence-learning-personalized-ads-recommendations/), [Meta Andromeda](https://engineering.fb.com/2024/12/02/production-engineering/meta-andromeda-advantage-automation-next-gen-personalized-ads-retrieval-engine/) | Risk: MEDIUM \| Benefit: SUBSTANTIAL<br>Wrong understanding of multi-objective optimization limits creative strategy. Correct understanding enables balanced signal engineering. | Meta AI research explicitly confirms multi-task/multi-objective architecture |
| Embedding-based ad representation | A | 8 | Academic research confirms standard practice; [arXiv embedding research](https://arxiv.org/html/2406.05898v1), [ACM context-aware embeddings](https://dl.acm.org/doi/10.1145/2766462.2767709) | Risk: LOW \| Benefit: MODERATE<br>Understanding embedding architecture informs creative signal engineering. Specific architecture details less critical for operations. | Standard ML practice for ad systems; Meta-specific details proprietary |
| PS/OF/BR/CS/VE/EA/AL/CTA-R/SCR definitions | C | N/A | Framework's proprietary constructs | Risk: N/A \| Benefit: N/A<br>These are the vault's own definitions, not Meta terms | Framework-specific taxonomy |
| S0/S1 state definitions | C | N/A | Framework construct | Risk: N/A \| Benefit: N/A<br>Vault's behavioral state model | Framework terminology |
| Value Expression Types (INSIGHT/VALIDATION/FRAMEWORK/SYSTEM) | C | N/A | Framework taxonomy | Risk: N/A \| Benefit: N/A<br>Vault's message categorization system | Framework-specific classification |
| MOC (Map of Content) | C | N/A | Obsidian vault terminology | Risk: N/A \| Benefit: N/A<br>Vault organizational concept | Obsidian/PKM standard term |

**Verification Key:**
- **Type:** A=Factual Technical, B=Operator Mental Model, C=Framework Construct, D=Operational Best Practice, E=Causal Assertion
- **Confidence Scale:** 1-2=Unverified, 3-4=Speculative, 5-6=Reasonably Inferred, 7-8=Well Supported, 9-10=Verified
- **Last Updated:** 2026-02-21

**Sources:**
- [What Can We Learn From How The Meta Ads Auction Works](https://bind.media/insights/what-can-we-learn-from-how-the-meta-ads-auction-works)
- [Meta Advertising 101: EAR and Ad Quality Rank](https://adsanalysis.io/meta-advertising-101-mastering-estimated-action-rate-and-ad-quality-rank-for-better-campaign-performance/)
- [Understanding the Meta Learning Phase](https://code3.com/resources/understanding-the-meta-learning-phase-why-it-matters-for-campaign-performance/)
- [Meta's Machine Learning Prediction Robustness](https://engineering.fb.com/2024/07/10/data-infrastructure/machine-learning-ml-prediction-robustness-meta/)
- [Meta's Generative Ads Model (GEM)](https://engineering.fb.com/2025/11/10/ml-applications/metas-generative-ads-model-gem-the-central-brain-accelerating-ads-recommendation-ai-innovation/)
- [Meta Andromeda: Next-Gen Personalized Ads](https://engineering.fb.com/2024/12/02/production-engineering/meta-andromeda-advantage-automation-next-gen-personalized-ads-retrieval-engine/)
- [Facebook ThruPlay for Video Ads](https://www.socialmediaexaminer.com/facebook-thruplay-video-ads-what-marketers-need-to-know/)

---

#reference #glossary #verification-complete
