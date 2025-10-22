# Landscape AI-Generated Insights Data Science Project

This PRD is a living document. It is perfectly acceptable to update sections as more information becomes available or as project requirements evolve. The purpose of this guide is to ensure a smooth collaboration among all teams, reduce misunderstandings, and support data-driven decision-making in our data science projects.

[Data Science Jira Guidelines](https://evaluateltd.atlassian.net/wiki/spaces/DS/pages/4030595123/Jira+Guidelines)

Items should be added or removed as needed. The Template represents what we expect to need to define most of the time, but there will inevitably be some bespoke elements in some projects.

|Item|Value|
|-|-|
|status|Defining|
|Product Management Sponsor|Vicki Tomich|
|Data Science PM|[NEEDS CLARIFICATION]|
|Data Science Tech Lead|Jeremy Miller|
|Other Team Members and Roles|UI/UX for insight display integration, QC team for profile validation, Landscape frontend engineering team|
|Leadership Stakeholder(s)|Liz (mentioned as enthusiastic) [NEEDS CLARIFICATION - full stakeholder list]|
|Objective|Add AI-generated insights throughout Landscape experience and automate payer profile document generation to improve competitive positioning and operational efficiency|
|Due Date|Chart insights: Near-term (current epic); Profile automation: 6-8 months [NEEDS CLARIFICATION - specific dates]|
|Key Outcomes|3-4x productivity improvement in profile creation (120/year → 350+ coverage); 60-80% automation of profile effort; competitive advantage vs $20M competitor offering|
|Deliverable|1) Real-time/cached chart insight blurbs for Landscape UI, 2) Quarterly payer profile summaries, 3) Automated 17-page payer profile documents with QC workflow|
|Links|[NEEDS CLARIFICATION - links to Landscape product, competitor analysis, historical profiles, Jira epic]|

# Project Canvas - Risk Assessment

## Value

### 1. Business Problem/Opportunity

**Core Business Challenge:**
Current Landscape product provides raw statistics and hard numbers about payer insured lives data without interpretation. Users must analyze trends and patterns themselves. Additionally, competitor offers a combined landscape + payer profiles service worth $20 million, but MMIT can only manually create 120 profiles per year (limited by human resources) while 350+ payer organizations exist.

**Direct Quote:**
> "The competition that we have has a combination of both of these services. So landscape which I just showed you and this like their profiles and between the both of them it's probably it's like a $20 million business."

**a. Who is the user?**
- **Primary Users:** Account Managers who manage relationships with payers
- **Specializations:** Large account focused, geographic territory focused, channel focused (commercial vs Medicare vs Medicaid)
- **User Needs:** High-level planning and targeting information; understanding "who, what, where" of insured lives; want to know "what's driving trends" not just see numbers

**Example Use Case (from transcript):**
> "Cosmetic therapy → Don't care about Medicare (won't cover) → Focus on commercial payers → Target states with high cosmetic treatment demand (CA, FL, NY)"

**b. What is the problem we want to solve for them?**
- **Problem 1:** Users see data trends but must interpret significance themselves - need contextual insights explaining "what's going on behind the numbers"
- **Problem 2:** Payer profile coverage gap - 350+ organizations but only 120 profiles/year created manually
- **Problem 3:** Competitor has static PDF/PowerPoint profiles that become outdated; opportunity to provide always-current, dynamically generated profiles

**Direct Quote:**
> "Because they are human-based, we can only create like 120 of them in a year because of the resources that we have and there are 350 plus organizations."

### 2. Business or Product Metrics

**Success Metrics:**
- **Productivity:** 3-4x improvement in profile creation capacity (from 120/year to full 350+ coverage with same resources)
- **Automation:** 60-80% of profile creation effort automated
- **Coverage:** 350+ payer organizations profiled (vs current 120)
- **Competitive:** Maintain quality advantage while offering more comprehensive, always-current profiles vs competitor's static documents
- **User Engagement:** [NEEDS CLARIFICATION - baseline metrics for chart interaction, profile usage frequency, time spent analyzing data]
- **Data Freshness:** Quarterly profile updates (vs competitor's annual or slower cadence)

**Direct Quote - Business Value:**
> "I could envision creating a data science service that automates 60, 70, 80% of this in terms of effort. The question is what's it worth?"

### 3. Expected ROI

**Operational Efficiency:**
- 60-80% automation of 17-page profile creation effort
- Same resources can now cover 350+ organizations vs 120
- Quarterly profile updates become feasible vs annual manual refresh
- Free up journalists for higher-value curation and QA work vs. manual creation

**New Product Sales:**
- Competitive advantage: real-time, always-current profiles vs competitor's static documents
- Attack $20M market opportunity with superior product
- [INFERRED] Potential to charge premium for AI-enhanced insights
- Differentiation through dynamic, data-driven profiles that update automatically

**Strategic Value:**
- Differentiation in market access analytics space
- Platform for future AI capabilities across product suite
- Competitive moat through automation capabilities

**Direct Quote - Strategic Funding:**
> "Strong likelihood of getting the funding for it because of like the strategic side like this would definitely give us a competitive edge"

**[NEEDS CLARIFICATION]:**
- Revenue projections from improved competitive positioning
- Customer acquisition targets
- Retention impact metrics
- Pricing model for AI-enhanced features

### 4. Alignment with Product Strategy

**Stated Strategic Alignment:**
- Competitive positioning against $20M competitor offering
- Strategic funding likely due to competitive advantage potential
- Leadership enthusiasm (Liz mentioned as supportive)

**[NEEDS CLARIFICATION]:**
- Explicit connection to company OKRs
- Alignment with broader product strategy
- Priority vs other strategic initiatives
- Multi-year product roadmap integration

### 5. Monday Board Link

[NEEDS CLARIFICATION]

## Viability

### 1. Data Availability

**Currently Available in Landscape:**
- **Payer organizations:** Types, hierarchy, relationships
- **Formulary and plan information:** What they are (not detailed coverage rules)
- **Enrollment numbers by:**
  - Channel (Medicare, Medicaid, Commercial, Exchange)
  - Lives types (dual eligible, low-income subsidy, self-insured, self-funded, fully funded, small group, ASO)
  - Geography (state, county distribution)
- **Historical data:** Trend analysis capability with quarterly snapshots
- **Data refresh:** Every 3 months

**Direct Quote - Data Sufficiency:**
> "All the information that is presented to the user is in one way or another present in the data that feeds the landscape UI."

**Exception Note:**
> "Yeah, and since this is a sample, there are there is a little bit of embellishment there because redeterminations you wouldn't know unless you knew current events."

**Additional Data Sources:**
- Financial data collected by MMIT (from public sources, company websites)
- News and press releases (for executive hires, company updates)
- **Hundreds of historical payer profiles** available as reference/evaluation data
- [INFERRED] Organization basics: HQ location, public/private status, rankings

**Data Characteristics:**
- 99.9% of insights derivable from internal data
- Exception: Current events context (e.g., "Medicaid redeterminations") requires external knowledge
- Rural vs urban inferable from county-level data
- Data completeness: [NEEDS CLARIFICATION]
- Historical depth: [NEEDS CLARIFICATION]

**[NEEDS CLARIFICATION]:**
- Specific data schema and field definitions
- Access patterns and APIs available
- Historical data retention period and completeness
- External data source specifications (which sources, update frequency, access methods, costs)
- Data quality metrics and consistency
- Geographic classification datasets (rural/urban)

### 2. Can the outbound dependencies for integration be cleared?

**Integration Points:**
- **Landscape UI:** Chart hover states for insight blurbs (primary integration)
- **Profile Export:** PDF generation or web page format
- **QC Workflow:** Internal validation tools before publication
- **Widget-wise:** Potential future incorporation mentioned

**[NEEDS CLARIFICATION]:**
- UI/UX team bandwidth and timeline for insight display integration
- API specifications for insight requests and responses
- QC team availability and capacity for profile validation
- Export format requirements and consumers
- Integration testing resources and timeline
- Frontend engineering team capacity
- Data engineering support for caching infrastructure

### 3. Solution Flow

**Component 1: Chart Insight Blurbs**

```
User Action → Filter Selection → Chart Interaction (Hover)
                                        ↓
                        [Check Cache for insight key]
                                ↙            ↘
                        Cache Hit         Cache Miss
                            ↓                  ↓
                    Return Cached      Request to DS Service
                       Insight                 ↓
                                    LLM generates insight
                                    (3-5 second response)
                                            ↓
                                        Cache result
                                        (3-month TTL)
                                            ↓
                                    Return to UI
```

**Implementation Approaches Discussed:**
1. **Real-time generation:** User hovers → DS service → LLM → response (3-5 sec)
2. **Pre-calculation:** Generate all combinations upfront (rejected due to combinatorial explosion)
3. **Hybrid (recommended):** Real-time with caching (30%+ cache hit rate target, 10% minimum)

**Direct Quote - Response Time:**
> "It will take a couple of seconds to populate. Just FYI, it won't be... I would think 3 to 5 seconds would probably be typical."

**Cache Strategy Quote:**
> "In all likelihood someone will hover over that exact same data point with that exact same filter set, probably at some point again in the next three months, hopefully many times"

**Component 2: Payer Profile Document Generation**

```
Quarterly Data Refresh
        ↓
Trigger Profile Generation
        ↓
DS Service Orchestrator
        ↓
┌───────┴───────┬───────────┬──────────┐
↓               ↓           ↓          ↓
Internal       External   Financial   News/
Lives Data     Research   Data        Events
└───────┬───────┴───────────┴──────────┘
        ↓
LLM Document Generation
(Multiple sections: summary, org details,
enrollment, financials, trends, charts)
        ↓
QC Workflow Interface
        ↓
Human Review/Validation
        ↓
Approval Decision
   ↙          ↘
Approve      Needs Changes
   ↓              ↓
Publish    → Feedback Loop
(PDF/Web)    (Refine/Regenerate)
```

**Development Approach:**
- Iterative refinement expected (especially for profiles)
- Not like blurbs where "50 good examples" would be sufficient
- Significant back-and-forth with stakeholders anticipated

**Direct Quote:**
> "This would be a pretty big lift and it's not like a you're gonna get it done in three months. It's probably gonna be more like 6 to 8."

**[NEEDS CLARIFICATION]:**
- Detailed API specifications
- Error handling and fallback behavior
- Scalability requirements (concurrent users)
- Monitoring and alerting requirements
- Cache invalidation logic details
- Streaming capability for perceived performance improvement

### 4. Other Considerations (privacy, partnerships, etc)

**Privacy:**
- Data is aggregated payer information (not individual patient data)
- [NEEDS CLARIFICATION - data classification, compliance requirements, HIPAA implications]

**Quality Control - Critical Requirement:**
- Profile accuracy impacts customer relationships
- Misinformation risk if QC fails
- Human validation required before publication

**Direct Quote - Quality Imperative:**
> "The value proposition is the precision of what's in here, so we could... like some kind of validation. I could envision there being a process where we would like create some of this and then maybe have like a QC process for someone to go in and and validate what we collected and what we want to publish before it actually gets out there."

**Technical Considerations:**
- LLM lacks business-specific context - must channel general knowledge into specific valuable insights
- Need to distinguish what's in data vs. what requires external context
- Historical data state reconstruction difficult for training (especially internet-based sources)

**Partnerships:**
- External data sources for financial information
- News/press release services
- [NEEDS CLARIFICATION - existing vendor relationships, new partnerships needed]

**Brand/Voice:**
- Maintain MMIT professional standards
- Consistency with manually-created profiles
- User trust in AI-generated content
- [NEEDS CLARIFICATION - brand guidelines for AI-generated content]

**[NEEDS CLARIFICATION]:**
- Legal review requirements for published profiles
- Competitive intelligence handling policies
- Data licensing for external sources
- Intellectual property considerations for AI-generated content

### 5. Timeline Constraints

**Near-term (Current Epic):**
- Chart insight blurbs - more immediate/feasible
- Profile summary blurbs - near-term deliverable

**Longer-term (Next Year):**
- Full payer profile automation - 6-8 months estimated

**Strategic Funding Note:**
- Profile automation likely to receive strategic funding due to competitive advantage

**Development Phases:**
- **Phase 1:** Gather 50 examples and define specifications (near-term)
- **Phase 2:** Build and test infrastructure (chart insights)
- **Phase 3:** Profile automation with significant iterative refinement

**[NEEDS CLARIFICATION]:**
- Specific milestone dates and deadlines
- Resource allocation timeline
- Dependencies on other projects/teams
- Beta/pilot program timeline
- Full rollout dates
- Coordination with quarterly data refresh cycles

## Feasibility

### 1. Input: What data will be sent to the data science service?

**For Chart Insight Blurbs:**
- **User-selected filters:**
  - Payer organization(s)
  - Channel type (Medicare, Medicaid, Commercial, Exchange)
  - Geography (state, county)
  - Lives types (dual eligible, LIS, self-insured, self-funded, fully-funded, small group, ASO)
  - Time period
- **Chart data points:**
  - Current enrollment values
  - Historical trend data
  - Percentage changes
  - Comparison periods (YoY, QoQ)
- **Contextual metadata:**
  - Chart type
  - Data dimensions displayed
  - Comparison basis

**For Payer Profile Generation:**
- Payer organization identifier
- Complete enrollment history (all channels, geographies, lives types)
- Organization hierarchy and relationships
- Formulary and plan information
- Financial data (revenue, membership trends)
- News/events data (executive changes, partnerships)
- Organization basics (HQ, public/private status, ranking)
- Historical comparison data

**[NEEDS CLARIFICATION]:**
- Complete data schema with field types and constraints
- Data volume estimates
- API payload specifications
- Maximum context size limitations

### 2. Output: What data will be returned from the data science service?

**Chart Insight Blurbs (Example from transcript):**
> "Centene's total enrolled lives declined by 3.1%, driven primarily by Medicaid redeterminations in Georgia, Ohio and Pennsylvania. Commercial lives remain flat with losses in small group plans offset by ASO growth. Medicare Advantage saw modest gains in Florida and Texas while exchange enrollment rose due to expanded silver tier offerings."

**Output Structure for Blurbs:**
- **Text:** Natural language insight (100-200 words estimated)
- **Metadata:** Generated timestamp, cache key, data sources used
- **Response time:** 3-5 seconds for real-time generation
- [INFERRED] **Confidence score:** May be useful for fallback logic
- [INFERRED] **Structured references:** Data points cited

**Payer Profile Documents - 17-page structure including:**
1. **Executive summary** of payer lives trends
2. **Organization basics** (HQ location, public/private status, rank by medical lives)
3. **Enrollment distribution** (geographic, channel breakdown)
4. **Financial performance** data
5. **Recent news/events** (executive hires, partnerships, deals)
6. **Historical trend analysis** with charts
7. **[NEEDS CLARIFICATION]** - Complete section breakdown

**Output Format Options:**
- **PDF** (traditional format for export)
- **Web page** (dynamic, always current)
- **Internal QC format** (pre-publication review interface)

**[NEEDS CLARIFICATION]:**
- Exact word count limits for blurbs
- Structured metadata requirements
- Chart/visualization specifications for profiles
- Version control requirements
- Multi-language support needs
- Export format technical specifications

### 3. Model Quality Metrics and Targets (Precision, Recall, ROC AUC, etc)

**For Chart Insights:**
- **Accuracy:** Very high required (user-facing, no QC layer)
- **Relevance:** Insights must be contextually appropriate to filtered data
- **Completeness:** Should address key trends visible in data
- **Consistency:** Similar data patterns should yield similar insights
- **Factual Accuracy:** 100% for numerical data cited
- **No Hallucination:** Critical - cannot invent data not present

**Target from Discussion:**
> "When these things are present in the data, we capture 80% of them and of the things that we capture, 95% are correct and error-free"

**Interpretation:**
- **Recall:** 80% - capture 80% of meaningful insights present in data
- **Precision:** 95% - of captured insights, 95% are correct and error-free

**For Payer Profiles:**
- **Data-derived content accuracy:** 95%+ (with QC)
- **Completeness:** 80%+ coverage of expected insights
- **Factual accuracy:** 100% for numerical data
- **QC pass rate target:** [NEEDS CLARIFICATION - what % pass without edits?]
- **Effort reduction:** 60-80% automation (20-40% QC effort)

**[NEEDS CLARIFICATION - Specific Metrics]:**
- How to measure "insight value" vs "just restating data"
- False positive rate tolerance
- User satisfaction thresholds (NPS, CSAT)
- A/B testing success criteria
- Quality rubric for different insight types
- Acceptable error types vs. critical errors

**Evaluation Approach:**
- Gold standard examples from historical profiles
- Subject matter expert validation
- User feedback integration
- Comparison to manually-created profiles
- [NEEDS CLARIFICATION - evaluation frequency, test set size, validation process]

### 4. Other Performance Metrics (latency, throughput, etc)

**Latency:**
- **Chart insights:** 3-5 seconds acceptable (stated in discussion)
- **Profile generation:** [NEEDS CLARIFICATION - likely minutes to hours acceptable given QC process]
- **Cache response time:** <500ms [INFERRED]
- [INFERRED] **Streaming consideration:** Progressive display to improve perceived performance

**Throughput:**
- **Concurrent users:** [NEEDS CLARIFICATION - peak load estimates for Landscape]
- **Profile generation capacity:** 350+ profiles per quarter
- **Cache hit rate:** 30%+ target (10% minimum acceptable)
- **API requests per second:** [NEEDS CLARIFICATION]

**Reliability:**
- **Uptime:** [NEEDS CLARIFICATION - likely 99%+ given user-facing nature]
- **Graceful degradation:** Fallback behavior when insights can't be generated
- **Error rate:** [NEEDS CLARIFICATION - acceptable failure rate]
- **Timeout handling:** [NEEDS CLARIFICATION]

**Scalability:**
- Must handle multiple concurrent insight requests
- Profile generation at scale (350+ organizations)
- Storage for cache and generated profiles (with 3-month retention)
- [NEEDS CLARIFICATION - storage size estimates, scaling plan]

**Cost Metrics:**
- LLM API costs per insight generation
- LLM API costs per profile generation
- Storage costs for caching
- Total infrastructure costs
- [NEEDS CLARIFICATION - budget constraints]

### 5. Deliverable Format (ie API, batch process, etc)

**Chart Insights:**
- **Format:** JSON response via API
- **Integration:** Embedded in Landscape UI hover states
- **Caching:** Redis or similar (3-month TTL aligned with data refresh)
- **Delivery:** Synchronous API response (with streaming option)
- **[NEEDS CLARIFICATION]:**
  - API specification (endpoints, authentication, rate limits)
  - Error response format
  - Retry logic requirements

**Payer Profiles:**
- **Generation:** Batch processing triggered by data refresh or on-demand
- **Format Options:**
  - PDF (traditional export)
  - Web page (dynamic viewing)
  - Internal QC format (pre-publication workflow)
- **Distribution:** [NEEDS CLARIFICATION - download, email, embedded viewer?]
- **Versioning:** Track changes over time [NEEDS CLARIFICATION - version control system]

**Infrastructure Components:**
- API endpoint for insight requests
- Batch processing pipeline for profile generation
- Storage for generated content (cache + profiles)
- QC workflow interface/tools
- Monitoring and logging system

### 6. Estimated Infrastructure and Compute Requirements

**[NEEDS CLARIFICATION - All infrastructure items need DS/Engineering team input]**

**For Chart Insights:**
- **LLM API calls:**
  - [ESTIMATE NEEDED - calls per day based on user activity]
  - [ESTIMATE NEEDED - tokens per call based on context size]
  - [ESTIMATE NEEDED - daily/monthly API costs]
- **Cache storage:**
  - [ESTIMATE NEEDED - size based on # of unique filter combinations]
  - [ESTIMATE NEEDED - Redis or equivalent infrastructure]
- **API hosting:**
  - [ESTIMATE NEEDED - server specs, container requirements]
  - [ESTIMATE NEEDED - auto-scaling parameters]

**For Profile Generation:**
- **Batch processing capacity:** 350+ profiles per quarter
- **LLM API usage:**
  - [ESTIMATE NEEDED - tokens per 17-page profile]
  - [ESTIMATE NEEDED - cost per profile generation]
- **Storage:**
  - Profiles (multiple versions)
  - Source data snapshots
  - Generated charts/visualizations
  - [ESTIMATE NEEDED - total storage requirements]
- **External data fetching:**
  - APIs for financial/news data
  - Rate limits and quotas
  - [ESTIMATE NEEDED - external service costs]

**Cost Considerations:**
- LLM API costs (per token pricing)
- Hosting/compute costs (servers, containers, orchestration)
- Storage costs (cache, profiles, backups)
- External data source subscriptions
- Monitoring and logging infrastructure
- [NEEDS CLARIFICATION - total budget allocation]

**Scaling Considerations:**
- Peak load handling (multiple concurrent requests)
- Geographic distribution (latency optimization)
- Disaster recovery and backup
- Development vs. production environments

### 7. Estimated Team Member Requirements: how many people from each team for how long?

**Phase 1: Chart Insights (Near-term - 2-3 months estimated)**

**Data Science:**
- [NEEDS CLARIFICATION - FTE allocation, duration]
- Prompt engineering and optimization
- Caching strategy implementation
- Quality evaluation and metrics
- **Estimated:** 4-6 person-weeks [INFERRED]

**Data Engineering:**
- [NEEDS CLARIFICATION]
- Caching infrastructure setup
- API development
- Integration with Landscape data sources
- **Estimated:** 2-3 person-weeks [INFERRED]

**Frontend Engineering:**
- [NEEDS CLARIFICATION]
- UI integration for hover states
- API consumption
- Streaming implementation (if applicable)
- **Estimated:** 3-4 person-weeks [INFERRED]

**UI/UX Design:**
- [NEEDS CLARIFICATION]
- Insight display design
- Hover interaction patterns
- Error state design
- **Estimated:** 2 person-weeks [INFERRED]

**Product/QA:**
- [NEEDS CLARIFICATION]
- Requirements validation
- 50 example insights creation
- User testing and feedback
- **Estimated:** 2 person-weeks [INFERRED]

**Phase 2: Profile Automation (6-8 months)**

**Data Science:**
- [NEEDS CLARIFICATION - significant investment expected]
- Document generation pipeline development
- Multi-source data integration
- Quality metrics development
- Iterative refinement with stakeholders
- **Estimated:** 12-16 person-weeks [INFERRED]

**Data Engineering:**
- [NEEDS CLARIFICATION]
- Batch processing infrastructure
- External data integration (financial, news)
- QC workflow tools development
- Export generation (PDF, web)
- **Estimated:** 4-6 person-weeks [INFERRED]

**Frontend Engineering:**
- [NEEDS CLARIFICATION]
- Dynamic profile UI development
- QC interface for reviewers
- Export functionality
- **Estimated:** 8-10 person-weeks [INFERRED]

**Subject Matter Experts (Journalists):**
- [NEEDS CLARIFICATION - critical resource]
- Gold standard profile creation
- Validation and QC of generated profiles
- Feedback on generated content
- Ongoing: QC workflow participation

**Product/Design:**
- [NEEDS CLARIFICATION]
- QC workflow design
- Profile template refinement
- User acceptance testing
- **Estimated:** 4-6 person-weeks [INFERRED]

**Ongoing Maintenance:**
- Monitoring and alerting
- Prompt tuning based on feedback
- Quality metric tracking
- Cache optimization
- [NEEDS CLARIFICATION - ongoing support model]

**Key Dependencies:**
- Journalist availability for QC (critical path item)
- Frontend team capacity alignment
- External data source access
- Infrastructure provisioning timeline

## Usability

### 1. End User Persona: describe who will be using the final product

**Primary Persona: Account Manager - Large Accounts**
- **Role:** Manages relationships with major national payers (e.g., United, Anthem, Centene)
- **Goals:**
  - Understand enrollment trends and drivers across large payer portfolios
  - Identify opportunities for engagement based on formulary changes
  - Prepare for quarterly business reviews with strategic insights
  - Track competitive positioning across multiple payers
- **Pain Points:**
  - Overwhelmed by raw data - need synthesis and interpretation
  - Limited time to create custom analyses
  - Static profiles become outdated quickly
  - Need to understand "why" behind trends, not just "what"
- **Technical Sophistication:** Business user, not data analyst
- **Usage Pattern:** Regular Landscape user, references profiles during payer meetings
- **Value from AI Insights:** Quickly understand trend drivers without manual analysis

**Secondary Persona: Account Manager - Geographic Territory**
- **Role:** Manages payers within specific states/regions
- **Goals:**
  - Track state-specific enrollment trends (especially Medicaid)
  - Understand local market dynamics
  - Target appropriate payers for product launches in territory
  - Monitor regional policy impacts
- **Pain Points:**
  - Need to filter national data to regional view
  - Local news and changes often missed in national data
  - Time-consuming to track multiple small regional payers
- **Usage Pattern:** Frequent filtering by geography, channel-specific analysis
- **Value from AI Insights:** Geographic-specific trend explanations and local context

**Tertiary Persona: Account Manager - Channel Focused**

**Example from transcript:** Cosmetic therapy use case
- **Role:** Specializes in specific channels (Commercial vs Medicare vs Medicaid) based on therapeutic area
- **Goals:**
  - Identify which payers/channels are relevant for specific therapeutic areas
  - Track channel-specific trends and policy changes
  - Focus effort on addressable market segments
- **Pain Points:**
  - Irrelevant data noise (e.g., Medicare data for cosmetic products)
  - Need to quickly identify addressable market
  - Channel-specific policy understanding
- **Usage Pattern:** Heavy channel filtering, state-level analysis for commercial
- **Value from AI Insights:** Channel-specific trend interpretation and opportunity identification

**Use Case Example from Transcript:**
> "Cosmetic therapy → Don't care about Medicare (won't cover) → Focus on commercial payers → Target states with high cosmetic treatment demand (CA, FL, NY)"

**[NEEDS CLARIFICATION]:**
- Persona validation with actual users
- Usage frequency data (daily, weekly, monthly)
- Most valuable use cases by persona
- Feature prioritization by persona
- Secondary users (leadership, analytics teams?)

### 2. User Experience Requirements: explain how will end users interact with the data science service outputs

**For Chart Insights:**

**Display Requirements:**
- **Trigger:** Hover state or info icon on charts
- **Positioning:** Non-blocking popover/tooltip near data point
- **Responsiveness:** Updates based on user filter selections
- **Readability:** Natural language, business terminology (not technical jargon)
- **Length:** Concise enough to digest quickly (100-200 words estimated)
- **Context:** Explicitly tied to visible data, answers "why" not just "what"

**Content Requirements:**
- Insights should reference specific data points visible in chart
- Geographic, channel, or lives-type specificity when relevant
- Trend direction with magnitude (e.g., "3.1% decline")
- Causal language when appropriate ("driven by," "offset by," "due to")
- Distinguish between data-derived insights vs. external context

**Evidence for ML outputs:**
- Insights cite specific data present in visualization
- Quantitative support for qualitative statements
- Clear connection between assertion and data
- [NEEDS CLARIFICATION] - Explicit data citations or implicit through context?

**Ability to fail gracefully:**
- **If insight cannot be generated:** [NEEDS CLARIFICATION]
  - Option 1: Show generic message ("Insight generation unavailable")
  - Option 2: Show no insight (data only)
  - Option 3: Show partial insight with disclaimer
  - Option 4: Show cached older insight with timestamp
- **Error messaging:** User-friendly, non-technical
- **Degraded performance:** Fallback to cached or no insight rather than blocking
- **Loading states:** Clear indication that insight is generating (3-5 sec)

**For Payer Profiles:**

**Display Requirements:**
- **Format:** Professional document suitable for customer-facing use
- **Navigation:** Clear section structure (TOC, page numbers for PDF)
- **Visualizations:** Charts and tables integrated with narrative
- **Branding:** MMIT brand standards maintained
- **Accessibility:** [NEEDS CLARIFICATION - WCAG standards?]
- **Responsiveness:** [NEEDS CLARIFICATION - mobile/tablet viewing?]

**Dynamic Updates:**
- Profiles update automatically with quarterly data refreshes
- Version history tracking [NEEDS CLARIFICATION - how visible to users?]
- Change highlighting [NEEDS CLARIFICATION - show what changed quarter-to-quarter?]

**QC Workflow Requirements:**

**Interface for Reviewers:**
- Tool for journalists to validate generated content
- Section-by-section review capability
- Edit/refinement capability (inline or separate interface?)
- Approval workflow (submit, review, approve/reject)
- Feedback capture for model improvement
- Comparison to previous manual profiles

**Functionality:**
- Highlight AI-generated sections vs. data tables
- Flag low-confidence sections for extra scrutiny
- Track time spent in QC vs. manual creation baseline
- Support collaborative review if multiple reviewers

**Efficiency Target:**
- Should be faster than creating from scratch (60-80% time savings target)
- Should maintain or improve quality vs. manual

**[NEEDS CLARIFICATION]:**
- Detailed UI/UX mockups for insight display
- QC tool specifications and workflow design
- User testing plan and success criteria
- Accessibility requirements (WCAG level)
- Mobile/responsive design needs
- Internationalization requirements
- User feedback mechanism design (flag incorrect insights)

# Ways of Working

## Communication Channels

### 1. Working Team:

**a. Teams Channel (preferred):**
[NEEDS CLARIFICATION - create dedicated channel for project]

**b. Email List:**
[NEEDS CLARIFICATION]

**c. Meeting Cadence:**
- **Sprint planning:** [NEEDS CLARIFICATION]
- **Development sync:** [NEEDS CLARIFICATION - likely weekly given iterative nature mentioned]
- **Stakeholder reviews:** [NEEDS CLARIFICATION - probably bi-weekly or monthly]
- **Note from discussion:** "Significant back-and-forth expected" especially for profile automation

**Key Stakeholders to Include:**
- Vicki Tomich (Product Lead)
- Jeremy Miller (DS Lead)
- [NEEDS CLARIFICATION - Frontend Engineering Lead]
- [NEEDS CLARIFICATION - Journalist/QC Lead]
- [NEEDS CLARIFICATION - Design Lead]
- Liz (Executive Sponsor)

### 2. Leadership Stakeholder Updates (if not already represented by the Product, or otherwise needed):

**a. Update Method:**
[NEEDS CLARIFICATION - exec reports, demos, dashboard?]

**b. Update Frequency:**
[NEEDS CLARIFICATION - monthly, quarterly?]

**Strategic Context:**
- Profile automation likely to receive strategic funding due to competitive advantage
- Leadership visibility expected given competitive positioning implications

# Assumptions

1. **Data Sufficiency:** 99.9% of insights can be derived from existing Landscape data, with rare exceptions for current events context

2. **User Acceptance:** 3-5 second response time for chart insights is acceptable to users (no streaming required initially)

3. **Cache Effectiveness:** Minimum 10% cache hit rate achievable, target 30%+ based on user behavior patterns

4. **Quality Bar:** Human QC can effectively validate AI-generated profiles in 20-40% of the time required to create from scratch (60-80% effort reduction)

5. **LLM Capability:** Current generation LLMs (GPT-4, Claude, etc.) can produce business-quality insights and profile content with appropriate prompt engineering

6. **Historical Profiles:** Hundreds of existing profiles provide sufficient training/evaluation data for quality benchmarking

7. **Competitive Advantage:** Dynamic, always-current profiles will be differentiated vs competitor's static documents and justify strategic investment

8. **Incremental Delivery:** Chart insights can be delivered independently of profile automation (Phase 1 before Phase 2)

9. **Resource Availability:** UI/UX and QC teams have capacity to support integration and validation workflows within stated timelines

10. **External Data Access:** Financial and news data sources will remain accessible, reliable, and within budget constraints

11. **User Trust:** Users will trust AI-generated insights if they are accurate and contextually relevant (no special trust-building required beyond quality)

12. **Technical Feasibility:** Real-time + caching approach is technically feasible within 3-5 second response time constraint

**[KEY ASSUMPTIONS TO VALIDATE]:**
- Cache hit rate assumptions (10-30%) based on actual user behavior data
- 60-80% automation rate for profiles is achievable
- Scope of Phase 1 MVP vs Phase 2
- Resource allocation and team availability
- External data source costs and accessibility
- User acceptance of AI-generated content

# Milestones

|Milestone|Owner|Deadline|Status|Success Criteria|Deliverable|
|-|-|-|-|-|-|
|**Discovery & Planning**|Vicki Tomich|[NEEDS CLARIFICATION]|In Progress|PRD approved, technical approach defined, resource commitments secured, 50 example insights gathered|Approved PRD, technical design doc, project plan, gold standard examples|
|**POC: Chart Insights**|Jeremy Miller|[NEEDS CLARIFICATION]|Pending|Generate quality insights for 50 example chart states; achieve 80% expert approval; validate <5 sec response time|Working prototype with 50 validated examples, performance benchmarks|
|**Infrastructure: Caching & API**|Engineering Lead|[NEEDS CLARIFICATION]|Pending|Cache infrastructure operational; API endpoints functional; integration tested|Production-ready cache system, API documentation, integration tests|
|**Phase 1: Chart Insights MVP**|Cross-functional|[NEEDS CLARIFICATION - Current Epic]|Pending|Insights available for top 10 payer organizations; cache hit rate >10%; user satisfaction >70%; no critical errors|Production API integrated into Landscape UI with caching, monitoring dashboard|
|**Phase 1: User Validation**|Vicki Tomich|[NEEDS CLARIFICATION]|Pending|A/B test shows positive engagement lift; user feedback indicates value; no quality concerns|A/B test results, user feedback summary, decision to proceed|
|**Phase 1: Full Rollout**|Cross-functional|[NEEDS CLARIFICATION]|Pending|100% of Landscape users have access; cache hit rate >20%; quality metrics stable|Full production deployment, rollout plan executed|
|**Phase 2: Profile POC**|Jeremy Miller|[NEEDS CLARIFICATION]|Pending|Generate 5 complete profiles; 80% content completeness; pass expert QC with minor edits only; demonstrate 60%+ effort reduction|5 QC-approved profiles, effort reduction metrics, feasibility validation|
|**Phase 2: QC Workflow**|Product + Engineering|[NEEDS CLARIFICATION]|Pending|QC interface functional; workflow tested with journalists; feedback loop operational|QC tool, workflow documentation, journalist training|
|**Phase 2: Section-by-Section Build**|Jeremy Miller|[NEEDS CLARIFICATION - 6-8 months estimate]|Pending|All 17-page sections can be generated; quality targets met per section; integration validated|Complete profile generation pipeline, section quality benchmarks|
|**Phase 2: Scale to 350+ Orgs**|Cross-functional|[NEEDS CLARIFICATION]|Pending|Profiles generated for all 350+ organizations; QC effort 60-80% reduced vs manual; quality parity with manual profiles; stakeholder confidence in publication|Production batch process, 350+ validated profiles, effort metrics|
|**Optimization & Monitoring**|Engineering + DS|[NEEDS CLARIFICATION]|Pending|Cache hit rate >30%; profile generation cost <$X per profile; user adoption >80%; quality SLAs met|Optimized production system, monitoring dashboards, cost analysis, quality reports|

# Open Questions for Stakeholders

## Strategic & Scope

1. **MVP Definition:** What is the minimum viable scope for Phase 1 chart insights? Which payers, channels, or chart types should be prioritized first?

2. **Success Definition:** How will we measure success beyond operational efficiency? Customer acquisition? Retention? Competitive win rate? NPS improvement?

3. **Phasing Strategy:** Should we deliver chart insights first, validate with users, then proceed to profiles? Or develop in parallel? What are the gates between phases?

4. **Competitive Intelligence:** What specific capabilities from competitor's $20M offering should we match or exceed? What differentiation is most valuable?

5. **User Prioritization:** Which account manager personas should we optimize for first? Large account vs. geographic vs. channel-focused?

6. **Funding Approval:** What is the approval process for Phase 2 strategic funding? What milestones from Phase 1 are needed to secure it?

## Technical & Data

7. **Insight Taxonomy:** What is the complete list of insight types needed? (trend direction, magnitude, drivers, geographic patterns, channel mix changes, offsetting factors, etc.)

8. **Data Schema:** Can we get detailed schema documentation for Landscape data sources? API specifications?

9. **External Data:** Which specific financial and news data sources should be integrated? What are access patterns, costs, and licensing requirements?

10. **Historical Context:** How far back should trend analysis go? What defines "meaningful" change vs. noise? What baseline comparisons are expected?

11. **Edge Cases:** What should happen when data is sparse, missing, or ambiguous? What's the fallback behavior? Show partial insight? Show nothing?

12. **Current Events:** How should we handle external context (e.g., "Medicaid redeterminations") that isn't in internal data? What sources? How to keep current?

## Quality & Validation

13. **Gold Standards:** Who will create the 50+ example "good insights" needed for evaluation and prompt engineering?

14. **QC Process:** What is the exact workflow for profile QC? Who reviews (specific journalists)? What tools do they need? What's the approval process? How many reviewers per profile?

15. **Quality Metrics:** What quantitative thresholds should we set for accuracy, completeness, and relevance? What is acceptable vs. excellent?

16. **User Testing:** How will we validate that insights are valuable (not just restating data)? What's the testing plan? Sample size? Duration?

17. **Feedback Loop:** How do we capture and incorporate user feedback to improve insight quality over time? In-product feedback mechanism?

18. **Error Classification:** What types of errors are acceptable vs. critical? Factual errors vs. tone issues vs. missing context?

## Resource & Timeline

19. **Team Capacity:** What is realistic DS, Data Engineering, Frontend Engineering, and UX capacity for next 3, 6, and 12 months?

20. **SME Availability:** Who can serve as domain experts for validation (journalist names)? How much time can they commit per week? Is this in their goals/OKRs?

21. **Strategic Funding:** Is profile automation pre-approved for strategic funding or does it need further justification? What's the decision timeline?

22. **Dependencies:** What other projects or initiatives could block or delay this work? Landscape roadmap conflicts? Infrastructure projects?

23. **Milestones:** What are the specific dates for key milestones? When is current epic expected to close? When should Phase 2 start?

## User Experience

24. **Latency Tolerance:** Is 3-5 seconds actually acceptable to users or should we target faster with pre-calculation or streaming? Do we have user research on this?

25. **Insight Length:** What's the ideal length for chart insights? Too short = not helpful; too long = won't read. Do we have user preferences?

26. **Profile Format:** Should profiles be PDF, web pages, or both? What's the priority? Export requirements?

27. **Graceful Failure:** What should users see if an insight can't be generated? Generic message? Nothing? Partial insight with disclaimer?

28. **Accessibility:** What are the accessibility requirements? WCAG 2.1 Level AA? Mobile responsive? Screen reader support?

29. **User Feedback:** How should users flag incorrect insights? In-product thumbs up/down? Report button? What happens with feedback?

## Business Model & Go-to-Market

30. **Monetization:** Will AI insights be available to all Landscape customers or a premium tier? Pricing impact?

31. **Competitive Positioning:** How will we market "dynamic AI-generated profiles" vs competitor's static documents? What's the messaging?

32. **Customer Education:** What communication/training will customers need about AI-generated content? Documentation? Webinars?

33. **Rollout Strategy:** Phased rollout by customer tier? Beta program? Full launch? Communication plan?

---

## Summary of Confidence Levels

### High Confidence Areas (Explicitly Discussed):
✅ Business problem and opportunity ($20M competitive market)
✅ Current limitations (120 profiles/year, 350+ orgs exist)
✅ Primary use cases (chart insights, profile automation)
✅ Timeline estimates (6-8 months for profiles)
✅ Quality requirements (precision critical, QC needed)
✅ User personas (account managers with different focus areas)
✅ Data availability (99.9% from internal Landscape data)
✅ Performance expectations (3-5 seconds acceptable)
✅ Automation targets (60-80% effort reduction)

### Medium Confidence Areas (Inferred from Discussion):
⚠️ Technical approach (real-time + caching recommended but not decided)
⚠️ Infrastructure requirements (Redis caching, API architecture)
⚠️ Evaluation metrics (80% recall, 95% precision mentioned for "fuzzy" insights)
⚠️ Development phases (Phase 1: insights, Phase 2: profiles)
⚠️ Resource estimates (person-weeks inferred from timeline)
⚠️ QC workflow (validation interface needed, journalists involved)

### Low Confidence / Needs Clarification:
❓ Specific team members and capacity commitments
❓ Detailed milestones and dates
❓ External data sources (specific providers, costs)
❓ Complete data schema and API specifications
❓ Quality evaluation framework and gold standards
❓ User experience specifications (mockups, error handling)
❓ Accessibility and internationalization requirements
❓ Monitoring and success metrics details
❓ Budget and infrastructure cost estimates
❓ Go-to-market and rollout strategy

### Critical Gaps Requiring Immediate Attention:
🔴 **50 example insights needed** - blocking for Phase 1 development
🔴 **Journalist QC capacity** - critical dependency for Phase 2
🔴 **Frontend engineering capacity** - needed for UI integration
🔴 **External data source access** - affects profile scope and cost
🔴 **Quality evaluation rubric** - needed to measure success
🔴 **Specific milestone dates** - needed for project planning

---

## Notes from Transcript

**Key Quote - Business Value:**
> "The competition that we have has a combination of both of these services. So landscape which I just showed you and this like their profiles and between the both of them it's probably it's like a $20 million business."

**Key Quote - Current Limitation:**
> "Because they are human-based, we can only create like 120 of them in a year because of the resources that we have and there are 350 plus organizations."

**Key Quote - Desired Outcome:**
> "What we want to do in landscape is we want to have like deeper insights here. So it's not just like hard numbers and statistics, it's like what's going on behind the numbers."

**Key Quote - Timeline:**
> "I my my thoughts on this is that this would be a pretty big lift and it's not like a you're gonna get it done in three months. It's probably gonna be more like 6 to 8."

**Key Quote - Quality Requirements:**
> "The value proposition is the precision of what's in here, so we could. Yeah, like some kind of validation. I could envision there being a process where we would like create some of this and then maybe have like a QC process for someone to go in and and validate what we collected and what we want to publish before it actually gets out there."

**Key Quote - Automation Potential:**
> "I could envision creating a data science service that automates 60, 70, 80% of this in terms of effort. The question is what's it worth?"

**Key Quote - Data Sufficiency:**
> "All the information that is presented to the user is in one way or another present in the data that feeds the landscape UI."

**Key Quote - Strategic Funding:**
> "Strong likelihood of getting the funding for it because of like the strategic side like this would definitely give us a competitive edge"

**Key Quote - Response Time:**
> "It will take a couple of seconds to populate. Just FYI, it won't be... I would think 3 to 5 seconds would probably be typical."

**Key Quote - Cache Rationale:**
> "In all likelihood someone will hover over that exact same data point with that exact same filter set, probably at some point again in the next three months, hopefully many times"
