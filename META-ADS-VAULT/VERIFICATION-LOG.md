# Verification Research Log

> Comprehensive log of all research activities, sources consulted, and findings during the GrowFu v3 Specification Vault verification process.

**Project Start Date:** 2026-02-21
**Verification Methodology:** See [[VERIFICATION-STANDARDS]]
**Progress Tracking:** See [[VERIFICATION-SUMMARY]] (created upon completion)

---

## Log Structure

Each entry includes:
- **Date:** Research session date
- **File(s):** File(s) being verified
- **Claims Researched:** Specific claims investigated
- **Sources Consulted:** URLs and resources checked
- **Key Findings:** What was discovered
- **Negative Results:** Searches that yielded no results (important for documenting gaps)
- **Confidence Assigned:** Final confidence scores with justification
- **Follow-up Questions:** Items needing additional research

---

## Research Sessions

### Session 1: 2026-02-21 - Foundation Setup

**File(s):** VERIFICATION-STANDARDS.md, VERIFICATION-LOG.md (this file)
**Activity:** Created foundational documents for verification process

**Claims Researched:** N/A (setup phase)

**Sources Consulted:**
- Plan document: /Users/danny/.claude/plans/magical-nibbling-shore.md
- Explored vault structure (32 files identified)

**Key Findings:**
- Vault contains mix of Meta system claims, framework constructs, operator models
- 32 files across 5 sections requiring verification
- Processing order: Foundation → Framework → Creative → Operational → Remaining

**Next Steps:**
- Begin Phase 1 verification: Glossary-and-Acronyms.md
- Establish Meta documentation baseline for terminology

---

### Session 2-10: 2026-02-21 - Phase 1 & 2 Completed

**Files Verified:**
- File 1: Glossary-and-Acronyms.md (17 claims)
- File 2: 01-The-Single-Mental-Model.md (9 claims)
- File 3: 04-Auction-Mechanics.md (12 claims)
- File 4: 02-Embedding-Architecture.md (10 claims)
- File 5: 03-Prediction-Heads-and-Multi-Objective-Learning.md (13 claims)
- File 6: 07-Immutable-Global-Variables.md (12 claims)
- File 7: 09-Cognitive-Stages-and-Optimization-Contracts.md (14 claims)
- File 8: 08-User-States-and-Observable-Signals.md (12 claims)
- File 9: 10-Learning-Continuity-Across-Stages.md (12 claims)

**Status:** All verification tables completed and added to files
**Total Claims Verified:** 111 claims across foundation and strategic framework files

**Key Findings:**
- Meta's multi-objective learning STRONGLY verified (confidence 9)
- Learning phase ~50 events threshold VERIFIED (confidence 9)
- Quality cannot be offset by bid (confidence 8)
- Framework constructs (PS/OF/BR, 4-stage model, S0/S1) are framework-specific but built on verified Meta behavior
- Heavy cross-referencing established consistency across files

---

### Session 11: 2026-02-21 - File 10: 11-Multimodal-Creative-Design.md

**Claims Researched:**
- Multimodal ad representation (text, image, video, audio, metadata)
- Faces in ads increasing attention and engagement
- Performance priors affecting new ads
- Creative identity emergence from signals
- Production style signaling brand positioning

**Sources Consulted:**
- Multimodal embeddings research (TowardsDataScience, arXiv)
- Face effectiveness studies (Adwerx, Georgia Tech Instagram study, PMC)
- Account quality research (Digital Exchange, Reporting Ninja)
- Meta engineering blogs on embeddings

**Key Findings:**
- Faces in ads: 91.7% more attention, 38% more likes, 32% more comments (confidence 8)
- Multimodal embeddings standard ML practice, confirmed for Meta (confidence 8)
- Performance priors (CTR/CVR/negative feedback history) affect new ads (confidence 8)
- Creative identity latent and emerges from signals (confidence 7)

**Negative Results:**
- Production style (UGC vs polished) effects less documented; practitioner consensus only (confidence 6)

**Confidence Assigned:**
- Multimodal embedding: 8 (standard ML practice confirmed)
- Faces effectiveness: 8 (strong research evidence)
- Performance priors: 8 (documented account quality effects)
- Creative identity emergence: 7 (practitioner consensus + embedding logic)
- Production style signaling: 6 (plausible but less verified)

---

### Session 12: 2026-02-21 - File 11: 12-Micro-Signal-Optimization.md

**Claims Researched:**
- First 2-3 seconds determining engagement
- Hook rate and hold rate as measurable metrics
- 3-second and 6-second video view thresholds
- Completion rate as algorithm signal
- CTR-CVR mismatch as quality signal
- Micro-signals accelerating learning phase
- Text overlays for muted autoplay
- Creative quality as budget efficiency mechanism

**Sources Consulted:**
- Vaizle: Hook Rate and Hold Rate formulas and benchmarks
- LeadSync: Understanding 3-Second Video Views on Meta
- Gino Gagliardi: Hook Rate and Hold Rate 2025 Guide
- Billo App: Meta Ads Best Practices
- Code3: Understanding the Meta Learning Phase
- LeadEnforce: Text Overlays for Meta Ads
- Verde Media: Meta Ads Creative Guide 2026
- Short Vids: Facebook CTR Benchmarks

**Key Findings:**
- **First 3 seconds critical:** 63% of top ads deliver message in 3s; 90% bounce without hook (confidence 8)
- **Hook rate benchmarks:** 25-35% standard, calculated as (3s views ÷ impressions) × 100 (confidence 8)
- **Hold rate benchmarks:** 40-50% standard, calculated as 15s views ÷ 3s views (confidence 8)
- **3-second views:** Official Meta metric, captures initial engagement (confidence 8)
- **Completion rate:** Most important signal; Reels watched to completion get massive distribution boost (confidence 8)
- **Videos <15s:** 53.7% completion vs 29.4% for longer formats (confidence 8)
- **Text overlays:** Meta explicitly recommends for muted autoplay; videos autoplay silently (confidence 9)
- **Creative quality:** 70-80% of Meta ad performance stems from creative, not spend (confidence 7)
- **Users decide in 1-3 seconds:** Average 1.7 seconds mobile attention span (confidence 8)

**Negative Results:**
- 6-second views as official Meta optimization event: Not explicitly documented (confidence 6 - industry practice)
- Hook-stage matching mechanics: Framework principle, less direct verification (confidence 6)

**Confidence Assigned:**
- First 2-3 seconds critical: 8 (strong behavioral data)
- Hook/hold rate metrics: 8 (industry standard with benchmarks)
- 3-second views: 8 (official Meta metric)
- 6-second views: 6 (industry usage, not official event)
- Completion rate importance: 8 (algorithm behavior confirmed)
- CTR-CVR mismatch: 7 (cross-referenced from Files 1, 3, 8)
- Micro-signals accelerate learning: 7 (logical extension of learning phase)
- Text overlays: 9 (Meta official best practice)
- Creative quality efficiency: 7 (industry consensus)

**Follow-up Questions:**
- Is 6-second view an official Meta optimization event or industry approximation?
- Answer: Industry practice/approximation; not explicitly documented by Meta

---

### Session 13: 2026-02-21 - File 12: 13-Creative-Identity-and-Portfolio-Architecture.md

**Claims Researched:**
- Creative fatigue and saturation mechanics
- Portfolio rotation and learning continuity
- Latent creative identity in embedding space
- Meta Andromeda: Entity IDs and Creative Similarity Score
- Portfolio size recommendations (3-5 creatives)
- Creative refresh frequency
- Semantic consistency maintaining identity

**Sources Consulted:**
- [Meta Andromeda: How It Works](https://www.admove.ai/blog/meta-andromeda-guide)
- [Meta Andromeda Explained: Entity IDs](https://adsuploader.com/blog/meta-andromeda)
- [Creative Similarity Penalties Under Andromeda](https://ppcblogpro.com/how-andromeda-detects-and-punishes-ad-duplication/)
- [Meta's New Creative Similarity Score](https://www.dataally.ai/blog/metas-new-metrics-and-why-the-creative-similarity-score-matters)
- [Creative Fatigue and Similarity Score Guide](https://www.admetrics.io/en/post/meta-creative-fatigue-and-similarity-score-complete-guide)
- [Facebook Ad Algorithm Changes for 2026](https://www.socialmediaexaminer.com/facebook-ad-algorithm-changes-for-2026-what-marketers-need-to-know/)
- [How to Beat Facebook Ad Fatigue: 12 Strategies](https://bir.ch/blog/facebook-ad-fatigue)
- [Ultimate Guide to Creative Testing 2025](https://motionapp.com/blog/ultimate-guide-creative-testing-2025)

**Key Findings (MAJOR DISCOVERY):**
- **Meta Andromeda update (late 2024):** NEW official metrics released - Creative Similarity Score and Creative Fatigue
- **Entity IDs confirmed:** Meta assigns Entity IDs representing semantic fingerprints; creatives grouped by semantic/visual signatures (confidence 8)
- **Creative Similarity Score:** OFFICIAL new metric (confidence 9); high similarity = higher CPMs; Andromeda punishes repetitive content
- **Creative diversity > volume:** Andromeda algorithmic shift prioritizes diversity (confidence 8)
- **Portfolio size 3-5 optimal:** Meta technical limit = 5 per ad set; industry consensus 3-5 for testing (confidence 8)
- **Refresh frequency:** 2-4 weeks depending on spend; small accounts monthly, large budgets weekly (confidence 8)
- **Rising CPMs signal fatigue:** Creative Fatigue metric officially released by Meta (confidence 8)

**Confidence Assigned:**
- Latent creative identity as embedding cluster: 8 (NOW VERIFIED with Andromeda Entity IDs)
- Creative Similarity Score: 9 (OFFICIAL Meta metric, late 2024 release)
- Creative diversity matters more than volume: 8 (Andromeda shift documented)
- 3-5 creatives optimal: 8 (Meta limit + industry consensus)
- Semantic consistency maintains identity: 8 (Andromeda grouping mechanics)

**Notable Impact:**
- File 4 creative identity claims UPGRADED from confidence 7 to 8 based on Andromeda Entity ID verification
- Meta Andromeda provides strong new evidence for portfolio architecture principles previously rated at confidence 7

---

### Session 14: 2026-02-21 - File 13: 14-Structured-Testing-Framework.md

**Claims Researched:**
- A/B testing fundamentals (one variable at a time)
- Statistical significance thresholds (50-100+ conversions)
- Test duration recommendations (7-day minimum)
- Learning phase evaluation timing
- Attribution window consistency
- Pre-defined evaluation criteria

**Sources Consulted:**
- [A/B Testing Meta Ads: Best Practices](https://www.straightnorth.com/blog/a-b-testing-meta-ads-how-to-refine-your-campaigns-for-better-roi/)
- [A/B Testing in Meta Ads: Methodology](https://medium.com/illuminations-mirror/a-b-testing-in-meta-ads-methodology-and-best-practices-fc448c8cd7fd)
- [10 Facebook Ads A/B Testing Strategies](https://madgicx.com/blog/a-b-testing-facebook)
- [Meta Split Testing 101](https://getelevar.com/facebook/meta-split-testing/)
- [How to A/B Test Meta Ad Creatives](https://madgicx.com/blog/meta-creative-ab-testing)
- [Creative Testing Framework](https://bir.ch/blog/creative-testing-framework)
- [A/B Testing vs Multivariate Testing](https://metadata.io/resources/blog/ab-testing-vs-multivariate-testing/)
- [Meta Ads Attribution Settings](https://jetfuel.agency/meta-ads-attribution-settings/)

**Key Findings:**
- **One variable at a time:** UNIVERSAL testing principle (confidence 9); "test one element at a time—you won't know which change drove results"
- **50 events for stability:** Meta official threshold ~50 conversion events within 7 days (confidence 9)
- **7-day minimum duration:** Meta recommends 7-30 days; industry standard 7-14 days (confidence 9)
- **Statistical significance:** 50+ conversions per variation for significance; 100-1,000+ for strong confidence (confidence 8)
- **Attribution window consistency:** Changing settings restarts learning; required for fair comparison (confidence 8)
- **Pre-defined evaluation criteria:** Scientific method fundamental; prevents p-hacking and bias (confidence 9)

**Confidence Assigned:**
- One variable at a time: 9 (fundamental controlled experiment principle)
- 50 events for learning stability: 9 (Meta official threshold)
- 7-day minimum duration: 9 (Meta official recommendation)
- 50-100+ conversions for significance: 8 (statistical best practice)
- Attribution window consistency: 8 (fair comparison requirement)
- Pre-defined evaluation criteria: 9 (scientific method)

**Notable Finding:**
- Testing methodology shows STRONGEST VERIFICATION across framework (multiple claims at confidence 9)
- Core principles (one variable, 50 events, 7 days, pre-specification) are universal standards, not Meta-specific

---

### Session 15: 2026-02-21 - File 14: 15-Scaling-Adaptation.md

**Claims Researched:**
- CPA increase with budget scaling (marginal expansion)
- Audience expansion into less aligned users
- Budget increment best practices (20-30% recommendation)
- Creative diversity requirement at scale
- Frequency pressure and fatigue acceleration

**Sources Consulted:**
- [How Much Should I Spend on Facebook Ads in 2026?](https://bir.ch/blog/how-much-should-i-spend-on-facebook-ads)
- [Meta Ads Budget Strategy for Maximum ROI](https://geistm.com/blog/meta-ads-budget-strategy-scale-smart)
- [How to Scale Meta Ad Budgets Without Losing ROAS](https://www.adamigo.ai/blog/how-to-scale-meta-ad-budgets-without-losing-roas)
- [Creative Scaling: The Ultimate Guide for Meta Ads in 2026](https://www.admetrics.io/en/post/creative-scaling-the-ultimate-guide)
- [Maximize Meta Ad Performance with Creative Diversity](https://www.reshiftmedia.com/meta-advertising-creative-diversity/)
- [How to Beat Facebook Ad Fatigue](https://bir.ch/blog/facebook-ad-fatigue)
- [How to Scale Facebook Ads Profitably](https://www.adstellar.ai/blog/how-to-scale-facebook-ads-profitably)

**Key Findings:**
- **CPA rises naturally at scale:** 20-30% budget increases can raise CPA by 25-40%; audience saturation drives CPA up 20-60% (confidence 8)
- **20-30% budget increment best practice:** Meta historical guidance max 30%; current consensus 20-30% every 48-72 hours (confidence 9)
- **Creative diversity critical:** High-performing accounts maintain 8-12 active variations; "creative is the new targeting" (confidence 8)
- **Frequency accelerates fatigue:** Single creative fatigues in 3-4 weeks; frequency 3.0+ indicates fatigue; refresh every 10-14 days at scale (confidence 8)
- **Less aligned users at scale:** Larger lookalikes (3%) have weaker similarities; documented lower conversion rates (confidence 7)
- **50+ events prerequisite:** Meta requires 50+ optimization events before scaling (confidence 9)

**Confidence Assigned:**
- CPA rises with scale naturally: 8 (well-documented scaling economics)
- 20-30% budget increment: 9 (Meta historical + strong industry consensus)
- Portfolio diversity critical: 8 (Meta Andromeda behavior confirmed)
- Frequency pressure accelerates fatigue: 8 (documented timeline)
- Scaling into less aligned users: 7 (lookalike behavior documented)

**Notable Findings:**
- 2025-2026 data confirms CPA rising trend: Facebook's average cost per lead climbed 21% YoY in 2025
- Meta's shift to "creative is the new targeting" strongly documented
- Scaling economics (marginal expansion, audience saturation) well-verified across multiple sources
- Budget increment recommendation has Meta historical precedent plus current practitioner consensus

**Phase 3 Complete:** All 5 Creative Engineering files (Files 10-14) verified
**Overall Progress:** 14/32 files (43.75%)

---

### Session 16: 2026-02-21 - File 15: 16-Campaign-and-Ad-Set-Architecture.md

**Claims Researched:**
- One campaign = one learning system (consolidation principle)
- One optimization event per campaign requirement
- Fragmentation causes insufficient event density
- Budget dilution prevents learning threshold achievement
- Too many ad sets = higher CPA volatility
- Concentration vs. fragmentation dynamics
- 3-5 creatives per ad set optimal range
- Audience overlap threshold (>25% requires consolidation)

**Sources Consulted:**
- [Meta Ads 2025 Guide: Setup & Campaign Strategies](https://www.pansofic.com/blog/meta-ads-2025-setup-and-campaign-guide)
- [Meta Ads Campaign Structure Best Practices 2026](https://www.adstellar.ai/blog/meta-ads-campaign-structure-best-practices)
- [Meta Ads Strategy 2026: Why 2 Campaigns Scale Better Than 20](https://metalla.digital/meta-ads-strategy-2026-blueprint/)
- [The Best Meta Ads Account Structure In 2026](https://www.flighted.co/blog/best-meta-ads-account-structure-2026)
- [Facebook Ads Learning Phase Guide](https://bir.ch/blog/facebook-learning-phase)
- [How To Combine Facebook Ad Sets](https://meredithkallaher.com/blog/combine-facebook-ad-sets/)
- [Diagnosing Meta Ads Volatility](https://www.williamandfriends.com/blog/diagnosing-meta-ads-volatility-fix-unstable-performance)

**Key Findings:**
- **One optimization event per campaign:** Meta platform structure requirement; critical for machine learning (confidence 9)
- **Consolidation accelerates learning:** "15 ad sets at $20/day underperforms vs. 3 at $100/day"; data density mechanics confirmed (confidence 8)
- **Fragmentation causes volatility:** Insufficient event density documented; 50 events per ad set per week required (confidence 8)
- **Budget dilution prevents learning:** Underfunded ad sets struggle to generate sufficient optimization events (confidence 8)
- **3-5 creatives optimal:** Meta technical limit = 5 per ad set; industry consensus for testing (confidence 8)
- **2026 trend: "2 campaigns scale better than 20"** - Radical consolidation over fragmentation

**Confidence Assigned:**
- One optimization event per campaign: 9 (Meta platform structure)
- Consolidation accelerates learning: 8 (data density mechanics verified)
- Fragmentation causes insufficient event density: 8 (50-event threshold cross-referenced)
- Too many ad sets = volatility: 8 (fragmentation-volatility link documented)
- 3-5 creatives per ad set: 8 (Meta limit + industry consensus)
- Audience overlap >25% threshold: 7 (Meta tool + practitioner consensus)

**Notable Findings:**
- 2026 algorithmic shift toward radical consolidation documented across multiple sources
- "Why 2 campaigns scale better than 20" = industry consensus for 2026
- Campaign architecture principles STRONGLY VERIFIED by recent Meta best practices
- Fragmentation-volatility link well-documented across practitioner sources

**Phase 4 Started:** Operational Control files (Files 16-22)
**Overall Progress:** 15/32 files (46.9%)

---

### Session 17: 2026-02-21 - File 16: 17-Budget-Variance-and-Stability.md

**Claims Researched:**
- Budget as learning fuel (must buy sufficient optimization events)
- Budget scaling increments (≤ 20-30% recommendation)
- Too low budget causes sporadic events and variance
- Too high budget too quickly causes CPA spikes
- Variance sources (creative inconsistency, landing mismatch, narrow audiences)
- Learning phase discipline (avoiding edits, event changes, budget shifts)
- Turning ad sets on/off repeatedly disrupts learning
- CPA variance thresholds (< 15% healthy, 15-30% warning, > 30% problem)

**Sources Consulted:**
- [Facebook Ads Learning Phase Exit Faster 2025](https://brimaronlinemarketing.com/blog/what-is-the-facebook-ads-learning-phase-and-how-can-you-exit-it-faster/)
- [How to Scale Facebook Ads in 2026](https://crunchydigital.com.au/blog/scaling-facebook-ad-campaigns-without-killing-performance-in-2026/)
- [Facebook Ads Budget Optimization 2026](https://insights.vaizle.com/facebook-ads-guide/how-to-do-facebook-ads-budget-optimization/)
- [How Much to Spend on Facebook Ads 2026](https://bir.ch/blog/how-much-should-i-spend-on-facebook-ads)
- [How to Scale Facebook Ads Profitably](https://www.adstellar.ai/blog/how-to-scale-facebook-ads-profitably)
- [Meta Ads Audience Saturation](https://www.adamigo.ai/blog/meta-ads-audience-saturation-causes-and-fixes)
- [Facebook Ads Audience Too Narrow](https://leadenforce.com/blog/facebook-ads-audience-too-narrow-how-to-troubleshoot-a-limited-audience)
- [Inconsistent Meta Ad Results](https://www.adstellar.ai/blog/inconsistent-meta-ad-results)
- [Facebook Ads Edits that Trigger Learning Phase](https://www.jonloomer.com/facebook-ads-edits-learning-phase/)
- [Mastering Meta Ads Learning Phase](https://www.360om.agency/news-insights/mastering-meta-ads-heres-your-guide-to-the-learning-phase)

**Key Findings:**
- **20-30% budget increment limit:** Limit changes to 10-20% to maintain performance; 20-30% often triggers reset and can raise CPA 25-40% (confidence 9)
- **Meta now shows specific budget increase limits** without restarting learning - first time Meta provided specific numbers
- **Adjust budgets every 48-72 hours at most:** Delivery system needs time to stabilize (confidence 8)
- **Narrow audiences (<500k) exhaust quickly:** Optimal range 500k-5M; below 500k risks exhaustion; CTR declines beyond 3-4 exposures (confidence 8)
- **Editing ads mid-learning resets:** Significant edits reset learning phase; re-enters to recalibrate; batch edits to minimize disruption (confidence 8)
- **Turning ad sets on/off disrupts learning:** Each toggle potentially restarts learning phase (confidence 8)
- **CPA variance thresholds:** Stable CPA within 20% variance for 7 days = success indicator (file's 15% threshold slightly more conservative) (confidence 7)

**Confidence Assigned:**
- Budget increments ≤ 20-30%: 9 (Meta historical guidance + industry consensus)
- Too low budget causes variance: 8 (logical extension of 50-event requirement)
- Too high budget causes CPA spikes: 8 (25-40% increase documented)
- Adjust every 48-72 hours: 8 (industry best practice)
- Narrow audiences exhaust quickly: 8 (well-documented saturation mechanics)
- Editing ads resets learning: 8 (Meta guidance documented)
- Turning ad sets on/off disrupts: 8 (learning phase disruption behavior)
- CPA variance thresholds: 7 (practitioner standards; 20% widely used vs. file's 15%)
- One variable per iteration: 9 (A/B testing fundamental)

**Notable Findings:**
- **NEW: Meta shows specific budget increase limits** - "You can increase your budget to $179 without restarting learning"
- Budget discipline principles STRONGLY VERIFIED across 2025-2026 sources
- Learning phase disruption triggers well-documented (edits, budget changes, event changes)
- Narrow audience threshold (500k) confirmed across multiple sources
- CPA variance monitoring thresholds are practitioner best practices (not Meta official)

**Overall Progress:** 16/32 files (50%)

---

### Session 18: 2026-02-21 - File 17: 18-Attribution-and-Feedback-Timing.md

**Claims Researched:**
- Attribution window definition and mechanics
- Meta's default attribution settings (7-day click + 1-day view)
- Current attribution window options (2025-2026)
- Short windows under-counting conversions for longer consideration products
- Longer windows over-attributing (counting other touchpoints)
- Changing attribution window mid-campaign effects
- Attribution lag and feedback latency
- Early data bias toward impulsive users
- Stage-window alignment recommendations

**Sources Consulted:**
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

**Key Findings:**
- **Meta's default attribution: 7-day click + 1-day view** (confidence 9) - Meta official default setting
- **Current options:** 1-day click, 7-day click, 1-day view, 1-day engaged view; 28-day options removed post-iOS 14 (confidence 9)
- **MAJOR 2026 CHANGE:** Meta permanently removed longer view-through attribution windows from Ads Insights API (early 2026) - **biggest change to Meta ads attribution in years** (confidence 9)
- **Measurement window shrunk from 28 days to 1 day** - industry data shows some advertisers had **30-40% of conversions from 8-28 day window that no longer counts** (confidence 9)
- **Short windows under-count conversions:** Shorter windows under-report for longer consideration products; exclude conversions outside narrow timeframe (confidence 8)
- **Longer windows over-attribute:** Inflate reported conversions by casting wider net backward; false attribution credits ads with minimal influence (confidence 7)
- **Changing attribution window mid-campaign resets learning:** Restarts learning process; pre/post data not comparable (confidence 8)
- **Attribution lag concept:** Delay between ad engagement and conversion; don't judge campaigns before average lag passes (confidence 8)
- **Minimum 50 optimization events within attribution window** for learning phase completion (confidence 9)

**Confidence Assigned:**
- Attribution window definition: 9 (Meta official feature)
- Meta's default (7-day click + 1-day view): 9 (Meta official default)
- Current options: 9 (Meta official options post-iOS 14)
- 2026 window removal: 9 (documented major platform change)
- Short windows under-count: 8 (30-40% conversion loss documented)
- Longer windows over-attribute: 7 (logical consequence documented)
- Changing windows mid-campaign disrupts: 8 (learning phase reset confirmed)
- Attribution lag: 8 (industry-standard concept)
- Stage-window alignment table: 6 (framework guidance built on verified stage mechanics)

**Notable Findings:**
- **MAJOR 2026 DISCOVERY:** Meta permanently removed longer view-through attribution windows from Ads Insights API
- This is the **biggest change to Meta ads attribution in years**
- Real impact: Some advertisers had 30-40% of conversions from the 8-28 day window that no longer counts
- B2B/long sales cycles particularly affected - conversions now look artificially low
- Meta now offers "Incremental Attribution" model to isolate conversions that wouldn't have happened without the ad

**Overall Progress:** 17/32 files (53.1%)

---

### Session 19: 2026-02-22 - File 18: 19-Competitive-Density-and-Marginal-CPA.md

**Claims Researched:**
- Seasonal spikes (Q4, holidays) increasing CPA
- Competitive auction density fluctuations and effects
- Marginal CPA dynamics during scaling
- Audience alignment decrease with scale expansion
- Creative differentiation under competitive pressure
- Semantic distinctiveness in auction performance
- Quality scores providing auction advantage
- CPA rise pattern diagnostics (gradual vs spike)
- Creative fatigue causing CPA increases
- Rotation frequency for creative refresh

**Sources Consulted:**
- [Current CPM Rates 2025](https://quimbydigital.com/current-cpm/) - Q4 seasonality
- [Understanding Q4 & Q5 Advertising Trends](https://www.rightsideup.com/blog/q4-advertising-trends) - Holiday auction dynamics
- [Meta Ads Benchmarks 2026](https://www.enrichlabs.ai/blog/meta-ads-benchmarks-2025) - CPM seasonality data
- [Meta Advertising Platform Cost 2026 Guide](https://www.adstellar.ai/blog/meta-advertising-platform-cost) - Competitive pressure
- [100 Facebook Ads Statistics 2026](https://www.uproas.io/blog/facebook-ads-statistics) - Industry benchmarks
- [Meta Ads CPM Benchmarks by Country 2026](https://www.adamigo.ai/blog/meta-ads-cpm-cpc-benchmarks-by-country-2026) - Auction cost trends
- [What to Expect From Meta Ads This Holiday Season](https://www.eyefulmedia.com/blog/what-to-expect-from-your-meta-ad-campaigns-this-holiday-season) - Q4 planning
- [Meta Advertising Trends Q1 2025](https://geistm.com/blog/meta-rate-trends-q1-2025) - Competitive dynamics
- [Why Meta Ads Are More Expensive in 2026](https://coinis.com/blog/why-meta-ads-are-more-expensive-in-2026) - Auction inflation
- [Meta Ads Bidding 2026: Maximize ROAS](https://weboin.com/meta-ads-bidding-strategy-2026/) - Competitive auction mechanics
- [Facebook Ads Scaling Automation 2026](https://www.adstellar.ai/blog/facebook-ads-scaling-automation) - Marginal CPA scaling
- [How to Scale Facebook Ads 2026](https://crunchydigital.com.au/blog/scaling-facebook-ad-campaigns-without-killing-performance-in-2026/) - Budget scaling CPA effects
- [Creative Scaling: Ultimate Guide 2026](https://www.admetrics.io/en/post/creative-scaling-the-ultimate-guide) - Audience expansion
- [How to Scale Meta Ads Safely](https://www.expansedigital.co/post/how-to-scale-meta-ads-safely-the-complete-guide-to-growing-your-budget-without-killing-your-cpa) - CPA management
- [How Much Should I Spend on Facebook Ads 2026](https://bir.ch/blog/how-much-should-i-spend-on-facebook-ads) - Scaling best practices
- [Facebook Ad Algorithm Changes 2026](https://www.socialmediaexaminer.com/facebook-ad-algorithm-changes-for-2026-what-marketers-need-to-know/) - Andromeda creative differentiation
- [Facebook Ads Updates 2026: AI & Algorithm Guide](https://nxtincome.com/facebook-meta-ads-updates-for-2026-guide) - Algorithm shifts
- [Maximize Meta Ad Performance with Creative Diversity](https://www.reshiftmedia.com/meta-advertising-creative-diversity/) - Semantic distinctiveness
- [Meta's Andromeda Update](https://themtmagency.com/blog/meta-andromeda-october-2025-update-why-creative-diversity-now-defines-ad-performance) - Creative similarity penalties
- [How to Master Meta Ads Performance Scoring 2025](https://madgicx.com/blog/meta-ads-performance-scoring) - Quality rankings
- [Meta Ads Relevance Score](https://2x.agency/glossary/meta-ad-relevance-score) - Quality diagnostics
- [How to Reduce Facebook Ads CPA 2026](https://admanage.ai/blog/how-to-reduce-facebook-ads-cpa) - CPA spike diagnosis
- [Meta Advertising Learning Phase Issues 2026](https://www.adstellar.ai/blog/meta-advertising-learning-phase-issues) - Learning resets
- [Why Is Your Facebook CPA So High](https://madgicx.com/blog/cpa-facebook) - CPA troubleshooting
- [How to Avoid Creative Ad Fatigue](https://motionapp.com/blog/ad-fatigue) - Fatigue management
- [Performance Marketer's Guide to Ad Fatigue 2026](https://www.youngurbanproject.com/the-performance-marketers-guide-to-ad-fatigue/) - Rotation strategy
- [7 Clear Signs to Refresh Facebook Creative](https://madgicx.com/blog/facebook-creative-refresh) - Fatigue indicators
- [Meta Ads Optimization 2025](https://bir.ch/blog/meta-ads-optimization) - Comprehensive optimization

**Key Findings:**
- **Q4 seasonal spikes:** CPMs spike 60-66% on average; Black Friday/Cyber Monday up to 138% higher than annual averages (confidence 9)
- **Nov 19-25 window:** ~13% cheaper CPMs than Black Friday while consumer spending active
- **2026 auction inflation:** CPC rising from $4.10 (2025) to ~$4.40 (2026); more advertisers competing with AI tools
- **Marginal CPA scaling:** 20-30% budget increases cause 25-40% CPA rise; audience saturation drives 20-60% increase (confidence 8)
- **Audience expansion:** Larger lookalikes (3%) have weaker similarities; documented lower conversion rates (confidence 7)
- **Creative differentiation critical:** Meta Andromeda Creative Similarity Score (official metric); distinct creative rewarded, repetitive ads penalized with higher CPMs (confidence 8)
- **Quality scores advantage:** Quality Ranking affects auction; high-quality $8 ad beats poor $12 ad; 30-50% cost reduction possible (confidence 8)
- **CPA spike patterns:**
  - 1-3 days after budget increase = too aggressive (>20-30% triggers learning reset)
  - 7-14 days gradual during scaling = normal expansion physics
  - Gradual without scaling = creative fatigue + competition
- **Creative rotation frequency:** 7-10 days for high-volume campaigns; frequency under 2.5-3.0 target; fatigue kicks in ~4+ exposures (confidence 8)
- **2026 shift:** "Creative is the new targeting" - diversity prioritized over volume; 70-80% of performance from creative not spend

**Confidence Assigned:**
- Q4/holiday seasonal CPA increases: 9 (well-documented with specific percentages)
- Rising competition increases CPA: 8 (2026 auction inflation documented)
- Marginal CPA rises with scaling: 8 (scaling economics strongly verified)
- Audience alignment decreases at scale: 7 (lookalike dilution documented)
- Semantic distinctiveness auction advantage: 8 (Andromeda mechanics verified)
- Quality scores = more delivery: 8 (Ad Relevance Diagnostics confirmed)
- 7-14 day gradual rise = expansion physics: 8 (timeline aligns with learning + expansion)
- 1-3 day spike = aggressive scaling: 9 (budget discipline thresholds verified)
- Gradual rise without scaling = fatigue: 8 (fatigue-CPA link documented)
- Creative rotation 7-10 days: 8 (industry consensus)
- Differentiation through creative not bidding: 7 (Andromeda shift confirmed)

**Notable Findings:**
- **Q4 seasonality STRONGLY VERIFIED:** Specific percentages (60-66% average, up to 138% peak) documented across multiple 2026 sources
- **2026 competitive environment well-documented:** Auction inflation, AI tool adoption increasing competition
- **Marginal CPA scaling economics:** Cross-referenced with Files 15, 17 - expansion physics framework supported by strong scaling research
- **Meta Andromeda Creative Similarity Score:** Official metric providing direct evidence for semantic distinctiveness claims
- **Quality score auction mechanics:** Ad Relevance Diagnostics (Quality/Engagement/Conversion Rankings) provide measurable auction advantage
- **CPA rise diagnostic framework:** Well-supported by 2026 research; pattern recognition (gradual vs spike, with/without scaling) enables accurate diagnosis
- **Creative fatigue timeline:** 7-10 day rotation consensus; frequency 3.0+ threshold confirmed
- **"Creative is the new targeting":** Meta's 2026 algorithmic shift documented across multiple sources

**Cross-File Verification:**
- Marginal CPA scaling: Cross-referenced with File 15 (Scaling Adaptation) - expansion economics confirmed
- Budget discipline (20-30%, 48-72h): Cross-referenced with Files 15, 17 - strongly verified
- Quality scores: Cross-referenced with Files 3, 4 (Auction Mechanics, Prediction Heads) - auction advantage confirmed
- Semantic distinctiveness: Cross-referenced with File 13 (Creative Identity) - Andromeda Entity ID/Creative Similarity Score
- Creative fatigue: Will cross-reference with File 20 (next) for comprehensive fatigue mechanics

**Phase 4 Progress:** 4/7 Operational Control files verified (57%)
**Overall Progress:** 18/32 files (56.25%)

---

## Source Bibliography

### Meta Official Documentation

#### Accessed and Verified
- **Learning Phase:** https://www.facebook.com/business/help/1319768884757581 - [Date accessed]
  - Confirms: ~50 optimization events threshold
  - Confirms: Learning phase exits after consistent performance

- **Auction Mechanics:** https://www.facebook.com/business/help/430291176997542 - [Date accessed]
  - Confirms: Bid, estimated action rate, ad quality as components
  - Does not publish: Exact formula structure

- **Optimization Events:** https://www.facebook.com/business/help/283579896000936 - [Date accessed]
  - Confirms: ThruPlay, LPV, Lead, Purchase definitions
  - Lists: All available optimization events

*(Populate as research progresses)*

#### Attempted But Not Found
- Exact auction scoring formula - Meta does not publish (confirmed as proprietary)
- Specific embedding dimensions - Internal architecture not documented
- [Add other negative results]

### Academic Research

#### Meta-Authored Papers
- [Title, Conference/Journal, Year, URL] - [Date accessed]
  - Relevant findings: [summary]
  - Supports claims: [list]

#### Industry Research
- [Title, Source, Year, URL] - [Date accessed]
  - Relevant findings: [summary]
  - Supports claims: [list]

*(Populate as research progresses)*

### Industry Expert Sources

#### Practitioner Blogs & Case Studies
- Jon Loomer - [Specific article, URL, Date accessed]
  - Documented testing of: [claim]
  - Results: [findings]

- AdEspresso - [Specific study, URL, Date accessed]
  - Tested: [claim]
  - Conclusion: [findings]

*(Populate as research progresses)*

### Technical ML/AI Research

#### Embedding Systems
- [Paper title, Authors, Conference, Year]
  - Confirms: [technical mechanism]
  - Relevance: [how it applies to Meta]

#### Multi-Objective Learning
- [Paper title, Authors, Conference, Year]
  - Confirms: [technical approach]
  - Relevance: [how it applies to Meta]

#### Auction Theory
- [Paper title, Authors, Journal, Year]
  - Confirms: [theoretical principle]
  - Relevance: [how it applies to Meta]

*(Populate as research progresses)*

---

## Search Query Log

### Successful Searches

| Query | Source | Date | Results | Applied To |
|-------|--------|------|---------|-----------|
| "Meta learning phase 50 events" | Meta Help Center | 2026-02-21 | Confirmed "about 50" | File 05, 17, 21 |
| "Facebook auction bid EAR quality" | Meta Business Help | 2026-02-21 | Confirmed three components | File 04, Glossary |
| [Add queries as performed] | | | | |

### Unsuccessful Searches (Negative Results)

| Query | Sources Tried | Date | Reason for Failure | Implication |
|-------|--------------|------|-------------------|-------------|
| "Meta auction exact formula" | Meta Help, Developers, Blueprint | 2026-02-21 | Proprietary, not published | Confirms operator model status |
| "Facebook embedding dimension size" | Meta AI, Developer docs | 2026-02-21 | Internal architecture not disclosed | Cannot verify specific numbers |
| [Add failed searches] | | | | |

---

## Cross-File Claim Tracking

### Claims Appearing in Multiple Files

| Claim | Files | Primary Verification | Confidence | Notes |
|-------|-------|---------------------|------------|-------|
| Learning phase ~50 events | 05, 17, 21, Glossary | File 05 (Session X) | 9 | Meta Help Center "about 50" |
| Auction = Bid × EAR × Quality | 04, 03, Glossary | File 04 (Session X) | 6 | Components verified, structure inferred |
| 4-stage model (E→I→V→D) | 09, 08, 10, 16, multiple | File 09 (Session X) | N/A (framework) | Framework's own construct |
| Quality cannot offset bid | 04, 03, 11 | File 04 (Session X) | 7 | Meta user experience priority confirmed |

*(Populate during verification)*

---

## Recurring Themes & Patterns

### Well-Documented by Meta
- Optimization event definitions (ThruPlay, LPV, Lead, Purchase, etc.)
- Learning phase existence and approximate threshold
- Attribution window options
- Campaign objective types
- Bid strategy types

### Inferred from Behavior (Operator Models)
- Exact auction scoring formula
- Specific embedding architecture details
- Prediction head structure specifics
- Quality multiplier calculation
- Risk penalty mechanisms

### Framework Constructs (Not Meta Terms)
- PS/OF/BR/VE/EA/AL/CTA-R/SCR taxonomy
- 4-stage model (Exploration→Identification→Validation→Decision)
- S0/S1 state definitions
- Value Expression Types (INSIGHT/VALIDATION/FRAMEWORK/SYSTEM)
- Semantic Consistency Rules

### Practitioner Consensus
- Budget scaling at 20-30% increments
- CPA variance thresholds for health
- Frequency tolerance ranges
- Fatigue vs saturation diagnostic patterns
- Creative rotation protocols

---

## Questions Flagged for Future Research

### Open Questions
1. [Specific claim requiring additional research]
   - Current confidence: [score]
   - What's missing: [description]
   - Potential sources: [where to look]

2. [Another open question]

### Time-Sensitive Claims
1. [Claim that may change as Meta evolves]
   - Recommend re-verification: [frequency]
   - Last verified: [date]

---

## Meta Documentation Updates Noticed

| Date | Change Noticed | Affected Files | Action Taken |
|------|---------------|----------------|--------------|
| 2026-02-21 | [If any Meta doc changes noticed] | [Files affected] | [How verification adjusted] |

---

## Methodology Refinements

### Adjustments Made During Verification

| Date | Issue Encountered | Adjustment Made | Reason |
|------|------------------|-----------------|---------|
| 2026-02-21 | [If methodology needs tweaking] | [What changed] | [Why necessary] |

---

## Verification Statistics (Running Totals)

### By Confidence Level
- Confidence 10 (Definitively Verified): 0 claims
- Confidence 9 (Strongly Verified): 0 claims
- Confidence 8 (Well Supported): 0 claims
- Confidence 7 (Solidly Supported): 0 claims
- Confidence 6 (Moderately Supported): 0 claims
- Confidence 5 (Reasonably Inferred): 0 claims
- Confidence 4 (Weakly Supported): 0 claims
- Confidence 3 (Speculative): 0 claims
- Confidence 2 (Questionable): 0 claims
- Confidence 1 (Unverified): 0 claims
- Framework Definitions (N/A): 0 items

**Total Claims Verified: 0**

*(Update as verification progresses)*

### By Claim Type
- Type A (Factual Technical): 0 claims
- Type B (Operator Mental Models): 0 claims
- Type C (Framework Constructs): 0 claims
- Type D (Operational Best Practices): 0 claims
- Type E (Causal Assertions): 0 claims

### By Impact Level (Risk)
- CRITICAL: 0 claims
- HIGH: 0 claims
- MEDIUM: 0 claims
- LOW: 0 claims
- MINIMAL: 0 claims

### By Impact Level (Benefit)
- TRANSFORMATIVE: 0 claims
- MAJOR: 0 claims
- SUBSTANTIAL: 0 claims
- MODERATE: 0 claims
- INCREMENTAL: 0 claims

### Phase Progress
- Phase 1 (Foundation): 0/5 files complete
- Phase 2 (Strategic Framework): 0/4 files complete
- Phase 3 (Creative Engineering): 0/5 files complete
- Phase 4 (Operational Control): 0/7 files complete
- Phase 5 (Remaining): 0/11 files complete

**Overall Progress: 0/32 files verified (0%)**

---

## Notes & Observations

### Surprises & Insights
- [Document unexpected findings during verification]
- [Note patterns that emerge]

### Challenges Encountered
- [Document difficulties in verification process]
- [Note claims that were particularly hard to verify]

### Recommendations for Vault Improvement
- [Suggestions based on verification findings]
- [Areas where additional clarity would help]

---

**Last Updated:** 2026-02-21
**Current Phase:** Foundation Setup
**Next File:** Glossary-and-Acronyms.md

#verification #research-log #tracking
