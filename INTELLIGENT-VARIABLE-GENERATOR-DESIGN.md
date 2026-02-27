# Intelligent Variable Generator (IVG) System Design

## Executive Summary

The **Intelligent Variable Generator (IVG)** is a sophisticated AI-powered system that transforms minimal user inputs (company description, brand info, product details) into complete, framework-compliant definitions of the 9 Immutable Global Variables required for GrowFu v3 campaigns.

The system combines deep automated research, multi-LLM analysis, strict validation logic, and interactive refinement to produce expert-quality variable definitions that would normally require deep GrowFu expertise and 6-8 hours of strategic work.

**Time Reduction**: 6-8 hours manual → 45-60 minutes with IVG (85%+ time savings)

---

## System Architecture Overview

### Core Principles

1. **Depth over speed**: Prioritize quality of reasoning over quick generation
2. **Evidence-based**: Every variable backed by research, not assumptions
3. **Framework compliance**: Hard constraints on variable structure and requirements
4. **Iterative refinement**: Generate, validate, refine cycle before user sees outputs
5. **Explainable**: Every decision comes with reasoning and evidence trail

### System Components

```
┌─────────────────────────────────────────────────────────────┐
│                    USER INPUT INTERFACE                      │
│  (Minimal: company, brand, product, audience, materials)     │
└───────────────────┬─────────────────────────────────────────┘
                    │
                    ▼
┌─────────────────────────────────────────────────────────────┐
│              RESEARCH ORCHESTRATOR                           │
│  Coordinates parallel research across multiple sources       │
└───────┬─────────────┬──────────────┬───────────────┬────────┘
        │             │              │               │
        ▼             ▼              ▼               ▼
┌─────────────┐ ┌──────────┐ ┌───────────┐ ┌────────────────┐
│  Company    │ │ Industry │ │Competitor │ │   Audience     │
│  Research   │ │ Research │ │ Research  │ │   Research     │
│   Agent     │ │  Agent   │ │   Agent   │ │     Agent      │
└─────┬───────┘ └────┬─────┘ └─────┬─────┘ └────────┬───────┘
      │              │              │                 │
      └──────────────┴──────────────┴─────────────────┘
                            │
                            ▼
┌─────────────────────────────────────────────────────────────┐
│              KNOWLEDGE SYNTHESIS ENGINE                      │
│  Consolidates research into structured intelligence base     │
└───────────────────┬─────────────────────────────────────────┘
                    │
                    ▼
┌─────────────────────────────────────────────────────────────┐
│              VARIABLE GENERATION ENGINE                      │
│     9 Specialized Analyzers (one per variable)              │
│  Each uses LLM + framework rules + research context         │
└───────┬─────────────┬──────────────┬───────────────┬────────┘
        │             │              │               │
        ▼             ▼              ▼               ▼
   ┌────────┐   ┌────────┐   ┌────────┐   ┌────────────┐
   │PS Gen  │   │OF Gen  │   │BR Gen  │   │ CS/VE/EA   │
   │        │   │        │   │        │   │  Gen       │
   └────┬───┘   └───┬────┘   └───┬────┘   └──────┬─────┘
        │           │            │                │
        └───────────┴────────────┴────────────────┘
                            │
                            ▼
┌─────────────────────────────────────────────────────────────┐
│              VALIDATION & CONSISTENCY ENGINE                 │
│  Hard constraints + cross-variable coherence checks          │
└───────────────────┬─────────────────────────────────────────┘
                    │
                    ▼
┌─────────────────────────────────────────────────────────────┐
│              ITERATIVE REFINEMENT LOOP                       │
│  Auto-fix violations, regenerate with constraints            │
└───────────────────┬─────────────────────────────────────────┘
                    │
                    ▼
┌─────────────────────────────────────────────────────────────┐
│              USER INTERACTION INTERFACE                      │
│  Present options, explain reasoning, gather feedback         │
└───────────────────┬─────────────────────────────────────────┘
                    │
                    ▼
┌─────────────────────────────────────────────────────────────┐
│              FINAL OUTPUT GENERATOR                          │
│  Campaign Definition Sheet + Evidence Pack                   │
└─────────────────────────────────────────────────────────────┘
```

---

## Phase 1: Deep Research Strategy

### 1.1 Research Orchestrator

**Technology**: Python orchestration layer with async/await for parallel research

**Responsibilities**:
- Coordinate 4 parallel research agents
- Manage research depth/breadth tradeoffs
- Consolidate findings into structured knowledge graph
- Track evidence provenance for all claims

---

### 1.2 Company Research Agent

**Data Sources**:

1. **Website Deep Crawl**
   - Technology: Firecrawl, Apify, or custom Playwright crawler
   - Extract: Homepage, About, Product pages, Blog, Case studies, Testimonials
   - Parse: Value propositions, problem statements, solution mechanisms, customer stories

2. **Social Media Analysis**
   - Technology: Official APIs (Twitter/X, LinkedIn, Facebook Graph API)
   - Extract: Recent posts, engagement patterns, messaging themes, visual identity
   - Analyze: Tone, emotional positioning, brand personality

3. **Existing Marketing Materials**
   - Technology: Multi-modal LLM (GPT-4o, Claude 3.5 Sonnet)
   - Analyze: Current ads if provided, brand guidelines, positioning docs
   - Extract: Current PS/OF if implicit, emotional axes, semantic patterns

4. **Product/Service Analysis**
   - Technology: Claude Opus 4.6 for deep reasoning
   - Map: Features → Benefits → Behavioral outcomes
   - Identify: What user behavior actually changes (critical for OF)

**Output**: Company Intelligence Profile
```json
{
  "value_propositions": ["..."],
  "problem_statements_found": ["..."],
  "solution_mechanisms": ["..."],
  "customer_outcomes": ["observable behavior changes"],
  "brand_voice": {
    "tone": "authoritative|conversational|empowering",
    "emotional_positioning": "from X to Y",
    "semantic_patterns": ["repeated phrases", "core language"]
  },
  "product_mechanics": {
    "features": ["..."],
    "behavioral_outcomes": ["what users DO differently"]
  },
  "evidence": [{"claim": "...", "source": "url", "quote": "..."}]
}
```

---

### 1.3 Industry Research Agent

**Data Sources**:

1. **Industry Intelligence**
   - Technology: Perplexity AI, Exa.ai, or custom web research
   - Extract: Market size, growth trends, competitive dynamics
   - Identify: Common pain points, typical customer journeys

2. **Problem Space Research**
   - Technology: Semantic Scholar API for academic papers, industry reports
   - Research: Documented behavioral/cognitive errors in this domain
   - Extract: Observable symptoms, state transitions

3. **Best Practices & Case Studies**
   - Successful campaigns in this vertical
   - Common messaging patterns that work
   - Typical cognitive stages and conversion paths

**Output**: Industry Intelligence Profile

---

### 1.4 Competitor Research Agent

**Data Sources**:

1. **Meta Ad Library API** (official Meta Ad Library)
   - Current active ads from competitors
   - Historical ad patterns
   - Creative approaches, messaging, hooks, CTAs

2. **Competitor Website Analysis**
   - Positioning strategies
   - Problem framing approaches
   - Outcome promises

3. **SimilarWeb / Semrush APIs** (if available)
   - Traffic patterns, audience overlap
   - Top performing content

**Output**: Competitive Intelligence Profile
```json
{
  "competitors": [
    {
      "name": "...",
      "positioning": "...",
      "problem_framing": "...",
      "emotional_axis_detected": "from X to Y",
      "cta_intensity_range": "passive|moderate|aggressive",
      "brand_role_inference": "above|beside|behind",
      "ad_examples": [{"text": "...", "image_url": "...", "analysis": "..."}]
    }
  ],
  "market_gaps": ["opportunities not addressed by competitors"],
  "saturation_analysis": "which approaches are overused"
}
```

---

### 1.5 Audience Research Agent

**Data Sources**:

1. **Behavioral Signal Research**
   - Reddit API: Search for discussions of the problem space
   - Quora: Common questions and frustrations
   - Review sites: Behavioral patterns in reviews

2. **Meta Audience Insights** (if API access available)
   - Demographics interested in this category
   - Interest overlaps
   - Typical engagement patterns

3. **User Journey Mapping**
   - Typical paths from problem awareness → purchase
   - Observable signals at each stage
   - Common rejection/avoidance behaviors

**Output**: Audience Intelligence Profile
```json
{
  "observable_s0_signals": {
    "what_they_consume": ["content types", "formats"],
    "what_they_ignore": ["scroll patterns", "cta_avoidance"],
    "micro_actions": ["typical early signals"],
    "avoidance_behaviors": ["what they don't do"]
  },
  "cognitive_journey": {
    "exploration_signals": ["..."],
    "identification_signals": ["..."],
    "validation_signals": ["..."],
    "decision_signals": ["..."]
  },
  "problem_language": ["how they describe the problem in their own words"],
  "outcome_desires": ["what they say they want to do differently"]
}
```

---

### 1.6 Knowledge Synthesis Engine

**Technology**: Claude Opus 4.6 (best reasoning model)

**Process**:
1. Ingest all 4 research agent outputs
2. Cross-reference and validate findings
3. Identify contradictions and resolve with evidence weight
4. Build unified knowledge graph
5. Tag all claims with evidence provenance

**Output**: Synthesized Intelligence Base with full evidence trails, conflict resolution notes, confidence scores, and gaps identified

---

## Phase 2: Variable Generation Engine

### Architecture: 9 Specialized Generator Modules

Each variable has a dedicated generator following this pattern:
```
Input: Synthesized Intelligence Base + Framework Rules + Variable-Specific Constraints
Process: Multi-step reasoning with explicit constraint checking
Output: Variable definition + reasoning + evidence + alternatives
```

---

### 2.1 PS (Problem Space) Generator

**Framework Requirements** (from [File 7](./META-ADS-VAULT/02-STRUCTURAL-STRATEGY/07-Immutable-Global-Variables.md)):
- Must be a recurring human error (cognitive, emotional, or behavioral)
- Must be OBSERVABLE, not psychological
- Must identify structural cause (not blame user)
- Must be expressible as: 1 sentence + 3 observable symptoms (behaviors)

**LLM Strategy**:
- **Model**: Claude Opus 4.6 (best reasoning)
- **Approach**: Multi-shot prompting with framework requirements embedded

**Prompt Template**:
```xml
<context>
You are a GrowFu strategist expert defining Problem Space (PS) for a campaign.

FRAMEWORK REQUIREMENTS:
- PS is a RECURRING HUMAN ERROR (cognitive, emotional, or behavioral)
- It must be OBSERVABLE behavior, not internal psychology
- Identify the STRUCTURAL CAUSE (do not blame the user)
- Express as: 1 sentence definition + 3 observable symptoms

HARD CONSTRAINTS:
- Symptoms must be BEHAVIORS (things people DO), not feelings
- Must be RECURRING pattern, not one-time mistake
- Must be addressable by the product/service offered

RESEARCH INTELLIGENCE:
{synthesized_intelligence_base}

TASK:
Generate 3 alternative PS definitions for {company_name} offering {product}.
For each:
1. One-sentence PS definition identifying the structural cause
2. Three observable behavioral symptoms
3. Evidence from research supporting each symptom
4. Explanation of why this is a structural cause, not user blame
5. Confidence score (1-10) based on evidence quality
</context>
```

**Validation Logic** (hard-coded Python):
```python
def validate_ps(ps_definition):
    errors = []

    # Check: Is it behavioral/observable?
    if contains_psychological_terms(ps_definition['sentence']):
        errors.append("PS uses psychological terms instead of observable behavior")

    # Check: Are symptoms behavioral?
    for symptom in ps_definition['symptoms']:
        if not is_observable_behavior(symptom):
            errors.append(f"Symptom not observable: {symptom}")

    # Check: Does it have structural cause framing?
    if blames_user(ps_definition['sentence']):
        errors.append("PS blames user instead of identifying structural cause")

    # Check: Is it addressable by the product?
    if not product_can_address(ps_definition, product_info):
        errors.append("PS not addressable by offered product/service")

    return errors
```

**Output**: 3 ranked PS options with evidence and reasoning

---

### 2.2 OF (Outcome Function) Generator

**Framework Requirements**:
- NOT aspiration - observable state transition
- Describe what user DOES differently after intervention
- Express as change in behavior, criteria, or action
- Must be measurable/observable

**Critical Example**:
- ❌ NOT: "users will feel confident"
- ✅ YES: "users will evaluate options using a defined framework rather than guessing"

**LLM Prompt Template**:
```xml
<context>
You are defining Outcome Function (OF) - the observable behavior change.

FRAMEWORK REQUIREMENTS:
- Observable state transition (S0 → S1)
- What the user DOES differently (not feels differently)
- Behavioral change, not aspiration
- Must be measurable in principle

HARD CONSTRAINTS:
- No feelings/emotions as the OF (those are on the EA axis)
- Must be an ACTION or BEHAVIOR CHANGE
- Must be attributable to the intervention
- Must decompose across stages

RESEARCH INTELLIGENCE:
{synthesized_intelligence_base}

PS DEFINITION (already decided):
{ps_definition}

TASK:
Generate 3 alternative OF definitions that:
1. Describe the behavioral state transition (what they DO differently)
2. Are observable/measurable
3. Directly address the PS structural cause
4. Decompose across cognitive stages appropriately
</context>
```

**Validation Logic**:
```python
def validate_of(of_definition):
    errors = []

    if contains_emotional_language(of_definition):
        errors.append("OF describes feelings, not behaviors")

    if not is_measurable(of_definition):
        errors.append("OF not observable/measurable")

    if not addresses_problem(of_definition, ps_definition):
        errors.append("OF doesn't address the PS structural cause")

    if not can_decompose_to_stages(of_definition):
        errors.append("OF can't decompose across cognitive stages")

    return errors
```

---

### 2.3 BR (Brand Role) Generator

**Framework Requirements**:
- **Direction**: Unidirectional / Bidirectional
- **Intensity**: Low / Medium / High
- **Position**: Above (authority) / Beside (peer/guide) / Behind (enabler)

**Implications**:
- Position "Above" (authority) → cannot use peer tone
- Position "Beside" (peer) → cannot use authoritative tone
- Position "Behind" (enabler) → user is hero, brand is platform

**LLM Prompt Template**:
```xml
<context>
You are defining Brand Role (BR) - the functional brand-user relationship.

FRAMEWORK:
BR has 3 dimensions:
1. DIRECTION: Unidirectional (brand tells user) vs Bidirectional (conversation/co-creation)
2. INTENSITY: Low (light touch) / Medium (engaged) / High (deep relationship)
3. POSITION:
   - Above: Authority, expert, teacher (cannot use peer tone)
   - Beside: Peer, guide, partner (cannot use authoritative tone)
   - Behind: Enabler, platform, tool (user is hero)

BR governs:
- What proof is required
- How strong CTA can be
- What tone is credible

RESEARCH INTELLIGENCE:
{synthesized_intelligence_base}

Analyze:
- Current brand voice and positioning
- Competitor positioning
- Product type (SaaS platform = behind, Consulting = above, Course = beside)

TASK:
Determine the appropriate BR with:
1. Classification on each dimension with reasoning
2. Implications for proof requirements
3. Implications for CTA intensity
4. Implications for tone/voice
5. Evidence from research
</context>
```

---

### 2.4 CS (Cognitive Stage) Generator

**Framework Requirements**:
- Choose ONE stage: Exploration → Identification → Validation → Decision
- Stage determines: objective, optimization event, CTA range, targeting
- Must match where users actually are (not aspiration)
- Must ensure sufficient signal volume (~50 events/week)

**Stage Mapping**:
- **Exploration**: Awareness | Event: ThruPlay/VV | CTA: Passive
- **Identification**: Recognition | Event: LPV | CTA: Informational
- **Validation**: Trust | Event: Lead | CTA: Commitment signal
- **Decision**: Action | Event: Purchase/Value | CTA: Buy/Join

**Critical Rule**: Never skip stages. If users can't consistently perform an action, don't optimize for it.

**Validation Logic**:
```python
def validate_cs(cs_definition, budget_estimate):
    errors = []
    warnings = []

    # Can achieve ~50 events/week with budget?
    estimated_events = estimate_weekly_events(
        cs_definition['stage'],
        budget_estimate,
        industry
    )
    if estimated_events < 50:
        warnings.append(
            f"May struggle to achieve 50 events/week. "
            f"Estimated: {estimated_events}. "
            f"Consider moving to earlier stage."
        )

    # Logical progression check
    if cs_definition['stage'] == 'Decision' and not warm_audience_exists:
        warnings.append(
            "Decision stage requires retargeting audience. "
            "May want to start with earlier stage."
        )

    return errors, warnings
```

---

### 2.5 VE (Value Expression Type) Generator

**Framework Requirements**:
- **Closed set**: INSIGHT / VALIDATION / FRAMEWORK / SYSTEM
- **One per campaign** (NEVER mix)
- Must align with stage

**Mapping**:
- **INSIGHT**: Reframes the problem (Exploration)
- **VALIDATION**: Normalizes the error (Exploration/Identification)
- **FRAMEWORK**: Organizes the problem (Identification)
- **SYSTEM**: Step-by-step execution (Validation/Decision)

**Critical Rule**: Mixing VE types creates semantic ambiguity that destroys learning.

---

### 2.6 EA (Emotional Axis) Generator

**Framework Requirements**:
- Format: [From State] → [To State]
- One per campaign (never mixed)
- Common axes: confusion→clarity, insecurity→confidence, overwhelm→control

**Key Distinction**:
- **EA** is the EMOTIONAL journey
- **OF** is the BEHAVIORAL change
- They should be complementary

**Example**:
- EA: confusion → clarity (emotional)
- OF: Users evaluate options using a framework rather than guessing (behavioral)

---

### 2.7 AL (Abstraction Level) Generator

**Framework Requirements**:
- High / Medium / Low
- Ads should be Medium or Low (not High)
- Early stage (Exploration) can be more abstract
- Decision stage must be concrete

---

### 2.8 CTA-R (CTA Intensity Range) Generator

**Framework Requirements**:
- Constrained by: **Stage (dominant)**, Brand Role, Trust level

**Per-Stage Ranges**:
- **Exploration**: Passive/curiosity ("See how it works")
- **Identification**: Informational ("Learn more", "Discover")
- **Validation**: Commitment ("Register", "Get access")
- **Decision**: Action ("Buy", "Join", "Start")

**Output Format**:
```json
{
  "minimum_intensity": "softest acceptable CTA",
  "maximum_intensity": "strongest acceptable CTA",
  "reasoning": "why this range",
  "acceptable_ctas": ["See how it works", "Learn more", "Discover"],
  "too_weak": ["Maybe look"],
  "too_strong": ["Buy now", "Start trial"]
}
```

---

### 2.9 SCR (Semantic Consistency Rules) Generator

**Framework Requirements**:
- **Core promise**: Must appear in all creatives
- **Required language**: Specific words/phrases to always use
- **Forbidden claims**: What cannot be promised
- **Immutable theme**: The unchanging semantic identity

**Purpose**: Prevent semantic variation that destroys learning

**LLM Prompt includes**:
- Brand language patterns from research
- Competitor claims to differentiate from
- Regulatory constraints for industry
- All other locked variables (PS, OF, VE, EA)

---

## Phase 3: Validation & Consistency Engine

### 3.1 Hard Constraint Validation

Each variable's output is validated against:
1. **Structural requirements** (format, required fields)
2. **Framework compliance** (behavioral vs psychological, observable vs aspirational)
3. **Cross-variable consistency** (do variables work together?)

### 3.2 Cross-Variable Consistency Checks

```python
class ConsistencyValidator:
    def check_all_consistency(self, variables):
        errors = []
        warnings = []

        # PS-OF coherence
        if not of_addresses_ps(variables['OF'], variables['PS']):
            errors.append("OF doesn't address PS structural cause")

        # CS-VE alignment
        stage_ve_map = {
            'Exploration': ['INSIGHT', 'VALIDATION'],
            'Identification': ['VALIDATION', 'FRAMEWORK'],
            'Validation': ['FRAMEWORK', 'SYSTEM'],
            'Decision': ['SYSTEM']
        }
        if variables['VE'] not in stage_ve_map[variables['CS']]:
            errors.append(f"VE {variables['VE']} not aligned with stage {variables['CS']}")

        # CS-CTA-R alignment
        if not cta_range_matches_stage(variables['CTA-R'], variables['CS']):
            errors.append("CTA intensity doesn't match cognitive stage")

        # BR-CTA-R consistency
        if variables['BR']['position'] == 'Beside' and cta_too_authoritative(variables['CTA-R']):
            errors.append("Peer brand role with authoritative CTA breaks credibility")

        # CS-AL consistency
        if variables['CS'] == 'Decision' and variables['AL'] == 'High':
            errors.append("Decision stage requires Low abstraction, not High")

        # EA-OF complementarity
        if not ea_complements_of(variables['EA'], variables['OF']):
            warnings.append("Emotional axis doesn't complement behavioral outcome")

        return errors, warnings
```

### 3.3 System Identity Rule Check

**Critical Validation** (from [File 7](./META-ADS-VAULT/02-STRUCTURAL-STRATEGY/07-Immutable-Global-Variables.md)):
> If PS, OF, or BR change, it is not an iteration. It is another system.

Validates that PS, OF, BR form ONE coherent system identity.

---

## Phase 4: Iterative Refinement Loop

### 4.1 Auto-Fix Mechanism

When validation errors are detected, the system attempts automatic fixes:

```python
class RefinementEngine:
    def auto_fix_violations(self, variable, errors, all_variables):
        """
        Attempts to fix validation errors automatically
        """
        for error in errors:
            if error.type == 'psychological_language_in_ps':
                # Regenerate PS with stronger behavioral constraint
                prompt = self.build_refinement_prompt(
                    variable='PS',
                    error=error,
                    constraint="Must use ONLY observable behaviors, NO psychological terms",
                    previous_attempt=variable
                )
                refined = self.llm_call(prompt)
                return refined

            elif error.type == 'cta_stage_mismatch':
                # Regenerate CTA-R with explicit stage constraint
                prompt = self.build_refinement_prompt(
                    variable='CTA-R',
                    error=error,
                    constraint=f"Stage is {all_variables['CS']}. CTA must be {STAGE_CTA_MAP[all_variables['CS']]}",
                    previous_attempt=variable
                )
                refined = self.llm_call(prompt)
                return refined
```

### 4.2 Refinement Loop Flow

```
Generate All Variables
     ↓
Validate Each Variable
     ↓
Validate Cross-Variable Consistency
     ↓
Errors Found? ──Yes──> Auto-Fix Attempt ──> Validate Again
     │                                            │
     No                                     Still Errors?
     ↓                                            ↓
Calculate Confidence Scores              Manual Refinement Needed
     ↓                                            ↓
Confidence > 80%? ──No──> Flag for User Review
     │
    Yes
     ↓
Proceed to User Interaction
```

---

## Phase 5: User Interaction Interface

### 5.1 Presentation Strategy

**Technology**: Web interface (React/Next.js) or CLI with rich formatting

**Approach**: Present one variable at a time, grouped logically

**Groups**:
1. **System Identity** (PS, OF, BR) - most critical, lock these first
2. **Campaign Configuration** (CS, VE, EA, AL, CTA-R) - dependent on system identity
3. **Semantic Rules** (SCR) - derived from all above

### 5.2 Variable Presentation Format

```
┌─────────────────────────────────────────────────────┐
│ PS: PROBLEM SPACE                                    │
├─────────────────────────────────────────────────────┤
│                                                      │
│ RECOMMENDED:                                         │
│ Operators launch ads without defined structural     │
│ variables first, resulting in:                      │
│   1. Inconsistent creative briefing                 │
│   2. Poor learning accumulation                     │
│   3. Wasted budget on semantic variation            │
│                                                      │
│ WHY THIS PS:                                         │
│ - Research shows 73% lack campaign templates        │
│ - Your ads show variation in emotional axis         │
│ - Structural cause addressable by your product      │
│                                                      │
│ CONFIDENCE: 8.5/10                                   │
│                                                      │
│ ALTERNATIVES:                                        │
│ Option B: [Different PS with reasoning]             │
│ Option C: [Different PS with reasoning]             │
│                                                      │
│ [✓ Accept] [→ Alternatives] [✏️ Refine] [❌ Reject] │
└─────────────────────────────────────────────────────┘
```

### 5.3 Interactive Refinement Options

**User Actions**:
1. **Accept**: Lock variable and proceed
2. **See Alternatives**: View 2-3 alternative definitions
3. **Refine**: Provide feedback, system regenerates
4. **Reject**: Manually input definition (system validates)

---

## Phase 6: Final Output Generation

### 6.1 Campaign Definition Sheet

Complete 22-field Campaign Definition Sheet in [File 22](./META-ADS-VAULT/04-OPERATIONAL-CONTROL/22-Master-Checklists-and-Execution-Templates.md) format:

**Sections**:
1. System Identity (PS, OF, BR)
2. Campaign Configuration (CS, VE, EA, AL, CTA-R)
3. Semantic Rules (SCR)
4. User State Model (S0, S1, Progress Signals)
5. Campaign Architecture
6. Governance

### 6.2 Evidence Pack

Separate document with:
- Research summary from all 4 agents
- Evidence trail (every claim → source)
- Confidence scores
- Alternative definitions considered
- Risks and limitations

### 6.3 Next Steps Guide

Automatic generation of action plan:
1. Review and approve Campaign Definition Sheet
2. User State Definition (S0/S1)
3. Campaign Architecture Planning
4. Creative Brief Development
5. Launch Checklist

---

## Technology Stack

### Core Infrastructure
- **Language**: Python 3.11+
- **Orchestration**: Apache Airflow or Prefect
- **Database**: PostgreSQL for research, variables, evidence
- **Vector DB**: Pinecone or Weaviate for semantic search
- **Caching**: Redis for API call caching

### LLM Layer
- **Primary Reasoning**: Claude Opus 4.6 (Anthropic) - best reasoning for complex variables
- **Fast Analysis**: Claude Sonnet 4.5 (Anthropic) - research synthesis
- **Multimodal**: GPT-4o (OpenAI) - analyze existing ads/images
- **Embedding**: text-embedding-3-large (OpenAI) or Voyage AI

### Research Tools
- **Web Scraping**: Firecrawl API, Apify, or custom Playwright
- **Meta Ad Library**: Official Meta Ad Library API
- **Web Research**: Perplexity API, Exa.ai, or Tavily AI
- **Social Media**: Twitter API, LinkedIn API, Reddit API
- **Academic**: Semantic Scholar API
- **Website Analysis**: Custom crawler + Beautiful Soup

### Validation Layer
- **Framework Rules**: Custom Python validation library
- **Linguistic Analysis**: Spacy/NLTK (check psychological vs behavioral language)
- **ML Classifier**: Fine-tuned model for PS/OF compliance detection

### User Interface
- **Web UI**: Next.js + React + Tailwind CSS
- **Backend API**: FastAPI (Python)
- **Real-time**: WebSocket for progress tracking
- **CLI Alternative**: Rich library for terminal interface

---

## Data Flow

```
USER INPUT (minimal)
    ↓
INPUT VALIDATION & ENRICHMENT
    ↓
RESEARCH ORCHESTRATION (parallel)
    ├─ Company Research Agent
    ├─ Industry Research Agent
    ├─ Competitor Research Agent
    └─ Audience Research Agent
    ↓
KNOWLEDGE SYNTHESIS
    ↓
VARIABLE GENERATION (sequential)
    ├─ PS Generator → Validate
    ├─ OF Generator → Validate
    ├─ BR Generator → Validate
    ├─ CS Generator → Validate
    ├─ VE Generator → Validate
    ├─ EA Generator → Validate
    ├─ AL Generator → Validate
    ├─ CTA-R Generator → Validate
    └─ SCR Generator → Validate
    ↓
CROSS-VARIABLE VALIDATION
    ↓
ERRORS? ──Yes──> REFINEMENT LOOP ──> Re-validate
    │
    No
    ↓
CONFIDENCE SCORING
    ↓
USER INTERACTION INTERFACE
    ↓
All Variables Locked?
    ↓
   Yes
    ↓
FINAL OUTPUT GENERATION
    ├─ Campaign Definition Sheet
    ├─ Evidence Pack
    └─ Next Steps Guide
```

---

## Implementation Phases

### Phase 1: MVP (8-10 weeks)
**Core system with manual research assistance**

**Components**:
1. Input interface (simple web form)
2. Company Research Agent (web scraping + LLM)
3. Variable Generation Engine (all 9 generators)
4. Hard validation layer
5. Simple user review interface
6. Campaign Definition Sheet output

**Research**: Semi-automated (tool suggests, user provides inputs)

### Phase 2: Enhanced Research (4-6 weeks)
**Fully automated research**

**Add**:
1. Industry Research Agent
2. Competitor Research Agent (Meta Ad Library)
3. Audience Research Agent (Reddit/Quora)
4. Knowledge Synthesis Engine
5. Evidence tracking

### Phase 3: Advanced Interaction (4-6 weeks)
**Sophisticated user interaction**

**Add**:
1. Alternative generation (2-3 options per variable)
2. Interactive refinement with feedback loop
3. Progress tracking UI
4. Evidence Pack generation
5. Confidence scoring

### Phase 4: Intelligence Layer (6-8 weeks)
**Learning and improvement**

**Add**:
1. Historical campaign performance integration
2. A/B testing of variable definitions
3. Success pattern recognition
4. Industry-specific tuning
5. Custom ML classifier
6. Active learning from user feedback

### Phase 5: Integration & Scale (4-6 weeks)
**Production-ready**

**Add**:
1. Meta Ads Manager integration
2. JSON export
3. API for programmatic access
4. Multi-user/agency support
5. Template library (per industry)
6. Batch processing

---

## Success Metrics

### System Quality Metrics
- **Framework Compliance Rate**: >95% (variables passing all validation)
- **Cross-Variable Coherence**: >85/100
- **Research Quality**: >80/100 average confidence

### User Experience Metrics
- **Time to Complete**: <60 minutes (vs 6-8 hours manual)
- **User Acceptance Rate**: >70% (variables accepted without modification)
- **Refinement Iterations**: <2 iterations per variable

### Business Outcome Metrics
- **Campaign Success Rate**: >80% (meet learning phase goals)
- **Expert Review Pass Rate**: >90% (validated by GrowFu experts)
- **Cost Savings**: 85%+ time reduction

---

## Example Walkthrough

### Input
```json
{
  "company_name": "DataFlow Analytics",
  "company_description": "B2B SaaS platform helping marketing teams consolidate data from multiple sources into actionable dashboards",
  "brand_info": "Positioned as the 'single source of truth' for marketing performance",
  "product": "Dashboard software with automated reporting, multi-channel integration, AI-powered insights",
  "target_audience": "Marketing directors and CMOs at mid-market B2B companies (50-500 employees)",
  "existing_materials": "https://dataflowanalytics.com"
}
```

### Generated Variables (Summary)

**PS**: Marketing teams make strategic decisions using incomplete data because their metrics are fragmented across disconnected tools, resulting in: (1) 15+ hours weekly compiling reports, (2) making decisions based on most accessible data not most relevant, (3) presenting inconsistent numbers in meetings

**OF**: Marketing leaders evaluate channel performance using unified attribution methodology across all channels instead of making decisions based on fragmented, inconsistent data sources

**BR**: Direction: Bidirectional | Intensity: Medium | Position: Beside (guide/enabler)

**CS**: Identification (LPV optimization event)

**VE**: FRAMEWORK (presenting "3-Layer Attribution Framework")

**EA**: Overwhelm → Control

**AL**: Medium (concept with concrete examples)

**CTA-R**: Informational ("See How It Works", "Learn the Framework")

**SCR**: Core promise: "See all your marketing performance in one unified dashboard with consistent attribution" | Required language: "unified", "attribution", "single source of truth"

**Total Time**: 45 minutes | **Confidence**: 8.5/10

---

## Risk Mitigation

### Research Quality Risks
- Multi-source validation (2+ sources for key claims)
- Confidence scoring for all findings
- Human review checkpoints for low-confidence areas
- Source quality filtering

### LLM Hallucination Risks
- Hard validation rules prevent structural violations
- Evidence requirement: every claim cites research
- Multi-LLM validation (cross-check with different models)
- User review mandatory for all variables

### Framework Misinterpretation Risks
- Extensive prompt engineering with framework quotes
- Examples library of correct definitions
- Fine-tuning on validated variable sets
- Framework creator review (initially)

---

## Critical Reference Files

1. **[07-Immutable-Global-Variables.md](./META-ADS-VAULT/02-STRUCTURAL-STRATEGY/07-Immutable-Global-Variables.md)** - Complete variable definitions, requirements, validation rules
2. **[22-Master-Checklists-and-Execution-Templates.md](./META-ADS-VAULT/04-OPERATIONAL-CONTROL/22-Master-Checklists-and-Execution-Templates.md)** - Campaign Definition Sheet template structure
3. **[09-Cognitive-Stages-and-Optimization-Contracts.md](./META-ADS-VAULT/02-STRUCTURAL-STRATEGY/09-Cognitive-Stages-and-Optimization-Contracts.md)** - Stage definitions, optimization events, CTA ranges
4. **[08-User-States-and-Observable-Signals.md](./META-ADS-VAULT/02-STRUCTURAL-STRATEGY/08-User-States-and-Observable-Signals.md)** - S0/S1 definitions, observable signals
5. **[Glossary-and-Acronyms.md](./META-ADS-VAULT/05-REFERENCE/Glossary-and-Acronyms.md)** - Authoritative definitions for all 9 variables

---

*This Intelligent Variable Generator system represents a sophisticated application of AI research agents, multi-LLM reasoning, and strict validation logic to automate the complex strategic process of defining campaign variables, reducing expert-level work from 6-8 hours to 45-60 minutes while maintaining framework compliance and quality.*
