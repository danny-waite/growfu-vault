# 4 — Auction Mechanics

> **Part of:** [[_MOC-System-Physics|Part I — System Physics]] | [[../00-INDEX/HOME|HOME]]
> **See also:** [[03-Prediction-Heads-and-Multi-Objective-Learning|Prediction Heads]], [[05-Delivery-and-Budget-Dynamics|Delivery & Budget]], [[../04-OPERATIONAL-CONTROL/19-Competitive-Density-and-Marginal-CPA|Competitive Density]], [[../05-REFERENCE/Glossary-and-Acronyms|Glossary]]

---

## The Three Core Auction Inputs

Meta does not publish an explicit formula. The auction is consistently based on three components:

1. **Bid** — what you are willing to pay
2. **[[../05-REFERENCE/Glossary-and-Acronyms|EAR]]** — Estimated Action Rate (predicted probability the user completes the objective)
3. **Ad Quality / User Experience** — predicted user experience impact

---

## How Ranking Happens (Operator-Accurate Mental Model)

> [!formula] Auction Final Score
> ```
> BusinessScore = Bid × EAR
> QualityPenalty = f(pHide, pReport, expected_negative_feedback, post-click bounce)
> RiskPenalty = g(pRisk, fraud, borderline policy)
>
> FinalScore ≈ BusinessScore × QualityMultiplier − RiskPenalty
> ```

This is not a literally published formula, but it is an **accurate operational model** for decision-making.

---

## 4.1 What Each Component Means

### A) Bid
What you are willing to pay.
Bid affects **win probability**, but not user experience constraints.

> Raising bid can win more auctions but cannot compensate for quality or risk penalties. See [[03-Prediction-Heads-and-Multi-Objective-Learning#3.3 The Most Important Operator Rule|the stability rule]].

### B) EAR (Estimated Action Rate)
The system's predicted probability that the user will complete the objective action if shown the ad.
[[../05-REFERENCE/Glossary-and-Acronyms|EAR]] is conditional on U, A, and C.

Your creative affects EAR by improving:
- **clarity** — the user understands what is being offered
- **relevance** — the user recognizes themselves in the message
- **belief shift** — the user is moved toward the action
- **friction reduction** — the path to action is clear
- **stage alignment** — the action requested matches the cognitive stage

### C) Quality / Experience
Quality is **not** aesthetic quality. It is **predicted user experience impact.**

Key quality signals:
- Probability of hide
- Probability of report
- Expected negative feedback
- Post-click bounce
- High CTR + low CVR (mismatch signal)
- Fatigue by repetition

> [!rule] Post-Click Bounce Is a Real Operational Risk
> Post-click bounce may not be an explicit auction term, but it is a plausible downstream signal affecting conversion probability, dissatisfaction, and future delivery confidence. Treat it as such regardless.

### D) Risk / Integrity
Relates to:
- Fraud/spam/abuse patterns
- Policy proximity (borderline behavior)
- Other integrity constraints

**Practical outcome:** Risk can function as a hard filter, throttling, or score penalty. Approaching policy edges increases system uncertainty and reduces distribution stability.

---

## 4.2 Competitive Reality

The auction is **relative:**

- Your ad is ranked against competitors targeting the same users in similar contexts.
- "Good" is always relative to alternative supply available at that moment.

> [!rule] Differentiation Is Not Optional
> In high-density auctions, you must win with higher **net utility**, not just higher bid. Semantic and visual differentiation is a competitive necessity, not a creative preference.

See [[../04-OPERATIONAL-CONTROL/19-Competitive-Density-and-Marginal-CPA|Competitive Density & Marginal CPA]] for how auction pressure affects your operations.

---

## Verification Status

> This section documents the verification status of key claims and assumptions in this note. Confidence scores reflect the strength of available evidence from Meta official sources, academic research, and industry validation.

| Claim/Assumption | Type | Confidence | Evidence | Impact | Notes |
|-----------------|------|------------|----------|--------|-------|
| Meta does not publish explicit auction formula | A | 10 | Confirmed by absence in Meta official docs; industry consensus on components only; [LinkedIn](https://www.linkedin.com/pulse/facebook-meta-ads-auction-how-works-sarfraz-razzaq) | Risk: N/A \| Benefit: N/A<br>Factual statement about Meta's opacity | Verified negative: no published formula found |
| Three auction inputs: Bid, EAR, Quality | A | 8 | Multiple sources confirm components; [Bind Media](https://bind.media/insights/what-can-we-learn-from-how-the-meta-ads-auction-works), [Disruptive Digital](https://disruptivedigital.agency/demystifying-the-meta-auction-how-to-win-more-ad-placements-on-facebook-and-instagram-2/) | Risk: HIGH \| Benefit: MAJOR<br>Missing any component creates incomplete optimization strategy. Understanding all three enables balanced approach. | Cross-reference: Glossary verification (confidence 8) |
| Auction formula structure (BusinessScore × Quality − Risk) | B | 6 | Components verified individually; structure is operator model; [Marin Software](https://www.marinsoftware.com/blog/how-to-structure-for-scale-on-facebook-the-ad-auction-and-delivery-system-explained) | Risk: MEDIUM \| Benefit: SUBSTANTIAL<br>Wrong formula mental model misguides optimization priorities. Correct structure informs bid-quality-risk balance. | Explicitly marked as operator mental model; components confirmed |
| Quality signals: pHide, pReport, negative feedback | A | 8 | Meta confirms user feedback impacts quality; [Madgicx Performance Scoring](https://madgicx.com/blog/meta-ads-performance-scoring), [Conv3rt](https://conv3rt.co.uk/articles/how-does-the-meta-ads-auction-system-work/) | Risk: HIGH \| Benefit: MAJOR<br>Ignoring quality signals causes delivery throttling. Optimizing quality improves auction competitiveness. | Cross-reference: Glossary verification (confidence 8) |
| Post-click bounce as quality signal | E | 7 | Post-click experience evaluated by Meta; bounce impacts future delivery cost; [Madgicx](https://madgicx.com/blog/meta-ads-performance-scoring), [Replo](https://www.replo.app/blog/how-landing-pages-affect-ad-conversion-rate) | Risk: HIGH \| Benefit: MAJOR<br>Poor landing page experience degrades ad delivery over time. Strong post-click experience improves delivery efficiency. | Explicitly noted in file as "plausible downstream signal"; confirmed by sources |
| High CTR + low CVR = mismatch signal | E | 7 | Landing page failing to close indicates relevance mismatch; [Bir.ch](https://bir.ch/blog/facebook-ads-not-converting), [Cropink](https://cropink.com/facebook-ad-metrics) | Risk: MEDIUM \| Benefit: SUBSTANTIAL<br>CTR-CVR mismatch wastes budget on unqualified clicks. Alignment improves conversion efficiency. | Behavioral pattern confirmed; indicates ad-landing page misalignment |
| Fatigue by repetition affects performance | A | 9 | Meta published research: "CTR falls with repeated exposures"; frequency >3.0 threshold; [Meta Analytics Medium](https://medium.com/@AnalyticsAtMeta/creative-fatigue-how-advertisers-can-improve-performance-by-managing-repeated-exposures-e76a0ea1084d), [Jon Loomer](https://www.jonloomer.com/creative-fatigue-meta-ads/) | Risk: HIGH \| Benefit: MAJOR<br>Ignoring fatigue causes rising costs and declining performance. Proactive creative rotation maintains efficiency. | Meta's own research confirms; strong documentation |
| Bid cannot compensate for quality/risk penalties | E | 8 | "Bad experience can't save high bids"; quality ads beat higher bids; [Disruptive Digital](https://disruptivedigital.agency/demystifying-the-meta-auction-how-to-win-more-ad-placements-on-facebook-and-instagram-2/), [Mongoose Media](https://mongoosemedia.us/how-do-facebook-ads-work-understanding-fb-ads-algorithm) | Risk: CRITICAL \| Benefit: TRANSFORMATIVE<br>Trying to outbid quality issues wastes budget without solving delivery. Quality-first approach unlocks stable delivery. | Cross-reference: File 2 verification (confidence 8); critical principle |
| Risk/integrity as hard filter or penalty | A | 7 | Policy violations cause delivery restrictions; integrity constraints confirmed; [Marin Software](https://www.marinsoftware.com/blog/how-to-structure-for-scale-on-facebook-the-ad-auction-and-delivery-system-explained) | Risk: HIGH \| Benefit: MAJOR<br>Policy proximity causes throttling and instability. Policy compliance maintains delivery confidence. | Cross-reference: Glossary verification (confidence 7) |
| Auction is competitive/relative | A | 8 | Ad ranked against competitors; "good" is relative to alternatives; [LeadEnforce](https://leadenforce.com/blog/crack-the-code-what-you-need-to-know-about-the-facebook-ad-auction), [Bind Media](https://bind.media/insights/what-can-we-learn-from-how-the-meta-ads-auction-works) | Risk: MEDIUM \| Benefit: SUBSTANTIAL<br>Absolute optimization ignores competitive context. Competitive awareness informs differentiation strategy. | Auction mechanics standard; confirmed for Meta |
| Differentiation required in high-density auctions | E | 7 | High competition requires higher net utility; creative differentiation necessary; [Disruptive Digital](https://disruptivedigital.agency/demystifying-the-meta-auction-how-to-win-more-ad-placements-on-facebook-and-instagram-2/) | Risk: HIGH \| Benefit: MAJOR<br>Generic creatives lose high-density auctions. Differentiation wins competitive placements. | Logical extension of competitive auction mechanics; practitioner consensus |
| EAR affected by clarity, relevance, belief shift, friction | E | 7 | Creative quality impacts action rate prediction; relevance and user experience drive EAR; [Ads Analysis](https://adsanalysis.io/meta-advertising-101-mastering-estimated-action-rate-and-ad-quality-rank-for-better-campaign-performance/) | Risk: MEDIUM \| Benefit: SUBSTANTIAL<br>Poor creative execution reduces predicted action rates. Optimized creative elements improve EAR and auction performance. | Logical factors; industry consensus on creative impact |

**Verification Key:**
- **Type:** A=Factual Technical, B=Operator Mental Model, C=Framework Construct, D=Operational Best Practice, E=Causal Assertion
- **Confidence Scale:** 1-2=Unverified, 3-4=Speculative, 5-6=Reasonably Inferred, 7-8=Well Supported, 9-10=Verified
- **Last Updated:** 2026-02-21

**Sources:**
- [Creative Fatigue: Meta Analytics Research](https://medium.com/@AnalyticsAtMeta/creative-fatigue-how-advertisers-can-improve-performance-by-managing-repeated-exposures-e76a0ea1084d)
- [Demystifying the Meta Auction](https://disruptivedigital.agency/demystifying-the-meta-auction-how-to-win-more-ad-placements-on-facebook-and-instagram-2/)
- [Meta Ads Performance Scoring](https://madgicx.com/blog/meta-ads-performance-scoring)
- [Landing Pages Affect Ad Conversion Rate](https://www.replo.app/blog/how-landing-pages-affect-ad-conversion-rate)
- [Facebook Ads Not Converting in 2026](https://bir.ch/blog/facebook-ads-not-converting)
- [Creative Fatigue Prevention - Jon Loomer](https://www.jonloomer.com/creative-fatigue-meta-ads/)

---

#system-physics #auction #ear #scoring #verification-complete
