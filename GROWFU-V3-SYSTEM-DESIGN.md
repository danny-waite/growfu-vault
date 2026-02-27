# GrowFu v3: High-Level System Design Document

## Context

GrowFu v3 currently exists as a comprehensive knowledge base (Obsidian vault) documenting the Meta Ads System Engineering Framework. The framework treats Meta's advertising platform as a **learning and allocation machine** rather than traditional ad placement. It contains 22+ documents across 4 major sections covering system physics, structural strategy, creative engineering, and operational control.

**The Need**: Transform this documented framework into an operational, intelligent platform that automates campaign definition, semantic validation, learning phase tracking, creative intelligence, and operational governance.

**The Goal**: Build an end-to-end system that enables advertisers to:
- Design campaigns as learnable systems (not random ad collections)
- Engineer creative that generates optimal signals for Meta's ML algorithms
- Monitor and maintain campaign health through real-time learning analytics
- Scale performance systematically while preserving learning continuity

---

## 1. System Overview

### What GrowFu v3 Will Be

An **intelligent Meta Ads system engineering platform** consisting of 10 integrated sub-systems that operationalize the framework's principles:

```
Campaign Definition → Creative Validation → Launch & Learning → Real-Time Monitoring → Optimization → Scaling
        ↑                                                                                                 ↓
        └──────────────────────────── Continuous Feedback & Adaptation ─────────────────────────────────┘
```

### Core Philosophy

Meta doesn't "choose ads" — it allocates impressions by optimizing predicted outcomes under constraints (user experience, quality, risk). GrowFu v3 makes this predictable and controllable by:

1. **Enforcing System Integrity** - Validating all changes against immutable variables
2. **Maintaining Semantic Consistency** - Using LLM analysis to ensure creative variations maintain identity
3. **Tracking Learning Intelligence** - Real-time signal accumulation and learning phase exit prediction
4. **Detecting Fatigue Early** - Multi-signal monitoring 5-7 days before performance collapse
5. **Optimizing Architecture** - Recommending campaign structure based on budget and signal volume
6. **Validating Stage Alignment** - Preventing optimization events users can't perform

### Primary Users

- **Campaign Strategists**: Define campaigns using 9 Immutable Global Variables
- **Creative Engineers**: Design multimodal creative Meta can learn from
- **Performance Operators**: Monitor learning, diagnose fatigue, manage scaling
- **Agency Teams**: Manage multiple accounts with consistent methodology

---

## 2. Sub-Systems Architecture

### 2.1 Campaign Definition Engine

**Purpose**: Transform strategic inputs into validated campaign system specifications.

**Core Responsibilities**:
- Guide users through 9 Immutable Global Variables (PS, OF, BR, CS, VE, EA, AL, CTA-R, SCR)
- Validate PS (Problem Space) is observable and behavioral
- Ensure OF (Outcome Function) is state transition, not aspiration
- Map cognitive stages to appropriate optimization events
- Generate Campaign Definition Sheet (22 validated fields)
- Enforce stage-appropriate targeting, CTA intensity, VE type

**Technology Stack**:
- **LLM**: GPT-4/Claude for PS/OF validation, suggesting behavioral symptoms
- **Rule Engine**: Stage-to-optimization-event mappings, CTA intensity constraints
- **Database**: PostgreSQL for campaign definitions, version history
- **Validation Engine**: Conflict checking (VE type vs. stage alignment)

**Inputs**: PS, OF, BR definitions; cognitive stage; budget; target audience size

**Outputs**: Complete Campaign Definition Sheet; recommended architecture; stage-specific creative brief; locked immutable variables

**Key Reference**: [07-Immutable-Global-Variables.md](./META-ADS-VAULT/02-STRUCTURAL-STRATEGY/07-Immutable-Global-Variables.md)

---

### 2.2 Semantic Consistency Engine

**Purpose**: Ensure all creative variations maintain same latent identity in Meta's embedding space.

**Core Responsibilities**:
- Analyze creative text/visual/audio for SCR (Semantic Consistency Rules) compliance
- Detect when variations cross semantic boundaries (becoming "different systems")
- Generate semantic similarity scores for creative portfolio
- Flag violations of immutable variables (PS, OF, VE, EA)
- Predict Creative Similarity Score (Meta Andromeda metric)

**Technology Stack**:
- **Multimodal LLM**: GPT-4V/Claude Sonnet for text + image/video analysis
- **Embedding Models**: OpenAI text-embedding-3, CLIP for semantic distance measurement
- **Rule Engine**: SCR enforcement (forbidden claims, required language, core promise)
- **Computer Vision**: Meta Andromeda simulation for creative clustering prediction

**Inputs**: Creative assets (text/images/videos); campaign SCR; existing portfolio

**Outputs**: Semantic consistency score (0-100); violation report; predicted Creative Similarity Score; recommended variations within tolerance

**Key Reference**: [13-Creative-Identity-and-Portfolio-Architecture.md](./META-ADS-VAULT/03-CREATIVE-ENGINEERING/13-Creative-Identity-and-Portfolio-Architecture.md)

---

### 2.3 Creative Intelligence System

**Purpose**: Manage creative portfolio lifecycle, detect fatigue/saturation, recommend rotation.

**Core Responsibilities**:
- Track creative through lifecycle phases: Exploratory → Control Candidate → Control → Fatiguing → Retired
- Monitor micro-signals (hold rate, watch time, completion) and macro-signals (CVR, CPA)
- Diagnose fatigue vs. saturation via multi-signal pattern matching
- Recommend refresh timing (2-4 weeks based on spend velocity)
- Manage portfolio clusters: Core Control, Variation A, Variation B, Exploratory
- Generate embedding-aware performance insights

**Technology Stack**:
- **Time-Series Database**: InfluxDB/TimescaleDB for hourly/daily micro-signal metrics
- **ML Model**: Gradient Boosting (XGBoost) for fatigue prediction 5-7 days early
- **Pattern Matching Engine**: Distinguish fatigue (CVR↓, hide/report flat) from saturation (hide/report↑)
- **LLM**: GPT-4 for natural language insights generation

**Inputs**: Real-time Meta Ads data (CTR, CVR, watch time, hide/report); creative assets; campaign stage

**Outputs**: Fatigue alerts (5-7 day advance warning); rotation recommendations; portfolio health score; Creative Similarity Score tracking; optimal refresh schedule

**Key Reference**: [13-Creative-Identity-and-Portfolio-Architecture.md](./META-ADS-VAULT/03-CREATIVE-ENGINEERING/13-Creative-Identity-and-Portfolio-Architecture.md), [20-Fatigue-Saturation-and-Rotation.md](./META-ADS-VAULT/04-OPERATIONAL-CONTROL/20-Fatigue-Saturation-and-Rotation.md)

---

### 2.4 Learning Phase Manager

**Purpose**: Track signal accumulation and predict learning phase exit with precision.

**Core Responsibilities**:
- Monitor optimization event volume real-time (target: ~50 events in 7 days)
- Calculate signal accumulation rate and predict learning phase exit date
- Detect learning phase resets (from budget changes >30%, optimization event changes)
- Recommend budget levels to achieve 50-event threshold within target timeframe
- Alert when actions risk re-entering learning phase
- Track learning continuity across creative rotations

**Technology Stack**:
- **Event Stream Processor**: Apache Kafka/Flink for real-time event counting
- **Predictive Model**: Linear Regression + Monte Carlo for learning phase exit forecasting
- **Rule Engine**: Validate changes against learning phase disruption rules
- **Database**: PostgreSQL for learning phase history, event accumulation curves

**Inputs**: Real-time conversion events (Meta Pixel/Conversions API); campaign budget/spend; proposed changes

**Outputs**: Learning phase status dashboard (events accumulated, % to threshold, predicted exit); budget recommendations; change impact predictions; learning continuity score

**Key Reference**: [17-Budget-Variance-and-Stability.md](./META-ADS-VAULT/04-OPERATIONAL-CONTROL/17-Budget-Variance-and-Stability.md)

---

### 2.5 Attribution & Signal Quality Monitor

**Purpose**: Detect signal quality issues before they degrade delivery.

**Core Responsibilities**:
- Monitor CTR-CVR dissonance (high click, low conversion = mismatch)
- Track post-click behavior (bounce rate, time on page, scroll depth)
- Identify false positive signals (clicks without intent)
- Calculate signal quality scores per creative
- Alert on quality degradation trends
- Recommend landing page optimizations

**Technology Stack**:
- **Web Analytics**: Google Analytics 4, custom tracker for post-click behavior
- **Anomaly Detection**: Isolation Forest ML model for unusual signal patterns
- **Database**: ClickHouse for high-volume event data analytics
- **Dashboarding**: Grafana/Metabase for real-time signal quality visualization

**Inputs**: Meta Ads performance (CTR, CVR, CPA); landing page analytics (bounce, time on page, scroll depth); Meta Pixel events

**Outputs**: Signal quality score per creative (0-100); CTR-CVR alignment report; post-click experience alerts; landing page optimization recommendations

**Key Reference**: [03-Prediction-Heads-and-Multi-Objective-Learning.md](./META-ADS-VAULT/01-SYSTEM-PHYSICS/03-Prediction-Heads-and-Multi-Objective-Learning.md)

---

### 2.6 Budget & Scaling Optimizer

**Purpose**: Recommend scaling actions while maintaining CPA stability and learning continuity.

**Core Responsibilities**:
- Monitor CPA variance (7-day rolling average, day-over-day %)
- Validate scaling readiness (learning exited, CPA stable 7+ days, no rising negative feedback)
- Recommend budget increment size (≤20-30% per adjustment)
- Calculate marginal CPA dynamics (predict CPA at higher budgets)
- Suggest timing of scaling actions (48-72 hour intervals)
- Detect delivery consistency issues

**Technology Stack**:
- **Time-Series Analysis**: Prophet, ARIMA for CPA trajectory forecasting
- **Statistical Testing**: CPA stability determination (coefficient of variation, moving average convergence)
- **Optimization Solver**: Optimal budget allocation across ad sets
- **Rule Engine**: Scaling constraints (20-30% max increment, 48-72hr minimum interval)

**Inputs**: Historical CPA (7-14 day window); current budget/spend; learning phase status; negative feedback trends; competitive density

**Outputs**: Scaling readiness report (green/yellow/red); recommended budget increment; predicted CPA at new budget; optimal timing; risk assessment

**Key Reference**: [17-Budget-Variance-and-Stability.md](./META-ADS-VAULT/04-OPERATIONAL-CONTROL/17-Budget-Variance-and-Stability.md), [19-Competitive-Density-and-Marginal-CPA.md](./META-ADS-VAULT/04-OPERATIONAL-CONTROL/19-Competitive-Density-and-Marginal-CPA.md)

---

### 2.7 Governance & Change Management Engine

**Purpose**: Validate all proposed changes against framework rules before execution.

**Core Responsibilities**:
- Enforce "one variable per iteration" rule
- Validate minimum observation windows (impressions + events + days)
- Detect changes violating immutability (PS, OF, BR changes mid-campaign)
- Prevent changes during learning phase unless justified
- Log all changes with date, reason, expected outcome
- Generate change impact predictions

**Technology Stack**:
- **Rule Engine**: Drools or custom business logic for governance rules encoding
- **Version Control System**: Track campaign configuration changes over time
- **Impact Prediction Model**: Estimate effect on learning phase, CPA
- **Approval Workflow Engine**: Route high-risk changes for review

**Inputs**: Proposed change; current campaign state (learning status, observation window, last change date); immutable variables

**Outputs**: Change validation result (approved/rejected + reason); impact prediction; alternative recommendations; change log entry

**Key Reference**: [21-Governance-and-Change-Management.md](./META-ADS-VAULT/04-OPERATIONAL-CONTROL/21-Governance-and-Change-Management.md)

---

### 2.8 Meta Ads Integration Layer

**Purpose**: Abstract Meta's APIs and normalize data for internal processing.

**Core Responsibilities**:
- Sync campaigns/ad sets/ads bidirectionally with Meta
- Stream real-time performance metrics (CTR, CPA, impressions, conversions)
- Push configuration changes to Meta (budget updates, creative swaps, ad set toggles)
- Normalize Meta's data model to GrowFu's semantic model
- Handle API rate limits, retries, error handling
- Track Meta platform changes (API updates, new features)

**Technology Stack**:
- **API Client**: Python/Node.js SDK for Meta Marketing API, Graph API
- **Event Streaming**: Apache Kafka for real-time metric ingestion
- **Data Pipeline**: Airflow for batch sync jobs (daily performance reports)
- **Caching Layer**: Redis to reduce API calls, improve response time
- **Webhook Listener**: Real-time events from Meta (if available)

**Inputs**: Meta Ads Manager API credentials; campaign/ad set/ad IDs; configuration changes to push

**Outputs**: Normalized performance data stream (standardized schema); entity data (metadata, status, configuration); API operation results

---

### 2.9 User States & Cognitive Stages Database

**Purpose**: Store templates and behavioral definitions for S0/S1 states across cognitive stages.

**Core Responsibilities**:
- Maintain library of S0 (Observable Initial State) templates per stage
- Store S1 (Target State) definitions and measurable progression signals
- Provide stage-specific guidance (optimization events, targeting, CTA intensity)
- Track industry-specific S0/S1 patterns (e-commerce, B2B SaaS, coaching)
- Enable custom S0/S1 definitions per campaign

**Technology Stack**:
- **Database**: PostgreSQL with JSON fields for flexible behavioral signals
- **Template Engine**: Generate S0/S1 templates based on industry/stage
- **LLM**: GPT-4 to suggest observable behavioral signals from PS/OF

**Inputs**: Cognitive stage; industry/vertical; user-provided PS/OF

**Outputs**: S0 template (primary signal, attention signals, light intent, rejection signals, CTA restrictions); S1 definition; progress signals; false positive signals

**Key Reference**: [08-User-States-and-Observable-Signals.md](./META-ADS-VAULT/02-STRUCTURAL-STRATEGY/08-User-States-and-Observable-Signals.md), [09-Cognitive-Stages-and-Optimization-Contracts.md](./META-ADS-VAULT/02-STRUCTURAL-STRATEGY/09-Cognitive-Stages-and-Optimization-Contracts.md)

---

### 2.10 Reporting & Insights Engine

**Purpose**: Generate natural language insights and executive summaries from technical data.

**Core Responsibilities**:
- Translate technical metrics into strategic insights
- Generate weekly performance reports with embedding-aware analysis
- Produce campaign health scores (learning, signal quality, portfolio diversity)
- Create executive dashboards (non-technical stakeholder view)
- Identify causal patterns (e.g., "CPA spike caused by Variation B hook exhaustion")
- Recommend next actions with rationale

**Technology Stack**:
- **LLM**: GPT-4 for natural language report generation from structured data
- **Business Intelligence**: Metabase/Looker for interactive dashboards
- **Causal Inference Engine**: Identify cause-effect relationships
- **Report Generator**: Templated reports with dynamic insights

**Inputs**: All system metrics (learning phase, CPA, signal quality, fatigue status); campaign configuration/history; industry benchmarks

**Outputs**: Weekly performance reports (narrative + data); campaign health dashboard (real-time); executive summary (high-level KPIs + strategic recommendations); anomaly alerts with explanations

---

### 2.11 Marketing Metrics Analysis Agent (MMAA)

**Purpose**: Bridge the gap between Meta platform performance and business unit economics to assess campaign profitability.

**Core Responsibilities**:
- **Pre-launch viability gating**: Prevent unprofitable campaigns by comparing estimated CPA to viable CAC ceiling (derived from LTV)
- **Post-launch monitoring**: Track actual CAC vs. viable ceiling in real-time with HEALTHY/WARNING/CRITICAL status
- **Stage-aware CAC calculation**: Implement multi-stage cumulative CAC (Exploration → Identification → Validation → Decision)
- **Expansion physics detection**: Distinguish expected marginal CAC rise during scaling (File 19) from problematic degradation
- **Learning phase filtering**: Exclude noisy learning-phase CAC from viability comparisons; use steady-state CAC only (File 17)
- **LTV estimation engine**: Calculate LTV using cohort projection, first-year proxy, or industry benchmarks with confidence scoring
- **Governance integration**: Auto-pause campaigns via Governance Engine when CAC exceeds 85% viable ceiling for 2+ days

**Technology Stack**:
- **LLM Reasoning**: Claude Opus 4.6 (nuanced viability assessment synthesis), GPT-4 (strategic recommendations)
- **Database**: PostgreSQL (viability assessments, pre-launch decisions)
- **Time-Series DB**: TimescaleDB (real-time CAC tracking, unit economics snapshots)
- **Event Streaming**: Kafka consumer for real-time performance data
- **Forecasting**: Prophet, ARIMA (LTV projection, CAC trend prediction)
- **Anomaly Detection**: Isolation Forest (viability alert triggers)

**Inputs**: LTV estimate (user-provided or calculated); estimated/actual CPA; spend and conversions; learning phase status; cognitive stage; recent scaling history

**Outputs**: Pre-launch: GO/CAUTION/NO-GO status with reasoning, viable CAC ceiling, risk factors, recommendations; Post-launch: Real-time viability status, CAC utilization %, LTV:CAC ratio, contribution margin, WARNING/CRITICAL alerts, optimization priorities

**Integration with Other Sub-Systems**:
- **Campaign Definition Engine**: Pre-launch viability gate (synchronous blocking)
- **Budget & Scaling Optimizer**: Viability-informed scaling approval (bidirectional)
- **Attribution & Signal Quality Monitor**: Real-time performance data stream (upstream)
- **Reporting & Insights Engine**: Viability dashboard and metrics (downstream)
- **Learning Phase Manager**: Learning phase filtering context (upstream)
- **Creative Intelligence System**: Creative-driven CAC optimization insights (upstream)
- **Governance Engine**: Auto-pause on CRITICAL viability breach (downstream)

**Key Reference**: [23-LTV-and-Unit-Economics.md](./META-ADS-VAULT/04-OPERATIONAL-CONTROL/23-LTV-and-Unit-Economics.md), [24-Marketing-Metrics-Analysis-Agent.md](./META-ADS-VAULT/04-OPERATIONAL-CONTROL/24-Marketing-Metrics-Analysis-Agent.md)

**Core Value Proposition**: Shift from "**Is this campaign performing well?**" (Meta platform metrics) to "**Is this campaign profitable?**" (business unit economics).

---

## 3. Technology Stack Summary

### 3.1 ML/AI Components

| Component | Technology | Purpose |
|-----------|-----------|---------|
| **Semantic Analysis** | GPT-4, Claude Sonnet 4.5 | Analyze creative for SCR compliance, PS/OF validation |
| **Multimodal Understanding** | GPT-4V, Claude + vision | Evaluate image/video creative semantic alignment |
| **Embedding Generation** | OpenAI text-embedding-3, CLIP | Measure semantic distance between creatives |
| **Fatigue Prediction** | Gradient Boosting (XGBoost) | Predict fatigue onset 5-7 days early |
| **Anomaly Detection** | Isolation Forest, LSTM | Detect unusual signal quality patterns |
| **Time-Series Forecasting** | Prophet, ARIMA | Predict CPA trajectory, learning phase exit date |
| **Causal Inference** | DoWhy, CausalML | Identify cause-effect relationships in performance |

### 3.2 LLM Components

| Use Case | Model | Rationale |
|----------|-------|-----------|
| **Campaign Definition Validation** | GPT-4 | Complex reasoning about PS/OF behavioral observability |
| **Creative Semantic Analysis** | Claude Sonnet 4.5 | Long context window for analyzing creative portfolios |
| **Insight Generation** | GPT-4 | Natural language report generation, strategic recommendations |
| **User Guidance** | GPT-3.5 Turbo | Interactive campaign definition wizard, lower latency |

### 3.3 Rule Engines

| Engine | Technology | Purpose |
|--------|-----------|---------|
| **Governance Rules** | Drools (Java) or custom Python | Encode all framework rules (immutability, one variable per iteration) |
| **Validation Rules** | JSON Schema + custom validators | Validate campaign definition completeness, stage-event alignment |
| **Change Impact Rules** | Decision trees, rule tables | Predict learning phase reset risk, CPA impact |

### 3.4 Data Storage

| Data Type | Database | Rationale |
|-----------|----------|-----------|
| **Campaign Definitions** | PostgreSQL | ACID transactions, complex relational queries |
| **Time-Series Metrics** | TimescaleDB (PostgreSQL extension) | Efficient storage/querying of high-frequency performance data |
| **Event Streams** | Apache Kafka | Real-time conversion event ingestion |
| **Analytics (high-volume)** | ClickHouse | Fast aggregations over billions of events |
| **Embeddings** | Pinecone / Weaviate | Vector similarity search for semantic analysis |
| **Cache** | Redis | API response caching, session management |
| **Object Storage** | S3 | Creative assets (images, videos), reports |

### 3.5 APIs and Integrations

| Integration | API/Service | Purpose |
|-------------|------------|---------|
| **Meta Ads** | Meta Marketing API, Graph API | Campaign management, performance data |
| **Conversion Tracking** | Meta Pixel, Conversions API | Real-time event tracking |
| **Creative Analysis** | Meta Andromeda API (when available) | Creative Similarity Score, Entity IDs |
| **Web Analytics** | Google Analytics 4 API | Post-click behavior tracking |
| **Landing Page Testing** | Custom tracker, Hotjar API | Bounce rate, scroll depth, heat maps |

### 3.6 Real-Time vs. Batch Processing

| Component | Processing Mode | Frequency |
|-----------|----------------|-----------|
| **Conversion Events** | Real-time (Kafka stream) | Sub-second |
| **Learning Phase Tracking** | Real-time (aggregation) | 15 minutes |
| **Performance Metrics Sync** | Batch (Airflow job) | Hourly |
| **Fatigue Detection** | Batch (signal analysis) | Daily |
| **CPA Variance Analysis** | Batch (time-series analysis) | Daily |
| **Creative Similarity Score** | Batch (from Meta) | Daily |
| **Reports** | Batch (scheduled generation) | Weekly |

---

## 4. Data Flow Architecture

### 4.1 Campaign Creation Flow

```
User Input (Campaign Strategist)
    ↓
Campaign Definition Engine
    → Validate PS (observable, behavioral?)
    → Validate OF (state transition, not aspiration?)
    → Select Cognitive Stage
    → Map Stage → Optimization Event
    → Define S0/S1 states
    → Set Immutable Variables (PS, OF, BR, VE, EA, SCR)
    ↓
Generate Campaign Definition Sheet (22 fields)
    ↓
Architecture Optimizer
    → Calculate minimum budget for 50 events in 7 days
    → Recommend # of ad sets (avoid fragmentation)
    → Suggest audience size (avoid saturation)
    ↓
Store in Campaign Database (PostgreSQL)
    ↓
Sync to Meta Ads Manager (via Integration Layer)
    ↓
Ready for Creative Production
```

### 4.2 Creative Production & Validation Flow

```
Creative Assets (text, image, video)
    ↓
Semantic Consistency Engine
    → Extract semantic meaning (LLM)
    → Generate embeddings (text-embedding-3, CLIP)
    → Compare to SCR (Semantic Consistency Rules)
    → Check VE type alignment
    → Check EA alignment
    → Measure distance from existing portfolio creatives
    ↓
Validation Report
    → Semantic consistency score (0-100)
    → SCR violations (if any)
    → Predicted Creative Similarity Score
    ↓
If PASS:
    → Store in Creative Database
    → Assign to Portfolio Cluster (Control, Variation A/B, Exploratory)
    → Push to Meta Ads Manager
    ↓
If FAIL:
    → Return to Creative Engineer with specific violation feedback
    → Suggest modifications to stay within semantic tolerance
```

### 4.3 Learning Phase & Optimization Flow

```
Campaign Launches on Meta
    ↓
Meta Pixel / Conversions API
    → Conversion events stream to Kafka
    ↓
Learning Phase Manager
    → Real-time event counting
    → Track toward 50-event threshold
    → Predict learning phase exit date
    ↓
Every 15 minutes:
    → Update learning status dashboard
    → Alert if accumulation rate too slow
    ↓
Day 7 (or when 50 events reached):
    → Learning Phase EXITED
    → Unlock scaling recommendations
    ↓
Budget & Scaling Optimizer
    → Monitor CPA variance (7-day rolling window)
    → When CPA stable 7+ days:
        → Recommend 20-30% budget increase
        → Predict CPA at new budget level
    ↓
User Approves Scaling
    ↓
Governance Engine
    → Validate scaling action (won't reset learning?)
    → Log change
    ↓
Push budget increase to Meta (via Integration Layer)
    ↓
Continue monitoring (new learning micro-cycle)
```

### 4.4 Fatigue Detection & Rotation Flow

```
Creative Intelligence System (daily job)
    ↓
Fetch performance data from Meta API
    → CTR, CVR, watch time, completion rate
    → Hide rate, report rate, negative feedback score
    ↓
Time-Series Analysis
    → Calculate 5-7 day trends for each metric
    → Pattern matching:
        - Fatigue: CVR↓, hide/report flat
        - Saturation: hide/report↑, CVR↓↓
        - Stabilization: all metrics flat
    ↓
Fatigue Prediction Model (ML)
    → Input: last 14 days of signal trends
    → Output: probability of fatigue in next 7 days
    ↓
If fatigue probability >70%:
    → Generate alert: "Hook exhaustion predicted in 5 days"
    → Recommend: "Rotate to Variation A (already in Exploratory cluster)"
    ↓
User Approves Rotation
    ↓
Semantic Consistency Engine
    → Validate Variation A maintains portfolio identity
    ↓
Governance Engine
    → Validate rotation won't reset learning
    → Log change
    ↓
Push creative swap to Meta (via Integration Layer)
    → Pause fatigued creative
    → Promote Variation A to Control
    ↓
Creative Intelligence System
    → Update portfolio lifecycle states
    → Mark old creative as "Retired"
```

### 4.5 Feedback Loops

**Primary Feedback Loop (Learning Accumulation)**:
Campaign Performance → Learning Phase Manager + Creative Intelligence → Insights Database → Reporting Engine → Creative Engineers → New validated creative → Launch (cycle repeats)

**Secondary Feedback Loop (Portfolio Evolution)**:
Creative Similarity Score (Meta Andromeda) → Creative Intelligence → Recommendation for increased semantic diversity → Campaign Definition Engine suggests broader framing variants (within SCR) → New creatives → Portfolio diversity improves → CPMs normalize

**Tertiary Feedback Loop (System Improvement)**:
All System Metrics → Data Warehouse (aggregated across campaigns) → ML Model Training → Improved fatigue prediction, CPA forecasting, industry S0/S1 templates → Updated models deployed → System becomes more accurate over time

---

## 5. Key Architectural Decisions

### 5.1 Multimodal LLMs for Semantic Analysis

**Decision**: Use GPT-4V/Claude for creative semantic analysis (not keyword matching).

**Rationale**:
- Meta uses multimodal embeddings (text + image + video + audio) to represent ads
- Simple keyword matching misses semantic meaning
- LLMs can reason about PS/OF alignment, VE consistency, EA emotional trajectory
- Creative Similarity Score (Meta Andromeda) is semantic - we need equivalent capability

**Trade-offs**: Higher cost (~$0.01-0.05 per creative), 2-5s latency vs. instant rules, slight output variance requiring ensemble/voting

### 5.2 Real-Time Event Streaming for Learning Phase

**Decision**: Use Kafka to stream conversion events real-time (not batch hourly/daily).

**Rationale**:
- Learning phase threshold is 50 events - at low budgets, each event matters
- Real-time tracking enables immediate alerts ("Just reached 50 events!")
- Batch hourly could delay learning phase exit recognition, missing scaling window
- Meta's system learns real-time; our monitoring should match

**Trade-offs**: Kafka infrastructure more complex, ~$200-500/month vs. batch ~$50/month

### 5.3 Rule Engine for Governance (Not Just LLM)

**Decision**: Use deterministic rule engine (Drools/custom) for governance, with LLM as advisory.

**Rationale**:
- Governance rules are binary (e.g., "changing optimization event WILL reset learning")
- Deterministic rules provide legal/audit trail
- LLMs can hallucinate or be inconsistent on critical decisions
- Speed: rule evaluation <10ms vs. LLM 1-3s

**Hybrid Approach**: Rules for known constraints, LLM for novel situation assessment

### 5.4 Separate Learning Phase Manager

**Decision**: Dedicated subsystem for learning phase tracking (not generic analytics widget).

**Rationale**:
- Learning phase is THE most critical concept ("learning buys performance")
- 50-event threshold is well-documented Meta behavior requiring precise tracking
- Learning phase resets have catastrophic impact (destroys accumulated knowledge)
- Governance decisions depend on learning status (can't change X during learning)
- Requires specialized predictive modeling

**Trade-offs**: Additional subsystem complexity, but worth it because learning phase status is so decision-critical

### 5.5 PostgreSQL + TimescaleDB (Hybrid Storage)

**Decision**: PostgreSQL for campaign definitions, TimescaleDB for time-series metrics.

**Rationale**:
- Campaign definitions are relational (campaigns → ad sets → ads)
- Time-series metrics need efficient time-based queries
- TimescaleDB is PostgreSQL-compatible (same SQL interface, easy migration)
- Hybrid approach: relational JOIN between campaign metadata and performance metrics

### 5.6 Use Meta's Pixel (Not Custom Tracking)

**Decision**: Use Meta Pixel and Conversions API (not custom tracking infrastructure).

**Rationale**:
- Meta's conversion tracking directly feeds their optimization algorithms
- Custom tracking creates attribution mismatch (our numbers ≠ Meta's numbers)
- Meta Pixel benefits from their ML improvements over time
- Compliance: Meta Pixel handles GDPR/CCPA properly

**Supplement**: Can add custom post-click tracking (GA4, custom scripts) for richer behavioral data but primary conversion source remains Meta Pixel

### 5.7 Gradual Rollout (Not Big Bang Launch)

**Decision**: Launch GrowFu v3 in phases (MVP → Full Platform).

**Rationale**:
- Framework is comprehensive (22 documents, 200+ verification claims)
- Faster time-to-value: Campaign Definition + Governance engines alone provide immediate value
- Validation: Need real campaign data to train fatigue prediction models
- Iteration: User feedback on MVP informs full platform design

---

## 6. Implementation Phases

### Phase 1 (MVP - 3 months)
**Core Value**: Prevent learning destruction through systematic campaign planning and governance

**Sub-systems**:
1. Campaign Definition Engine (wizard for 9 immutable variables)
2. Semantic Consistency Engine (basic LLM analysis)
3. Governance Engine (prevent learning phase resets)
4. Meta Ads Integration Layer (sync campaigns)
5. Basic dashboard (learning phase status, CPA tracking)

**Deliverables**:
- Campaign Definition Sheet wizard (22 fields)
- Pre-launch checklist validation
- Change management validation before execution
- Real-time learning phase tracker

### Phase 2 (6 months)
**Core Value**: Intelligent monitoring and proactive optimization

**Sub-systems**:
1. Learning Phase Manager (real-time event tracking, exit prediction)
2. Creative Intelligence System (fatigue detection, portfolio management)
3. Attribution & Signal Quality Monitor (CTR-CVR analysis, post-click tracking)

**Deliverables**:
- Fatigue alerts 5-7 days in advance
- Portfolio health scoring
- Signal quality dashboards
- Predicted learning phase exit dates

### Phase 3 (12 months)
**Core Value**: Predictive optimization and advanced insights

**Sub-systems**:
1. Budget & Scaling Optimizer (ML-based CPA forecasting)
2. Advanced Reporting & Insights (LLM-generated reports)
3. Industry Templates & Benchmarks
4. User States & Cognitive Stages Database (comprehensive library)

**Deliverables**:
- Automated scaling recommendations
- Weekly natural language performance reports
- Industry-specific campaign templates
- Comparative performance benchmarking

---

## 7. Critical Success Factors

### 7.1 Data Quality
- Meta API accuracy and timeliness
- Attribution window consistency
- Cross-validation with Meta Ads Manager UI

### 7.2 LLM Reliability
- Structured output formats to reduce hallucination
- Ensemble approach for critical decisions
- Human-in-the-loop for launch approval
- Result caching for consistency

### 7.3 Meta Platform Changes
- Monitor Meta developer changelog (automated)
- Abstraction layer (internal schema ≠ Meta schema)
- Version tracking (rules flagged with dates)
- Community monitoring for practitioner reports

### 7.4 User Adoption
- Educate WHY (show failed campaigns from rule violations)
- Progressive disclosure (simple mode vs. advanced mode)
- Speed optimization (pre-fill templates, smart defaults)
- Escape hatches (manual override with warning, logged)

---

## 8. Critical Reference Files

The following documentation files are essential for implementation:

1. **[07-Immutable-Global-Variables.md](./META-ADS-VAULT/02-STRUCTURAL-STRATEGY/07-Immutable-Global-Variables.md)**
   - Core system logic: 9 variables (PS, OF, BR, CS, VE, EA, AL, CTA-R, SCR)
   - Variable stability rules and immutability constraints
   - Foundation of Campaign Definition Engine

2. **[22-Master-Checklists-and-Execution-Templates.md](./META-ADS-VAULT/04-OPERATIONAL-CONTROL/22-Master-Checklists-and-Execution-Templates.md)**
   - Complete operational specification
   - Campaign Definition Sheet (22 fields) - exact output format
   - Pre-launch, scaling, change management checklists
   - Encodes all governance rules

3. **[03-Prediction-Heads-and-Multi-Objective-Learning.md](./META-ADS-VAULT/01-SYSTEM-PHYSICS/03-Prediction-Heads-and-Multi-Objective-Learning.md)**
   - Signal quality logic
   - Expected Utility formula and multi-objective optimization
   - CTR-CVR mismatch detection, quality multipliers, risk penalties

4. **[13-Creative-Identity-and-Portfolio-Architecture.md](./META-ADS-VAULT/03-CREATIVE-ENGINEERING/13-Creative-Identity-and-Portfolio-Architecture.md)**
   - Portfolio management rules
   - 4-cluster portfolio structure (Control, Variation A/B, Exploratory)
   - Lifecycle states Creative Intelligence System must track
   - Creative Similarity Score logic and rotation protocols

5. **[17-Budget-Variance-and-Stability.md](./META-ADS-VAULT/04-OPERATIONAL-CONTROL/17-Budget-Variance-and-Stability.md)**
   - Learning phase mechanics
   - 50-event threshold, 20-30% increment limits, variance thresholds
   - What actions reset learning phase (critical for Governance Engine)

---

## 9. Next Steps

1. **Validation Workshop**: Review this design with GrowFu framework stakeholders
2. **Technology Proof-of-Concepts**: Test LLM semantic analysis accuracy, event streaming architecture
3. **Phase 1 Detailed Design**: Break down MVP sub-systems into specific features and user stories
4. **Data Model Design**: Define PostgreSQL schema for campaign definitions
5. **Meta API Access Setup**: Obtain API credentials, test integration patterns

---

## Verification

This design document synthesizes the comprehensive GrowFu v3 framework documentation (22 notes across 4 major sections) into a buildable system architecture. All sub-systems, technologies, and data flows are grounded in the framework's verified principles (confidence scores 7-9 for key mechanics) and Meta's documented platform behavior.

**Design Completeness**: ✓ All 10 sub-systems specified with purpose, responsibilities, technologies, inputs/outputs
**Technology Stack**: ✓ Specific technologies chosen with architectural rationale
**Data Flows**: ✓ End-to-end flows from campaign creation through optimization documented
**Phased Approach**: ✓ 3-phase rollout balances time-to-value with system completeness
**Framework Alignment**: ✓ Design directly implements documented framework principles

---

*This high-level design document serves as the foundation for building GrowFu v3 as an operational intelligent platform that transforms Meta advertising from luck-based to system-based optimization.*