# Intelligent NPI Targeting (INT) Data Science Project

This PRD is a living document. It is perfectly acceptable to update sections as more information becomes available or as project requirements evolve. The purpose of this guide is to ensure a smooth collaboration among all teams, reduce misunderstandings, and support data-driven decision-making in our data science projects.

|Item|Value|
|-|-|
|status|Defining|
|Product Management Sponsor|Jaya Kumawat|
|Data Science PM|Jeremy Miller|
|Data Science Tech Lead|Hassan Malik (SVP Data Science & AI)|
|Other Team Members and Roles|Sunil Rout (Technical Lead/Product Development)|
|Leadership Stakeholder(s)|Sameer Seraj, Chris Caneta|
|Objective|Develop an intelligent NPI targeting system that integrates real-world data (RWD) with market access data to enable proactive physician targeting for pharmaceutical new product launches|
|Due Date|December 18, 2025 (Early Release - Limited Scope)|
|Key Outcomes|Enable pharmaceutical sales teams to identify and target high-impact prescribers before/at product launch; increase prescription adoption rates by 15-20%|
|Deliverable|Production-ready intelligent NPI targeting platform with 3 core use cases (Phase 1)|
|Links|[NEEDS CLARIFICATION - Add Monday Board, Jira, etc.]|

# Project Canvas - Risk Assessment

## Value

### 1. Business Problem/Opportunity

**Core Business Challenge:**
Pharmaceutical companies currently lack an integrated view of prescriber targeting that combines real-world prescribing data with market access/payer restrictions. This results in:
- Reactive "spray and pray" marketing approaches after product launch
- Missed opportunities to target high-potential prescribers proactively
- Inefficient sales rep resource allocation
- Poor understanding of which physicians have favorable vs. restricted access for specific drugs

**a. Who is the user?**
- **Primary:** Pharmaceutical/biopharma sales representatives and sales teams
- **Secondary:** Brand teams, commercial teams, medical affairs teams working on brand strategy
- **Tertiary:** Payers (10% potential usage)

**b. What is the problem we want to solve for them?**
- **For new product launches:** Sales teams need to know WHO to target BEFORE or AT launch time (proactive vs. reactive)
- **Post-launch:** Teams need to monitor brand performance, adoption rates, and identify early adopters vs. laggards
- **Competitive intelligence:** Understanding competitor landscape and market share dynamics
- **Market access barriers:** Identifying which prescribers face payer restrictions (prior authorization, step therapy) that may block prescriptions

### 2. Business or Product Metrics

**Success Metrics (mentioned in transcript):**
- 15-20% increase in prescription volume for targeted physicians
- Time to first prescription (for new launches)
- Adoption rate curves (early adopters, mainstream, laggards)
- Favorable access rate (% of prescribers without payer restrictions)
- Top decile NPI identification accuracy
- [NEEDS CLARIFICATION - Specific KPIs and KBQs mentioned but not detailed]

### 3. Expected ROI

**Value Proposition (from transcript):**
- "Potential financial impact these use cases have had or will be having on the industry" - SPECIFIC DOLLAR AMOUNTS NOT QUANTIFIED
- Proactive targeting provides "substantially more value" than reactive monitoring (Hassan's assessment)
- Capitalizing on "payer wins" - when a drug gets favorable formulary status
- Reducing wasted sales effort on low-potential prescribers

**[NEEDS CLARIFICATION - Specific ROI projections, revenue impact estimates]**

### 4. Alignment with Product Strategy

This is the **first product** in a broader portfolio strategy:
- Part of "Market Access + Real World Data New Products Development" product suite
- Follows a data integration strategy combining previously siloed data sources
- Enables multiple downstream products (6 specialized modules planned)
- Strategic rationale: "Without this integration, we wouldn't be doing INT" (Jaya)

The product differentiator is the **integration of RWD with market access data** - something not previously capitalized in the market.

### 5. Monday Board Link
[NEEDS CLARIFICATION - Not provided in transcript]

## Viability

### 1. Data Availability

**Data Sources Mentioned:**

a. **Real World Data (RWD):**
   - Medical claims data
   - Prescription claims data (at event level via Singlecare)
   - EHR data
   - Clinical notes (26 high-value therapeutic areas with sample data already processed)
   - Patient-level data (15 years of experience mentioned)

b. **Market Access Data:**
   - Payer plan formulary restrictions
   - Prior authorization (PA) requirements
   - Step therapy requirements
   - PA burden scores
   - Favorable vs. restricted access classifications

c. **Existing DS Services:**
   - **Drug Analog API** (knowledge graph-based, about to go to production) - can identify top K similar drugs in therapy area
   - Peer comparison capabilities
   - RWD evidence base

**Data Integration Status:**
- Current state: RWD and market access data are NOT integrated on existing platforms
- Planned state: Create integrated data model where different sources "talk to each other"
- [INFERRED] Data pipelines need to be built to join these sources at NPI/prescriber level

**[NEEDS CLARIFICATION]:**
- Exact database names, schemas, API endpoints
- Data freshness/latency requirements
- Data quality assessment
- Historical data availability by therapeutic area
- Specific claims data providers beyond Singlecare

### 2. Outbound Dependencies and Integration

**Consumers of this system:**
- Pharmaceutical company sales teams (via what interface? [NEEDS CLARIFICATION])
- Brand/commercial teams
- Medical affairs teams

**Integration Questions [NEED CLARIFICATION]:**
- How will pharma clients access this? (Web UI, API, data export, embedded in CRM?)
- What is the integration timeline with client systems?
- Do pharma clients have bandwidth to integrate by December 18th?
- What authentication/authorization requirements exist?
- Data residency or privacy requirements?

**Known Dependency:**
- Drug Analog API (mentioned as "about to go to production" - timing alignment needed)

### 3. Solution Flow

**High-Level Flow (from transcript):**

```
[Pharma Client Input: Drug/Brand + Therapeutic Area]
           ↓
[Drug Analog API] → Identify similar drugs in market
           ↓
[RWD Query] → Find high-impact prescribers of similar drugs
           ↓
[Market Access Data] → Filter by favorable access
           ↓
[Ranking/Segmentation] → Prioritize targets
           ↓
[Output: Ranked NPI list + supporting evidence]
```

**Modules/Use Cases (6 total planned, 3 for Dec 18th):**
1. **High Impact Prescribers** (traditional + specialized NPI targeting)
2. **Brand Launch Excellence** (early adopter identification, adoption tracking)
3. **Competitive Landscape Analysis** (market share, competitor performance)
4. **Payer Win Capitalization** [MENTIONED - Details unclear]
5. **Market Access Pull** [MENTIONED - Details unclear]
6. [UNNAMED 6th module]

**Prototype Status:**
- Sunil has a "working prototype" that was demoed during meeting
- Using "dummy data" currently - needs real data integration

### 4. Other Considerations

**Privacy & Compliance:**
- Working with patient-level data and PHI
- 15 years experience with real world data (team background)
- [NEEDS CLARIFICATION - HIPAA compliance approach, de-identification strategy, data use agreements with pharma clients]

**Partnerships:**
- Singlecare mentioned as prescription data source
- [NEEDS CLARIFICATION - Other data vendor agreements, pharma client pilots]

**Territory/Geography:**
- Clients can upload custom "zip to territory" configuration files
- Enables sales rep territory-specific NPI lists

### 5. Timeline Constraints

**Critical Date: December 18, 2025** - Early Access (EA) release for INT + PBM

**Scope for Dec 18th:**
- "Limited scope" - specifically **3 use cases** (Jaya confirmed)
- NOT the full product
- Goal: "Get something out and rolling" to validate with customers

**Team Concerns about Timeline:**
- Hassan: "I don't think it's real estate friendly" (skeptical about Dec 18th for 3 use cases)
- Discussion of "3 use cases in 2 months" being ambitious

**Phasing:**
- Phase 1: Dec 18th - Core 3 use cases, descriptive analytics
- Phase 2: [TIMELINE UNCLEAR] - Add AI/ML for physician segmentation, prescribing pattern prediction, peer comparisons (Sunil mentioned this)

**[NEEDS CLARIFICATION]:**
- When is Phase 2 expected?
- What is the definition of "done" for Dec 18th? (MVP, beta, production-ready?)
- What happens with the other 3 use cases?

## Feasibility

### 1. Input

**What data will be sent to the DS service:**

**For New Product Launch Use Case (Priority #1):**
- Drug/brand name OR drug characteristics (for new/unlaunched drugs)
- Therapeutic area
- [INFERRED] Geography/territory filters (optional)
- [INFERRED] Time period for analysis

**For Brand Performance Monitoring Use Case:**
- Brand name
- Launch date
- Time window (e.g., "first 6 months post-launch")
- Geography/territory filters
- [INFERRED] Benchmark drugs for comparison

**For Competitive Landscape:**
- Primary drug/brand
- Competitor drug list OR therapy area
- Time period
- Geographic scope

**Custom Configuration Inputs:**
- Zip to territory mapping files (uploaded by pharma clients)
- [NEEDS CLARIFICATION - File formats, upload mechanism]

### 2. Output

**What data will be returned from the DS service:**

**Core NPI/Prescriber Data:**
- NPI (National Provider Identifier)
- Prescriber name
- Specialty
- Facility/practice location
- Geographic distribution (city, state, zip)
- Contact information [NEEDS CLARIFICATION]

**Prescribing Metrics:**
- Total prescriptions (for drug/therapy area)
- Total patients treated
- Prescription volume trends (QoQ growth)
- Decile ranking (top 10%, etc.)
- Market share vs. competitors [FOR COMPETITIVE USE CASE]

**Market Access Indicators:**
- Number of patients with favorable access (no restrictions)
- Number of patients with restricted access (PA, step therapy)
- PA burden score
- Access classification: Excellent / Good / Limited / Restricted
- % of patients by access tier

**Adoption Segmentation (for Brand Launch use case):**
- Early adopters (first 30 days)
- Mainstream adopters (30-60 days)
- Laggards (60+ days)
- Time to first prescription (from approval/launch)
- Time to peak adoption (plateau point)

**Supporting Evidence (Phase 2 - AI/ML features):**
- Peer comparison: "Similar prescribers write to 40% of patients, you write to 20%"
- RWD evidence: "Positive patient outcomes from this drug" [DETAILS UNCLEAR]
- Prescribing pattern predictions
- Potential/propensity scores [INFERRED]

**Deliverable Format:**
- [NEEDS CLARIFICATION - Is this a UI, API response, CSV export, dashboard?]
- Prototype suggests dashboard/UI exists
- Territory-specific exports mentioned

**[CRITICAL GAP - NO SPECIFIC EXAMPLES PROVIDED]:**
The transcript does not include 20+ question/answer examples for scope validation. This is a significant gap for a complex analytical product.

### 3. Model Quality Metrics and Targets

**[MAJOR GAP - NOT DISCUSSED IN TRANSCRIPT]**

The transcript does not specify:
- Precision/recall targets for NPI recommendations
- Ranking quality metrics (NDCG, MRR, etc.)
- Drug similarity thresholds (for analog API)
- Segmentation accuracy for early adopter classification
- False positive/negative tolerance

**[INFERRED REQUIREMENTS]:**
- Drug Analog API must return therapeutically relevant similar drugs
- NPI rankings should correlate with actual prescription uplift (15-20% target mentioned)
- Access classification must align with actual payer policies

**DATA SCIENCE WORK NEEDED:**
Based on transcript analysis, the following DS capabilities are required:

1. **Ranking/Recommendation System** (Priority 1)
   - Rank NPIs by prescription potential for a drug/therapy area
   - Combine multiple signals: volume, growth trends, access favorability
   - May use existing Drug Analog API for new launches

2. **Segmentation/Classification** (Phase 2)
   - Classify prescribers: Early Adopter / Mainstream / Laggard
   - Classify access level: Excellent / Good / Limited / Restricted
   - Territory/geography clustering

3. **Time Series Analysis**
   - Track adoption curves over time
   - Calculate time-to-first-prescription
   - Identify plateau points

4. **Drug Similarity** (Leveraging existing capability)
   - Knowledge graph-based drug analog matching
   - "Top K similar drugs" API already built

5. **Peer Comparison** (Phase 2 - mentioned but not required for Dec 18)
   - Find similar prescribers by patient characteristics
   - Comparative prescribing metrics

6. **Prediction** (Phase 2 - "AI/ML stuff")
   - Prescribing propensity scoring
   - Potential uplift estimation

**Hassan's Key Concern:**
Emphasized the difference between "presenting current facts" vs. "predicting future changes" - the latter is much more valuable but harder. Phase 1 appears to focus on descriptive analytics, Phase 2 on predictive.

### 4. Other Performance Metrics

**[NEEDS CLARIFICATION - Not specified in transcript]:**
- Latency requirements (e.g., query response time)
- Throughput (queries per second, concurrent users)
- Data freshness (how recent must the data be?)
- Uptime/availability SLAs

### 5. Deliverable Format

**[PARTIALLY SPECIFIED]:**
- Prototype UI exists (Sunil demoed it)
- Configurable file upload capability (zip-to-territory mapping)
- [NEEDS CLARIFICATION - Is this delivered as SaaS, API, on-premise, embedded?]
- [NEEDS CLARIFICATION - How do pharma clients access it?]

### 6. Estimated Infrastructure and Compute Requirements

**[NOT DISCUSSED IN TRANSCRIPT - MAJOR GAP]**

**[INFERRED NEEDS]:**
- Database to store integrated RWD + market access data
- API layer to serve Drug Analog service
- Compute for large-scale data joins (15 years of patient data × millions of NPIs)
- Storage for claims data (event-level prescription data is large)
- UI hosting infrastructure

### 7. Estimated Team Member Requirements

**Current Team (from transcript):**
- Jaya Kumawat (Product Manager, 90 days at Nostella)
- Sunil Rout (Technical Lead, 5 months at Nostella, 15 years RWD experience)
- Hassan Malik (SVP Data Science & AI - advisory/stakeholder role)
- Jeremy Miller (Data Science PM - oversight/collaboration role)
- [NEEDS CLARIFICATION - How many data scientists, ML engineers, data engineers, frontend/backend devs?]

**Timeline Concerns:**
- Hassan expressed doubt about "3 use cases in 2 months" with current team
- [NEEDS CLARIFICATION - Does DS team need to staff additional resources?]

## Usability

### 1. End User Persona

**Primary Persona: Pharmaceutical Sales Representative**
- Works for biopharma/pharma companies
- Responsible for promoting specific drug brands to physicians
- Has assigned territory (geography-based)
- Needs to maximize prescriptions in their territory
- Currently uses manual/reactive targeting methods
- May lack visibility into payer restrictions affecting their targets

**Secondary Persona: Brand Team / Commercial Team**
- Strategic oversight of brand performance
- Needs market intelligence and competitive insights
- Plans launch strategies for new products
- Monitors post-launch adoption and ROI

**Tertiary Persona: Medical Affairs**
- Works with brand teams on clinical strategy
- Needs evidence-based targeting rationale
- Focuses on appropriate prescribing (efficacy + access)

### 2. User Experience Requirements

**[PARTIALLY INFERRED FROM PROTOTYPE DISCUSSION]:**

**Must-Have UX Elements:**
- Search/filter by drug, brand, therapeutic area, geography
- NPI list with sortable columns (volume, growth, access level)
- Visual dashboards showing:
  - Prescription volume statistics
  - Geographic distributions (maps?)
  - Adoption curves over time
  - Access tier breakdowns
- Export functionality for sales rep lists
- File upload for territory configuration

**Evidence for ML Outputs:**
- Peer comparison data ("similar prescribers perform at X%")
- RWD evidence for clinical outcomes
- Justification for NPI rankings [NEEDS CLARIFICATION ON SPECIFICS]

**Ability to Fail Gracefully:**
- [NEEDS CLARIFICATION - Not discussed]
- [INFERRED] Should handle cases where:
  - No similar drugs exist for analog matching
  - Insufficient data for a therapy area
  - New drugs with no market history

**Phase 2 Enhancements (mentioned for "next year"):**
- AI/ML-driven physician segmentation
- Predictive propensity scores
- Advanced peer benchmarking

# Ways of Working

## Communication Channels

### 1. Working Team

**a. Teams Channel (preferred):**
[NEEDS CLARIFICATION - Not specified]

**b. Email List:**
[NEEDS CLARIFICATION - Not specified]

**c. Meeting Cadence:**
- This was an initial 30-minute discovery meeting
- Jeremy mentioned scheduling follow-up: "let's take a look at the calendar and pick a time tomorrow"
- [NEEDS CLARIFICATION - Regular standup/sync schedule not defined]

**Action Items from Transcript:**
- Jaya/Sunil to share:
  - Deck presented in meeting
  - PRD that Sunil has drafted
- Jeremy to share with Jaya/Sunil:
  - Clinical notes therapeutic area list (26 TAs)
  - UI walkthrough for clinical summarization work
  - Data strategy overview

### 2. Leadership Stakeholder Updates

**Stakeholders:**
- Sameer Seraj (Jaya's manager, driving Dec 18th deadline)
- Chris Caneta (product strategy has been socialized with him)

**a. Update Method:**
[NEEDS CLARIFICATION]

**b. Update Frequency:**
[NEEDS CLARIFICATION]

# Assumptions

1. **Drug Analog API will be production-ready in time for Dec 18th launch** - Hassan mentioned it's "about to go to production"

2. **RWD and Market Access data can be integrated at NPI level** - Implied throughout but technical feasibility not validated

3. **26 therapeutic areas with clinical notes are sufficient for Phase 1** - May need validation against pharma client priorities

4. **Pharma clients will provide territory mapping files** - Assumes willingness and capability to upload custom configurations

5. **"Dummy data" in prototype will be replaced with real data** - Sunil mentioned current prototype uses dummy data

6. **December 18th is a hard deadline driven by Sameer** - Jaya emphasized this date multiple times

7. **Phase 1 can deliver value with descriptive analytics only** - Phase 2 will add predictive ML, but Phase 1 is useful without it

8. **Sales reps/brand teams will adopt a new tool** - No discussion of change management or user adoption strategy

9. **3 use cases are sufficient for initial launch** - Prioritized from 6 total planned modules

10. **Existing claims/RWD infrastructure can scale to this use case** - No discussion of performance testing or load requirements

# Milestones

|Milestone|Owner|Deadline|Status|Success Criteria|Deliverable|
|-|-|-|-|-|-|
|Discovery & Alignment|Jaya/Jeremy/Hassan|Oct 23, 2025|In Progress|Stakeholder agreement on scope, DS team understands requirements|This PRD, shared deck, technical PRD from Sunil|
|Data Integration POC|Sunil + [DS Engineers TBD]|[NEEDS CLARIFICATION]|Not Started|RWD + Market Access data joined at NPI level, sample queries working|Integrated data model, sample API responses|
|Drug Analog API Production|Hassan's team|[~Nov 2025?]|In Progress|API returns top K similar drugs with acceptable accuracy|Production API endpoint, documentation|
|Use Case 1: New Product Launch Targeting|Sunil + [DS Team TBD]|Dec 18, 2025|Not Started|Pharma client can input drug, get ranked NPI list with access data|Working module in production|
|Use Case 2: Brand Launch Excellence|Sunil + [DS Team TBD]|Dec 18, 2025|Not Started|Adoption curves, early adopter segmentation visible for launched brands|Working module in production|
|Use Case 3: Competitive Landscape|Sunil + [DS Team TBD]|Dec 18, 2025|Not Started|Market share and competitor analytics available|Working module in production|
|Early Access Release|Jaya/Sunil|Dec 18, 2025|Not Started|3 use cases live, initial pharma clients onboarded|Production system, client training|
|Phase 2: AI/ML Enhancements|[TBD]|[2026?]|Not Started|Predictive segmentation, peer comparison, propensity scoring added|Enhanced modules with ML capabilities|

# Open Questions for Stakeholders

## Critical Gaps (Must Resolve Before Development)

1. **Data Access & Integration:**
   - What are the exact data sources (database names, schemas, API endpoints)?
   - Do we have legal/contractual rights to integrate and sell this combined dataset?
   - What is the data refresh cadence requirement?
   - How will we handle data quality issues or missing data?

2. **Model Performance Requirements:**
   - What accuracy/precision is acceptable for NPI rankings?
   - How will we validate that recommendations actually drive 15-20% uplift?
   - What is the success criteria for Drug Analog API similarity?

3. **Deliverable Format & Integration:**
   - How will pharma clients access this system? (UI, API, data export, CRM integration?)
   - What authentication/authorization is required?
   - Are there data residency or compliance requirements?
   - What is the onboarding process for new pharma clients?

4. **Scope Clarification:**
   - Which 3 use cases are prioritized for Dec 18? (Transcript suggests #1 New Launch is highest priority, but need confirmation)
   - What is the MVP definition for each use case?
   - What functionality is explicitly OUT of scope for Phase 1?

5. **Resource & Timeline:**
   - What DS resources (data scientists, MLE, data engineers) are allocated to this?
   - Is Dec 18 deadline negotiable given Hassan's concerns?
   - What is the Phase 2 timeline and budget?

## Important Clarifications (Should Resolve Soon)

6. **User Experience:**
   - Can we see the current prototype Sunil demoed?
   - What are the specific user workflows for each persona?
   - How will sales reps export and use the NPI lists?

7. **Competitive Differentiation:**
   - What do competitors offer in this space?
   - What is our unique value proposition beyond "integration"?
   - Why hasn't this integration been done before?

8. **Business Metrics:**
   - What are the specific KPIs and KBQs mentioned in Jaya's slides?
   - What is the expected revenue/ROI from this product?
   - How many pharma clients are in the pipeline for Dec 18th launch?

9. **Technical Architecture:**
   - What infrastructure will host this (cloud, on-prem, hybrid)?
   - What are latency, throughput, and availability requirements?
   - How will we scale to support multiple pharma clients?

10. **Privacy & Compliance:**
    - What is the HIPAA compliance strategy?
    - How is PHI de-identified or handled?
    - What data use agreements are needed with pharma clients?

## Nice-to-Know (Can Resolve Later)

11. **Phase 2 AI/ML Features:**
    - What specific predictive models are envisioned?
    - What training data exists for propensity modeling?
    - What is the success criteria for peer comparison accuracy?

12. **Use Cases 4-6:**
    - What are the details of "Payer Win Capitalization"?
    - What is "Market Access Pull" module?
    - What is the 6th unnamed module?

13. **Change Management:**
    - How will pharma sales teams be trained on this tool?
    - What is the adoption strategy?
    - Are there incentives for sales reps to use this vs. current methods?

---

## Summary

**Confidence Level: MEDIUM**

**What We Know Well:**
- High-level business problem and user personas
- Three priority use cases (new launch targeting, brand performance, competitive analysis)
- Data sources conceptually (RWD + market access)
- Aggressive timeline (Dec 18) for limited scope release
- Key stakeholders and team members

**Major Gaps:**
- Technical specifications (data schemas, API contracts, performance requirements)
- Model quality metrics and validation approach
- Detailed user workflows and UX requirements
- Resource allocation and capacity planning
- Infrastructure and deployment strategy
- Specific examples of inputs/outputs for each use case
- Business metrics and ROI projections

**Recommended Next Steps:**
1. Schedule follow-up technical deep-dive with Sunil to review prototype and data architecture
2. Define MVP scope precisely for each of the 3 use cases
3. Validate Dec 18 timeline feasibility with DS engineering team
4. Document data integration requirements and dependencies
5. Establish success metrics and validation plan
6. Create detailed project plan with milestones and resource allocation

**Risk Assessment:**
- **HIGH RISK:** Aggressive timeline (2 months for 3 complex use cases)
- **MEDIUM RISK:** Data integration complexity (multiple sources never integrated before)
- **MEDIUM RISK:** Dependency on Drug Analog API production readiness
- **LOW-MEDIUM RISK:** Unclear resource allocation and team capacity
