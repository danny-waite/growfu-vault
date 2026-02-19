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

#operational-control #attribution #feedback-timing #windows
