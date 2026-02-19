# 14 — Structured Testing Framework

> **Part of:** [[_MOC-Creative-Engineering|Part III — Creative Engineering]] | [[../00-INDEX/HOME|HOME]]
> **See also:** [[12-Micro-Signal-Optimization|Micro-Signal Optimization]], [[../02-STRUCTURAL-STRATEGY/09-Cognitive-Stages-and-Optimization-Contracts|Cognitive Stages]], [[../04-OPERATIONAL-CONTROL/18-Attribution-and-Feedback-Timing|Attribution Timing]], [[../04-OPERATIONAL-CONTROL/22-Master-Checklists-and-Execution-Templates|Master Checklists]], [[../05-REFERENCE/Glossary-and-Acronyms|Glossary]]

---

## Never Vary Randomly

Random variation produces unattributable results. If you change multiple elements simultaneously, you cannot know what caused performance change — and you have potentially destroyed learning by introducing semantic ambiguity.

> [!rule] One Axis at a Time
> Vary one dimension per test. This is the only way to attribute performance differences to specific creative decisions.

---

## The 5-Axis Variation Matrix

| Axis | What It Tests | Examples |
|---|---|---|
| **1. Hook type** | How you open | Problem statement / Question / Statistic / Story opening / Social proof opening |
| **2. Proof mechanism** | How you substantiate claims | Case study / Expert authority / User testimonial / Before-after / Data/numbers |
| **3. Emotional framing** | The emotional journey | Curiosity → Clarity / Fear → Relief / Skepticism → Conviction / Overwhelm → Control |
| **4. Visual pacing** | Rhythm and editing | Fast cuts / Slow reveals / Text-only / Talking head / B-roll narrative |
| **5. CTA framing** | How the action is requested | Soft curiosity / Direct command / Loss framing / Gain framing / Social proof CTA |

---

## How to Run a Structured Test

### Step 1: Lock all non-test axes
Before testing Axis 1 (Hook), ensure Axes 2-5 are identical across test variants. If they are not, you are not testing a hook — you are introducing noise.

### Step 2: Define the evaluation criteria before launch

| Criteria | What to Specify |
|---|---|
| Primary KPI | The single metric that decides the winner |
| Secondary KPIs | Diagnostic metrics (e.g., hold rate, CVR) |
| Minimum impressions | Before drawing conclusions |
| Minimum events | Volume threshold for statistical confidence |
| Evaluation window | Days or days + min events, whichever comes later |

### Step 3: Do not evaluate early
Evaluating during the learning phase produces misleading results. See [[../01-SYSTEM-PHYSICS/05-Delivery-and-Budget-Dynamics|Learning Phase Constraint]].

### Step 4: Attribute accurately
Apply consistent [[../04-OPERATIONAL-CONTROL/18-Attribution-and-Feedback-Timing|attribution windows]] across all test variants. Mixing window types invalidates comparison.

---

## Test Sequencing Across Stages

Testing priorities differ by stage because the primary optimization metric differs:

| Stage | Primary Test Metric | Secondary |
|---|---|---|
| Exploration | Hold rate, Completion % | Profile clicks |
| Identification | [[../05-REFERENCE/Glossary-and-Acronyms|LPV]] rate, Scroll depth | Engagement |
| Validation | Lead rate, Lead quality proxy | LPV rate |
| Decision | Purchase rate / [[../05-REFERENCE/Glossary-and-Acronyms|CPA]] | Checkout initiation |

> A hook test at Exploration stage is evaluated on micro-signals (hold rate, completion).
> The same hook test at Decision stage is evaluated on conversion rate.

---

## What Good Test Results Look Like

| Scenario | Interpretation | Action |
|---|---|---|
| Variant A: higher hold rate AND higher CVR | Clear winner | Promote to control candidate |
| Variant A: higher CTR, lower CVR | Clickbait signal | Do not promote. Investigate hook-landing mismatch. |
| No significant difference | Insufficient signal or axes are not meaningful differentiators | Extend window or redesign test |
| Both underperform control | Current control is the right benchmark | Retire test variants, keep control |

---

#creative-engineering #testing #variation-matrix #structured-testing
