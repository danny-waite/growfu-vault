# Verification Standards Reference

> Quick reference guide for maintaining consistency across all file verifications in the GrowFu v3 Specification Vault.

---

## Claim Type Classification

| Type | Name | Definition | Examples |
|------|------|------------|----------|
| **A** | Factual Technical Claims | Meta-documented facts, thresholds, API specs, system behaviors | Attribution windows (1-day, 7-day), ThruPlay definition, learning phase exists |
| **B** | Operator Mental Models | Approximations of black-box behavior, components verified but formula inferred | Auction formula structure, exact embedding dimensions |
| **C** | Framework Constructs | Vault's proprietary concepts and definitions | PS/OF/BR definitions, 4-stage model, 9 immutable variables |
| **D** | Operational Best Practices | Practitioner-derived protocols and procedures | Budget scaling 20-30%, CPA variance thresholds |
| **E** | Causal Assertions | Cause-effect claims about system behavior | Skipping stages increases CPA, quality cannot be offset by bid |

---

## Confidence Scoring Rubric (1-10)

### Score Definitions

| Score | Label | Criteria | Evidence Required |
|-------|-------|----------|-------------------|
| **10** | Definitively Verified | Meta official docs explicitly confirm | Meta Help Center, API docs, official specs |
| **9** | Strongly Verified | Meta official with minor ambiguity OR multiple authoritative sources | Meta Blueprint + Help Center, or Meta + academic + industry consensus |
| **8** | Well Supported | Meta semi-official OR industry + academic consensus | Meta blog posts, or widespread practitioner + academic validation |
| **7** | Solidly Supported | Strong practitioner consensus, behaviorally observable | Multiple documented case studies, replicated results |
| **6** | Moderately Supported | Reputable practitioners with testing, logical extension of verified principles | Jon Loomer, AdEspresso testing; reasonable inference from confirmed facts |
| **5** | Reasonably Inferred | Plausible operator model, some evidence, system-consistent | Behavioral consistency, partial supporting evidence |
| **4** | Weakly Supported | Limited evidence, anecdotal, theoretically plausible | Single practitioner report, no contradictions but minimal support |
| **3** | Speculative | Reasonable hypothesis, minimal evidence | Logical but unproven, no direct contradictions |
| **2** | Questionable | Doubtful, contradicted by some sources | Conflicting evidence, possibly outdated |
| **1** | Unverified/Incorrect | No supporting evidence, contradicted by authorities | Refuted by Meta docs or consensus |
| **N/A** | Framework Definition | Vault's own terminology, not externally verifiable | PS/OF/BR as defined by framework itself |

### Scoring Guidelines

- **Conservative bias:** When uncertain between two scores, choose the lower
- **Component verification:** For mental models, verify components separately then score structure 5-7
- **Absence of evidence:** Meta not documenting something ≠ false (many details proprietary)
- **Behavioral validation:** Observable system behavior counts as evidence even without documentation
- **Time sensitivity:** Note verification date; Meta's system evolves

---

## Impact Assessment Framework

### Risk Categories (If Assumption is Wrong)

| Level | Definition | CPA Impact | Delivery Impact | Examples |
|-------|------------|------------|-----------------|----------|
| **CRITICAL** | Campaign failure, learning never stabilizes | System failure | No delivery or severe throttling | Wrong optimization event for stage, zero signal volume |
| **HIGH** | Major performance degradation | >50% increase | Severely limited scale | Ignoring quality signals, skipping stages |
| **MEDIUM** | Moderate performance impact | 20-50% increase | Slower learning, reduced efficiency | Aggressive budget scaling, suboptimal targeting |
| **LOW** | Minor efficiency loss | <20% increase | Slightly longer optimization | Suboptimal hook timing, minor creative choices |
| **MINIMAL** | Edge optimization only | <5% impact | Negligible | Specific styling preferences, minor refinements |

### Benefit Categories (If Correctly Applied)

| Level | Definition | Efficiency Gain | Scale Impact | Examples |
|-------|------------|-----------------|--------------|----------|
| **TRANSFORMATIVE** | Fundamental viability change | 2-5x+ improvement | Unlocks impossible scale | Stage-appropriate optimization events |
| **MAJOR** | Significant competitive advantage | 50-100%+ improvement | Major scale unlocked | Semantic consistency preservation |
| **SUBSTANTIAL** | Meaningfully better outcomes | 25-50% improvement | Faster learning, better stability | Proper attribution alignment |
| **MODERATE** | Clear operational benefit | 10-25% improvement | Smoother scaling | Budget scaling discipline |
| **INCREMENTAL** | Minor optimization | 5-10% improvement | Marginal efficiency | Fatigue monitoring thresholds |

### Impact Statement Format

```
Risk: [LEVEL] | Benefit: [LEVEL]
Detail: [1-2 sentences explaining what breaks if wrong AND what improves if right]
```

**Examples:**

```
Risk: CRITICAL | Benefit: TRANSFORMATIVE
Detail: Wrong optimization event causes learning failure and wasted budget. Correct stage-event alignment enables stable learning and efficient scaling.

Risk: MEDIUM | Benefit: SUBSTANTIAL
Detail: Aggressive budget increases may cause temporary delivery instability. Gradual scaling maintains learning continuity and pacing confidence.

Risk: LOW | Benefit: MODERATE
Detail: Suboptimal hooks reduce early retention signals, slowing learning. Well-engineered hooks accelerate signal accumulation.
```

---

## Source Citation Standards

### Meta Official Documentation

**Primary Sources:**
- Meta Business Help Center: https://www.facebook.com/business/help
- Meta for Developers: https://developers.facebook.com/docs
- Meta Blueprint: https://www.facebook.com/business/learn
- Meta Business Blog: https://www.facebook.com/business/news
- Meta Ads Manager Documentation

**Citation Format:**
- "Meta Help Center (Auction Overview)" - for general help articles
- "Meta API Documentation (Optimization Events)" - for technical specs
- "Meta Blueprint (Campaign Structure)" - for educational content
- "Meta Business Blog (2025-01-15)" - for blog posts with date

### Academic Research Sources

**Primary Databases:**
- Google Scholar: https://scholar.google.com
- arXiv: https://arxiv.org (for ML/AI preprints)
- ACM Digital Library: https://dl.acm.org
- Meta AI Research: https://ai.meta.com/research

**Key Conferences:**
- KDD (Knowledge Discovery and Data Mining)
- ICML (International Conference on Machine Learning)
- RecSys (Recommender Systems)
- WWW (The Web Conference)

**Citation Format:**
- "Meta AI (2024): Multi-objective Learning in Ad Systems"
- "RecSys 2023: Auction Mechanisms for Online Advertising"
- "Academic consensus: embedding-based representations standard practice"

### Industry Expert Sources

**Reputable Practitioners:**
- Jon Loomer (documented Meta Ads testing)
- AdEspresso (case studies and experiments)
- Social Media Examiner
- Meta Marketing Partners (official partner documentation)

**Citation Format:**
- "Practitioner consensus (3+ sources): 20-30% budget scaling"
- "Jon Loomer documented testing (2024): learning phase behavior"
- "Industry consensus: avoid >30% budget increases"

### ML/AI Technical Research

**Focus Areas:**
- Embedding architectures (transformer models, representation learning)
- Multi-task learning and multi-objective optimization
- Auction theory and mechanism design
- Click-through rate prediction
- Recommendation systems

**Citation Format:**
- "ML standard practice: multi-task learning on shared embeddings"
- "Auction theory: utility maximization framework"
- "Technical ML research: prediction head architecture common"

---

## Common Meta Documentation Links

### Core System Mechanics
- **Auction:** https://www.facebook.com/business/help/430291176997542
- **Delivery System:** https://www.facebook.com/business/help/1665333080167380
- **Learning Phase:** https://www.facebook.com/business/help/1319768884757581
- **Optimization Events:** https://www.facebook.com/business/help/283579896000936

### Campaign Structure
- **Campaign Objectives:** https://www.facebook.com/business/help/1438417719786914
- **Bid Strategies:** https://www.facebook.com/business/help/1619591734742116
- **Budget Types:** https://www.facebook.com/business/help/1673188326246160

### Attribution & Measurement
- **Attribution Windows:** https://www.facebook.com/business/help/458681590974355
- **Conversion Events:** https://www.facebook.com/business/help/131378000381059
- **Meta Pixel:** https://www.facebook.com/business/help/742478679120153

### Creative & Quality
- **Ad Quality:** https://www.facebook.com/business/help/182671009134278
- **Creative Best Practices:** https://www.facebook.com/business/help/1637587253170559
- **Video Optimization:** https://www.facebook.com/business/help/1524056094370723

*(Note: URLs checked as of February 2026; Meta may reorganize documentation)*

---

## Multi-File Claim Tracking

Track claims that appear in multiple files to ensure consistent scoring:

| Claim | Primary File | Confidence | Also Appears In | Notes |
|-------|--------------|------------|-----------------|-------|
| Learning phase ~50 events | 05-Delivery-and-Budget-Dynamics.md | 9 | 17-Budget-Variance-and-Stability.md, 21-Governance.md | Meta Help Center confirms "about 50" |
| Auction includes Bid × EAR | 04-Auction-Mechanics.md | 8 | Glossary-and-Acronyms.md | Components verified, formula structure inferred |
| 4-stage model (E→I→V→D) | 09-Cognitive-Stages.md | N/A (framework) / 6 (behavior) | Multiple | Framework construct; underlying behavior moderately supported |
| Quality cannot be offset by bid | 04-Auction-Mechanics.md, 03-Prediction-Heads.md | 7 | 11-Multimodal-Creative.md | Supported by Meta's user experience priority statements |

*(Populate during verification process)*

---

## Evidence Description Templates

### For High Confidence (8-10)
- "Meta Help Center explicitly confirms [specific claim]"
- "Meta API documentation specifies [technical detail]"
- "Meta Blueprint + Help Center both document [behavior]"
- "Meta AI research paper (2024) describes [mechanism]"

### For Moderate Confidence (5-7)
- "Operator mental model; components (Bid, EAR, Quality) verified via Meta docs"
- "Practitioner consensus (Jon Loomer, AdEspresso, 3+ sources); empirically validated"
- "Behavioral observation consistent across multiple documented tests"
- "Logical extension of verified principle [X]; supported by industry experience"

### For Low Confidence (3-4)
- "Anecdotal practitioner reports; limited direct evidence"
- "Reasonable hypothesis; no contradictions but minimal support"
- "Speculative threshold; directional guidance without confirmed number"

### For Framework Constructs (N/A)
- "Framework definition; PS/OF/BR are vault's proprietary constructs"
- "Framework's own taxonomy; not Meta terminology"
- "Vault's structural rule; not Meta's documented requirement"

---

## Quality Assurance Checklist

### Before Marking File Complete
- [ ] All formulas verified or noted as mental models
- [ ] All numeric thresholds researched
- [ ] All "rule" callouts assessed
- [ ] All optimization events checked against Meta docs
- [ ] Framework constructs distinguished from Meta claims
- [ ] Cross-file references noted
- [ ] Evidence sources specific and clear
- [ ] Impact shows BOTH risk and benefit
- [ ] Table markdown renders correctly
- [ ] Confidence scores follow rubric
- [ ] Verification date added
- [ ] #verification-complete tag added

### Consistency Checks (Periodic)
- [ ] Similar claims scored consistently
- [ ] Evidence descriptions use standard formats
- [ ] Impact levels justified
- [ ] Cross-file claims reference each other
- [ ] No score inflation over time

---

## Special Cases Quick Reference

### Operator Mental Models
- Verify each component separately
- Score structure 5-7 if components verified
- Note: "Explicitly marked as operator approximation"
- Example: Auction formula (Bid ✓, EAR ✓, Quality ✓ → formula structure = 6)

### Specific Numbers
- Search Meta docs for exact number
- Check practitioner consensus if not documented
- Score: 9-10 Meta, 6-7 practitioner consensus, 3-5 anecdotal
- Note ranges if sources differ
- Example: "~50 events" (Meta says "about 50" = confidence 9)

### Framework Applied to Meta
- Framework rule itself = N/A
- Underlying Meta behavior = scored normally
- May need two rows
- Example: "One campaign = one stage" (framework) vs "Changing optimization harms learning" (Meta behavior = confidence 7)

### Causal Claims
- Verify mechanism exists
- Check for consequence evidence
- Assess logic chain validity
- Score: 5-7 if mechanism confirmed, 3-5 if plausible only
- Impact critical here
- Example: "Skipping stages increases CPA" (mechanism: signal volume matters ✓, consequence: documented ✓ = confidence 6-7)

---

## Version History

- **v1.0** - 2026-02-21 - Initial standards document created
- *(Update as verification progresses and edge cases emerge)*

---

#verification #standards #reference
