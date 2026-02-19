# 11 — Multimodal Creative Design

> **Part of:** [[_MOC-Creative-Engineering|Part III — Creative Engineering]] | [[../00-INDEX/HOME|HOME]]
> **See also:** [[../05-REFERENCE/U-A-C-Triad-Reference|U–A–C Triad]], [[12-Micro-Signal-Optimization|Micro-Signal Optimization]], [[../02-STRUCTURAL-STRATEGY/07-Immutable-Global-Variables|Immutable Variables]], [[../05-REFERENCE/Glossary-and-Acronyms|Glossary]]

---

## Creative Is Not Message. It Is Representation.

Your ad is not a message you send to users. It is a **multimodal object** the system encodes into a latent representation (the A embedding in the [[../05-REFERENCE/U-A-C-Triad-Reference|U-A-C triad]]).

Every element of your creative contributes to that representation — whether you intend it to or not.

---

## 11.1 Content Signals

These are the **meaning-bearing** elements of your creative. They directly shape the Ad Embedding (A).

### Text
- Semantic clarity — does the meaning decode immediately?
- Claim strength — how strong/aggressive is the promise?
- Urgency — how time-pressured is the message?
- Alignment with landing — does the landing page fulfill what the ad implies?

### Image / Video
- **Faces** — human faces increase attention and affect trust signals
- **Overlay text** — carries meaning even when audio is off
- **Production style** — UGC vs. polished signals different brand identities
- **Visual rhythm** — pacing, cuts, and transitions affect watch time
- **First-frame anchor** — the image or frame that registers before any motion plays

### Audio
- **Tone** — authoritative vs. conversational vs. urgent
- **Authority** — speaker credibility signals
- **Emotional cadence** — pacing of delivery affects emotional processing

> [!rule] Each Content Element Influences the Ad Embedding (A)
> Changing any of these meaningfully can shift the ad's latent identity — which means you are potentially asking the system to learn a new entity.

---

## 11.2 Structural Signals

These are **metadata-level** features that the system uses as context embeddings. You control them through campaign structure, not creative content.

- Placement
- Format (single image, video, carousel, story, etc.)
- Device
- Optimization objective
- Landing type (instant form, website, etc.)
- Category
- Country / regulation

> **Example:** Format × Device cross-feature changes behavior probability. A video ad on Reels on mobile performs differently than the same video on desktop News Feed — not because of the creative, but because the context embedding (C) is different.

> [!rule] Treat Placements as Context Variation, Not Message Variation
> Do not change your message to match a placement. Change your format. The core message (governed by [[../02-STRUCTURAL-STRATEGY/07-Immutable-Global-Variables|VE, EA, SCR]]) must remain consistent.

---

## 11.3 Performance Priors

Historical aggregated performance influences how the system initializes predictions for new creatives.

| History Type | Effect |
|---|---|
| CTR history | High = positive prior; too high + low CVR = clickbait flag |
| CVR history | Stable high = strong prior for conversion |
| Negative feedback history | High = increased resistance on new ads |
| Fatigue history | Detected = faster decay prediction on similar formats |

These are **priors, not destiny.** But poor history increases initial resistance. Build quality from the start.

---

## 11.4 Creative Identity

Creative identity is **latent.** It is not what you name your ad or what you intend it to be. It is how the system categorizes it based on signals and user reactions.

Categories the system may assign:

- "Educational"
- "Clickbait"
- "Luxury / Premium"
- "Aggressive"
- "Low trust"

**Identity emerges from:** structure + signals + user reactions.

> [!rule] Maintain Creative Identity Consistency Per Campaign
> If your portfolio mixes "educational" and "aggressive" identity signals within the same campaign, you create ambiguity in the system's learning. All creatives in one campaign should build toward the same latent identity.

---

## Creative Signal Checklist

Before launching any creative, verify:

- [ ] Text semantic clarity: does meaning decode in < 3 seconds?
- [ ] Claim strength: within [[../02-STRUCTURAL-STRATEGY/07-Immutable-Global-Variables|CTA-R]] and [[../02-STRUCTURAL-STRATEGY/07-Immutable-Global-Variables|SCR]] boundaries?
- [ ] First frame: does it anchor to the right user state?
- [ ] Production style: consistent with portfolio identity?
- [ ] Audio (if present): tone matches [[../02-STRUCTURAL-STRATEGY/07-Immutable-Global-Variables|EA]]?
- [ ] Format: appropriate for declared placements?
- [ ] Landing alignment: does the landing fulfill exactly what the ad implies?

---

#creative-engineering #multimodal #creative-design #signals
