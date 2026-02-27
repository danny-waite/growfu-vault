# 18 — Attribution & Feedback Timing

> **Part of:** [[_MOC-Operational-Control|Part IV — Operational Control]] | [[../00-INDEX/HOME|HOME]]
> **See also:** [[../01-SYSTEM-PHYSICS/06-Feedback-Loop-and-Evolution|Feedback Loop]], [[../03-CREATIVE-ENGINEERING/14-Structured-Testing-Framework|Structured Testing]], [[21-Governance-and-Change-Management|Governance]], [[../05-REFERENCE/Glossary-and-Acronyms|Glossary]]

---

## Attribution Window Defines Feedback Timing

The attribution window you select tells the system how long after an ad impression it should look for a conversion. This directly affects:
- What signals the system uses to optimize
- What creative strategies are viable
- How fast you can make decisions

---

## Window Types and Their Creative Implications

### Short Window (e.g., 1-day click)

**What it requires:**
- Creative must produce **immediate action**
- Urgency and friction reduction dominate
- Users must be able to complete the action on first exposure

**Best for:**
- Decision-stage campaigns
- High-intent retargeting audiences
- Offers with low commitment and zero learning curve

### Longer Window (e.g., 7-day click)

**What it allows:**
- Educational creatives can perform
- Authority-building sequences make sense
- Users can see the ad, reflect, and return to convert

**Best for:**
- Validation-stage campaigns
- Consideration-phase products (higher ticket, longer decision process)
- Content-rich landing experiences

---

## The Alignment Rule

> [!rule] Always Align: Stage × Creative Type × Attribution Window
> Mismatch between creative psychology and attribution window creates **misleading feedback.**
>
> Example of mismatch: Running a 7-day attribution window on an Exploration-stage campaign optimized for ThruPlay tells you nothing useful about conversion downstream. And using a 1-day window for a high-consideration product makes educational creatives look like failures.

---

## Practical Alignment Table

| Stage | Creative Type | Attribution Window |
|---|---|---|
| Exploration | INSIGHT / problem-awareness | Not conversion-attributed — use engagement windows |
| Identification | FRAMEWORK / mechanism | 7-day click (allow deliberation) |
| Validation | SYSTEM / proof | 7-day click or 1-day view + 7-day click |
| Decision | CTA-direct / urgency | 1-day click (immediate action signal) |

---

## Feedback Latency Problem

Even with the right window, feedback takes time to arrive.

> **Do not evaluate creative performance before the minimum observation window.** (See [[21-Governance-and-Change-Management|Governance — Minimum Observation Windows]].)

Early data is disproportionately weighted toward the most impulsive users — who are not representative of your actual conversion audience. Decisions made on early data produce campaigns optimized for the wrong user profile.

---

## Common Attribution Mistakes

| Mistake | Consequence |
|---|---|
| Using 1-day window for 7-day consideration product | Systematically under-counts conversions → false "failure" signal |
| Using 7-day window for retargeting campaign | Over-attributes — conversions from other touchpoints counted as this campaign's wins |
| Changing attribution window mid-campaign | Creates data discontinuity — pre/post data is not comparable |
| Comparing campaigns with different attribution windows | Apples-to-oranges. Never valid. |

---

## Verification Status

> This section documents the verification status of key claims and assumptions in this note. Confidence scores reflect the strength of available evidence from Meta official sources, academic research, and industry validation.

| Claim/Assumption | Type | Confidence | Evidence | Impact | Notes |
|-----------------|------|------------|----------|--------|-------|
| Attribution window defines how long after impression to look for conversion | A | 9 | Meta's attribution window defines how long it can link conversion back to ad click/view; official Meta feature; [Foreplay Attribution](https://www.foreplay.co/post/where-and-how-to-use-facebook-attribution-settings-ultimate-guide), [JetFuel Guide](https://jetfuel.agency/meta-ads-attribution-settings/) | Risk: LOW \| Benefit: MODERATE<br>Understanding windows enables accurate measurement. | Meta official feature; well-documented |
| Attribution window affects optimization signals, creative strategies, decision speed | E | 8 | Window selection affects what system optimizes for; bidding relies on window; shorter = faster feedback; [Cometly Impact](https://www.cometly.com/post/attribution-window-settings-impact-on-results) | Risk: MEDIUM \| Benefit: SUBSTANTIAL<br>Wrong window misguides optimization. Appropriate window enables accurate decision-making. | Meta's automatic bidding uses attribution window for optimization |
| Meta's default: 7-day click + 1-day view | A | 9 | Meta's default attribution settings = 7-day click-through + 1-day view-through; [Triple Whale](https://www.triplewhale.com/blog/facebook-attribution), [Lebesgue](https://lebesgue.io/facebook-ads/which-facebook-ad-conversion-window-should-you-use) | Risk: LOW \| Benefit: MODERATE<br>Understanding defaults enables informed configuration. | Meta official default setting |
| Current options: 1-day click, 7-day click, 1-day view, 1-day engaged view | A | 9 | Post-iOS 14: 1-day click, 7-day click, 1-day view, 1-day engaged view; 28-day options removed; [Foreplay Guide](https://www.foreplay.co/post/where-and-how-to-use-facebook-attribution-settings-ultimate-guide) | Risk: LOW \| Benefit: MODERATE<br>Knowing available options enables proper configuration. | Meta removed longer windows for privacy compliance |
| 2026 change: Removed longer view-through windows from Insights API | A | 9 | Meta permanently removed longer view-through attribution windows from Ads Insights API (early 2026); biggest change in years; [DataSlayer 2026](https://www.dataslayer.ai/blog/meta-ads-attribution-window-removed-january-2026) | Risk: HIGH \| Benefit: MAJOR<br>Measurement window shrunk from 28 days to 1 day affects reporting. | NEW 2026 change; significant industry impact |
| Short window (1-day) requires immediate action creative | E | 7 | 1-day click window gives faster, cleaner feedback for quick-action offers; [Five Nine Strategy](https://fiveninestrategy.com/meta-attribution-lag-explained/) | Risk: MEDIUM \| Benefit: SUBSTANTIAL<br>Mismatch between creative psychology and window creates misleading feedback. | Logical alignment principle; practitioner best practice |
| Longer window (7-day) allows educational creatives, reflection time | E | 7 | Longer windows capture delayed actions; better for longer consideration products; [Cometly Impact](https://www.cometly.com/post/attribution-window-settings-impact-on-results) | Risk: MEDIUM \| Benefit: SUBSTANTIAL<br>Educational content needs time to work. Appropriate window captures delayed conversions. | Logical principle; practitioner consensus |
| Short windows under-count conversions for longer consideration products | E | 8 | Shorter windows under-report conversions; exclude conversions outside narrow timeframe; 30-40% of conversions from 8-28 day window; [AdAmigo Rules](https://www.adamigo.ai/blog/meta-ads-attribution-rules-explained), [DataSlayer 2026](https://www.dataslayer.ai/blog/meta-ads-attribution-window-removed-january-2026) | Risk: HIGH \| Benefit: MAJOR<br>Under-counting causes false "failure" signals and budget cuts. Appropriate window captures true performance. | Well-documented phenomenon; 2026 data confirms 30-40% loss |
| Longer windows over-attribute (count other touchpoints as this campaign's wins) | E | 7 | Longer windows inflate reported conversions; cast wider net backward; false attribution credits ads with minimal influence; [Cometly Impact](https://www.cometly.com/post/attribution-window-settings-impact-on-results) | Risk: MEDIUM \| Benefit: SUBSTANTIAL<br>Over-attribution overstates performance. Appropriate window provides accurate picture. | Logical consequence of longer lookback periods |
| Changing attribution window mid-campaign creates data discontinuity | E | 8 | Changing attribution settings can reset learning phase; restarts learning process; pre/post data not comparable; [ConvertBomb Learning](https://convertbomb.com/blog/facebook-ads-learning-phase-tips), [Foreplay Guide](https://www.foreplay.co/post/where-and-how-to-use-facebook-attribution-settings-ultimate-guide) | Risk: HIGH \| Benefit: MAJOR<br>Mid-campaign changes destroy comparison validity. Consistent windows enable accurate tracking. | Cross-reference: File 16 attribution window changes (confidence 8) |
| Comparing campaigns with different attribution windows is invalid | D | 9 | Apples-to-oranges comparison; different measurement standards; standard measurement methodology principle | Risk: MEDIUM \| Benefit: SUBSTANTIAL<br>Invalid comparisons lead to wrong conclusions. Consistent measurement enables valid analysis. | Universal measurement principle; widely accepted |
| Early data disproportionately weighted toward impulsive users | E | 6 | Shorter windows provide faster feedback; immediate-action users convert first; logical but not explicitly documented | Risk: MEDIUM \| Benefit: SUBSTANTIAL<br>Early-only data optimizes for wrong profile. Full observation window captures representative audience. | Logical inference; not explicitly verified in sources |
| Decisions on early data optimize for wrong user profile | E | 6 | Extension of early data bias; premature optimization targets non-representative users; practitioner understanding | Risk: MEDIUM \| Benefit: SUBSTANTIAL<br>Premature decisions create systematic mis-targeting. Patient observation enables accurate optimization. | Logical consequence; practitioner best practice |
| Attribution lag: delay between engagement and conversion | A | 8 | Attribution lag = delay between ad engagement and conversion; documented industry concept; [Five Nine Strategy](https://fiveninestrategy.com/meta-attribution-lag-explained/) | Risk: LOW \| Benefit: MODERATE<br>Understanding lag prevents premature evaluation. | Industry-standard concept; well-documented |
| Don't judge campaigns before average attribution lag passes | D | 8 | Don't judge new Meta campaigns until at least average attribution lag passed; cutting too early kills future winners; [Five Nine Strategy](https://fiveninestrategy.com/meta-attribution-lag-explained/) | Risk: HIGH \| Benefit: MAJOR<br>Premature judgment wastes potentially successful campaigns. Patience enables accurate assessment. | Industry best practice; logical waiting period |
| Minimum 50 optimization events within attribution window for learning | A | 9 | Hit ~50 optimization events within 7 days to exit learning phase; well-documented threshold; [LeadEnforce Attribution](https://leadenforce.com/blog/meta-ads-attribution-what-to-know-about-windows-delays-and-data-accuracy) | Risk: CRITICAL \| Benefit: TRANSFORMATIVE<br>Insufficient events prevent learning completion. Meeting threshold enables optimization. | Cross-reference: Files 1, 2, 16 learning phase threshold (confidence 9) |
| Stage-window alignment table (Exploration → Decision) | C/D | 6 | Framework guidance; underlying principles verified (stage optimization = confidence 9); specific window recommendations = practitioner best practice | Risk: MEDIUM \| Benefit: SUBSTANTIAL<br>Misaligned windows create misleading feedback. Proper alignment enables stage-appropriate measurement. | Framework structure (N/A) built on verified stage mechanics + logical window selection |
| Exploration: engagement windows (not conversion-attributed) | D | 7 | Exploration stage optimizes for engagement events (ThruPlay); conversion attribution inappropriate for awareness stage | Risk: MEDIUM \| Benefit: SUBSTANTIAL<br>Conversion windows on awareness campaigns mislead. Engagement focus measures appropriate outcomes. | Cross-reference: File 7 stage optimization (confidence 9); logical extension |
| Decision stage: 1-day click (immediate action signal) | D | 7 | 1-day click window appropriate for quick-action offers; immediate feedback for direct-response campaigns; [Five Nine Strategy](https://fiveninestrategy.com/meta-attribution-lag-explained/) | Risk: MEDIUM \| Benefit: SUBSTANTIAL<br>Longer windows on immediate-action offers dilute signal quality. Short windows capture true immediate intent. | Practitioner best practice; confirmed for quick-action offers |

**Verification Key:**
- **Type:** A=Factual Technical, B=Operator Mental Model, C=Framework Construct, D=Operational Best Practice, E=Causal Assertion
- **Confidence Scale:** 1-2=Unverified, 3-4=Speculative, 5-6=Reasonably Inferred, 7-8=Well Supported, 9-10=Verified
- **Last Updated:** 2026-02-21

**Important Distinctions:**
- **Meta Official Features (Type A, Confidence 9):** Attribution windows, defaults, options = Meta platform features
- **2026 Attribution Changes (Type A, Confidence 9):** Removal of longer view-through windows = MAJOR recent change
- **Attribution Mechanics (Type E, Confidence 7-8):** Under-counting, over-attribution = WELL DOCUMENTED behaviors
- **Framework Alignment Table (Type C/D, Confidence 6):** Stage-window recommendations = practitioner best practice

**Key Finding:**
Attribution and feedback timing principles STRONGLY VERIFIED by Meta documentation and 2025-2026 industry sources:
- Attribution window basics (confidence 9) - Meta official feature
- Default: 7-day click + 1-day view (confidence 9) - Meta official default
- **2026 MAJOR CHANGE:** Removed longer view-through windows from Insights API (confidence 9)
- Changing windows mid-campaign resets learning (confidence 8) - documented trigger
- Short windows under-count (confidence 8) - 30-40% conversion loss documented
- Longer windows over-attribute (confidence 7) - logical consequence
- Minimum 50 events threshold (confidence 9) - Meta official requirement
- Attribution lag concept (confidence 8) - industry standard

**Notable 2026 Discovery:**
- Meta permanently removed longer view-through attribution windows from Ads Insights API (early 2026)
- **Biggest change to Meta ads attribution in years**
- Measurement window shrunk from 28 days to 1 day
- Industry data: some advertisers had 30-40% of conversions from 8-28 day window that no longer counts

Framework provides stage-window alignment guidance around verified Meta attribution mechanics.

**Sources:**
- [The Ultimate Guide to Facebook Attribution Settings 2025](https://www.foreplay.co/post/where-and-how-to-use-facebook-attribution-settings-ultimate-guide)
- [Meta Attribution in 2025: Triple Whale Guide](https://www.triplewhale.com/blog/facebook-attribution)
- [Meta Ads Attribution Settings 2026 Guide](https://jetfuel.agency/meta-ads-attribution-settings/)
- [Meta Ads Attribution Window Changes 2026](https://www.dataslayer.ai/blog/meta-ads-attribution-window-removed-january-2026)
- [Best Attribution Windows for Meta Ads 2025](https://www.adamigo.ai/blog/best-attribution-windows-for-meta-ads-in-2025)
- [Facebook Conversion Window: 7 Days Click and 1 Day View](https://lebesgue.io/facebook-ads/which-facebook-ad-conversion-window-should-you-use)
- [Attribution Window Settings Impact On Results](https://www.cometly.com/post/attribution-window-settings-impact-on-results)
- [Meta Attribution Lag: Why Great Campaigns Look Bad At First](https://fiveninestrategy.com/meta-attribution-lag-explained/)
- [Meta Ads Attribution Rules Explained](https://www.adamigo.ai/blog/meta-ads-attribution-rules-explained)
- [Meta Ads Attribution: Windows, Delays, and Data Accuracy](https://leadenforce.com/blog/meta-ads-attribution-what-to-know-about-windows-delays-and-data-accuracy)
- Cross-references to Files 1, 2, 7, 16 for underlying mechanics

---

#operational-control #attribution #feedback-timing #windows #verification-complete
