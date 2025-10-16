# PRD Review: Premium Tier Churn Prediction Model

**Reviewer:** Claude (AI PM Assistant)
**Date:** 2024-01-15
**PRD Version:** Draft (Initial)

## Overall Assessment

**Quality Rating:** Good

**Recommendation:** Approve with minor changes

**Summary:** This is a well-structured PRD with clear problem definition, realistic scope, and thoughtful DS-specific requirements. The document does an excellent job capturing stakeholder discussions and flagging uncertainties with "[NEEDS CLARIFICATION]" tags. The 25 open questions demonstrate thoroughness in identifying gaps. Main improvements needed: clarifying CS capacity constraints upfront, adding more specificity to intervention strategies, and refining experiment design details.

---

## Strengths

1. **Excellent problem quantification:** The $2M annual loss and 8% monthly churn provide clear business context. The precision requirement (≥80%) directly ties to business constraints (discount costs), showing strong alignment between DS and business requirements.

2. **Realistic timeline and phased approach:** The 3-4 month timeline with explicit phases (exploration → development → testing → productionization) is appropriate for the scope. The emphasis on Week 1 validation (data quality check, signal validation, feasibility assessment) before full commitment is a smart de-risking strategy.

3. **Strong risk assessment:** The risk table identifies genuine concerns (data quality, weak signal, CS capacity) with realistic mitigation strategies. The emphasis on exploratory analysis upfront to validate feasibility shows good DS practice.

4. **Transparent about gaps:** The extensive use of "[NEEDS CLARIFICATION]" tags and 25 open questions demonstrates intellectual honesty. This is much better than making assumptions that could derail the project later.

5. **Good balance of precision vs. recall:** The explicit prioritization of precision over recall (given discount costs) shows clear understanding of business tradeoffs. The 10% targeting approach is appropriable for CS capacity constraints.

6. **Well-defined monitoring and maintenance:** Quarterly retraining, monitoring for drift, and outcome tracking create a sustainable long-term solution rather than a one-off model.

---

## Critical Issues (Must Fix)

1. **CS Team Capacity is a Blocker**
   - **Problem:** The entire solution depends on CS team handling outreach, but their capacity is listed as "[NEEDS CLARIFICATION]" with only a dependency note. This is mentioned as a risk but not treated with appropriate urgency.
   - **Impact:** If CS can only handle 20 users/week but the model flags 100 users/week (10% of 1000 premium users), the project delivers no value. This could invalidate the entire approach.
   - **Recommendation:** Move CS capacity confirmation to Phase 1 (Week 1) blockers. Make it explicit: "Project cannot proceed without confirmed CS capacity." If capacity is insufficient, the PRD should propose alternatives (e.g., automated email campaigns, tiered intervention strategy).

2. **Missing Baseline Metrics for Success**
   - **Problem:** The success metrics table has "[NEEDS CLARIFICATION]" for target churn rate, intervention success rate, and ROI. Without baselines and targets, it's impossible to determine if the project succeeds.
   - **Impact:** Cannot evaluate A/B test results or justify continued investment without clear success criteria.
   - **Recommendation:** Before Week 1 ends, establish:
     - Target churn rate (e.g., reduce from 8% to 6% monthly)
     - Minimum intervention success rate (e.g., 30% of flagged users saved)
     - ROI threshold (e.g., retain $500K annually to justify costs)
     Even rough estimates are better than "[NEEDS CLARIFICATION]" for core success metrics.

3. **Experiment Design Lacks Critical Details**
   - **Problem:** The A/B test section has placeholders for sample size, duration, and randomization approach. The note "[INFERRED - needs confirmation]" for randomization suggests this hasn't been discussed with stakeholders.
   - **Impact:** Without sample size calculations, the test could be underpowered (wasting time) or run too long (delaying launch). Unclear randomization could cause contamination or ethical concerns (denying help to at-risk users in control group).
   - **Recommendation:** Before launching Phase 2, work with stakeholders to:
     - Calculate minimum sample size (based on expected effect size and power)
     - Decide randomization approach (suggest: randomize among flagged users, but document ethical considerations of withholding intervention from control)
     - Define test duration (recommend: 1 billing cycle + 2 weeks = ~6 weeks for monthly billing)
     - Specify early stopping criteria if results are overwhelmingly positive/negative

---

## Suggested Improvements (Should Fix)

1. **Intervention Strategy Needs More Detail**
   - **Current state:** Lists "personalized outreach, product education, discounts, white-glove onboarding" but doesn't specify which intervention for which users or what "personalized" means.
   - **Recommendation:** Add a section describing intervention playbook:
     - How will CS decide which intervention to use?
     - Will different risk levels get different interventions?
     - What's the discount structure (% off, duration)?
     - Define "personalized" - does this require model explainability to tell CS *why* user is at risk?
   - **Why it matters:** Intervention effectiveness directly impacts ROI. A generic "here's a discount" email will perform worse than "we noticed you haven't used Feature X - let us help."

2. **Data Requirements Need More Specificity**
   - **Current state:** Lists data sources (login frequency, feature usage, support tickets) but doesn't specify:
     - Feature granularity (which specific features matter?)
     - Time windows (daily/weekly/monthly aggregations?)
     - Historical data depth (12 months? 24 months?)
   - **Recommendation:** In Phase 1, create a detailed feature specification document:
     - List specific features/tables/fields needed
     - Specify time windows for aggregation (e.g., "logins in last 7/14/30 days")
     - Document data availability and quality for each source
   - **Why it matters:** Vague data requirements lead to scope creep during development. Specifying upfront prevents "we need 18 months of data but only have 6" surprises.

3. **Missing Definition of "Premium Tier"**
   - **Current state:** Entire project targets "premium tier" users but doesn't define this segment.
   - **Recommendation:** Add clarification:
     - How many premium users are there? (affects scale)
     - What defines premium? (pricing tier, feature access, contract type?)
     - Are there sub-segments within premium? (e.g., monthly vs. annual contracts)
   - **Why it matters:** Affects sample size, model complexity, and whether different models are needed for different premium segments.

4. **Explainability Requirements Underspecified**
   - **Current state:** Marked as P1 but only says "provide interpretable signals." Doesn't specify format or level of detail.
   - **Recommendation:** Specify explainability requirements:
     - Format: Feature importance (global) + per-user top 3 risk factors
     - Audience: Must be interpretable by CS team (non-technical)
     - Example: "User at risk because: 1) No login in 14 days, 2) Support ticket unresolved for 5 days, 3) Zero usage of core feature X"
   - **Why it matters:** Explainability isn't just for model debugging - it's essential for CS team to tailor interventions effectively.

5. **Retraining Strategy Needs Operationalization**
   - **Current state:** Says "quarterly retraining" but doesn't specify who does it, how it's triggered, or what triggers re-evaluation of features.
   - **Recommendation:** Add operational details:
     - Who owns retraining? (DS team? ML Engineering?)
     - How is it triggered? (calendar-based or performance-based?)
     - What's the retraining process? (full model rebuild or incremental update?)
     - When should features be re-evaluated? (e.g., if new product features launch)
   - **Why it matters:** Many models decay because retraining is "someone else's problem." Clarify ownership upfront.

---

## Minor Issues (Nice to Have)

1. **Non-goals could be more specific:** "Predicting churn for non-premium tiers" - consider whether learnings from premium model could extend to other tiers in future.

2. **Missing section on model versioning:** How will model versions be tracked? How will you roll back if new model performs worse?

3. **No mention of regional/demographic considerations:** Are there privacy concerns with using behavioral data? Any geographic regulations (GDPR, CCPA)?

4. **Guardrail metrics are sparse:** Only mentions "overall satisfaction scores" - consider adding: support ticket volume, NPS, product usage of retained users.

5. **Alternative approaches section is thin:** Could briefly mention why simpler approaches (rule-based, logistic regression) were considered and rejected.

6. **No mention of cost of false negatives:** Focuses on precision (false positives waste discount budget), but what's the cost of missing a churning $10K/year customer?

7. **Stakeholder table missing some roles:** Consider adding: Data Engineering lead, Legal/Compliance (for privacy), Finance (for budget approval).

8. **No discussion of model bias:** Could users from certain segments be systematically under/over-flagged? How will you monitor for fairness?

---

## Completeness Checklist

- [x] Problem statement: Complete and clear
- [x] Goals: Measurable and time-bound
- [~] Success metrics: **Defined but missing baseline/target values**
- [x] Requirements: Comprehensive
- [~] Data requirements: **Good structure but needs more specificity**
- [x] Dependencies: Identified
- [x] Risks: Documented with mitigation strategies
- [x] Timeline: Reasonable and phased appropriately
- [~] Stakeholders: **Core team identified but missing DE, Legal, Finance**
- [x] Open questions: Excellent - 25 questions organized by category
- [x] Experiment design: **Framework present but critical details missing**
- [~] DS-specific requirements: **Good coverage but explainability needs detail**

---

## DS-Specific Review

### Data Requirements: Good

**Strengths:**
- Identifies specific data sources (login frequency, feature usage, support tickets, in-app behavior)
- Acknowledges data quality as a key risk
- Plans Week 1 validation of data availability and quality
- Recognizes need for historical churn outcomes (labeled data)

**Needs Work:**
- Doesn't specify how much historical data is needed (12 months? 24 months?)
- Missing granularity details (which specific features? daily/weekly/monthly aggregation?)
- No mention of class imbalance (8% churn means 92% non-churn - how will this be handled?)
- Doesn't address feature engineering complexity (temporal patterns, user cohorts, seasonal effects)

**Recommendation:** Create a detailed data specification document in Phase 1 listing:
- Required tables/fields with descriptions
- Minimum historical data depth with justification
- Expected class distribution and imbalance handling strategy
- Feature engineering plan (rolling windows, trend features, interaction terms)

### Model Requirements: Good

**Strengths:**
- Clear problem type: binary classification (churn/no-churn)
- Specific performance requirement: ≥80% precision
- Realistic approach: gradient boosting as starting point, iterate if needed
- Explicitly prioritizes precision over recall with business justification
- Defines prediction window: 2-4 weeks advance notice

**Needs Work:**
- No mention of recall targets or acceptable miss rate
- Doesn't specify calibration requirements (are the probabilities themselves meaningful?)
- Missing baseline comparison (what's random baseline? current CS team intuition?)
- No discussion of threshold selection (how to convert probability → flag decision?)

**Recommendation:**
- Add recall minimum (e.g., "achieve ≥80% precision while maintaining ≥40% recall")
- Specify whether probability calibration matters (e.g., "80% probability should mean 80% actually churn")
- Define baseline for comparison (e.g., "must beat random selection and CS team's current intuition")
- Document threshold selection process (precision-recall curve, business cost-benefit analysis)

### Infrastructure Requirements: Good

**Strengths:**
- Clear on batch vs. real-time: daily batch is sufficient
- Specifies integration point: Salesforce
- Identifies monitoring needs: drift detection, performance tracking, outcome feedback
- Realistic retraining cadence: quarterly

**Needs Work:**
- No scale estimates (how many users to score daily? data size?)
- Missing compute requirements (can this run on laptop? needs cluster?)
- Doesn't specify latency requirements (how fast must daily batch complete?)
- No mention of model storage/versioning infrastructure
- Unclear where predictions are stored (database? data warehouse? Salesforce only?)

**Recommendation:**
- Add scale context: "Score ~X,000 premium users daily, process ~Y GB data"
- Specify compute needs: "Expect model training to take <8 hours on 16-core machine"
- Define SLA: "Daily batch must complete by 8am for CS team morning review"
- Specify infrastructure: "Store predictions in [database], retain 90-day history for monitoring"

### Feasibility: Medium-High

**Assessment:** Project is feasible but has moderate execution risk.

**Positive Indicators:**
- Timeline is realistic (3-4 months for full deployment)
- Team has relevant expertise (DS Lead, Engineering Lead, CS partnership)
- Data appears to be available (usage tracking, support tickets, churn outcomes)
- Week 1 validation gates reduce risk of proceeding with bad data
- Scope is focused (premium tier only, binary classification, no real-time requirement)

**Risk Factors:**
- **CS capacity is unknown** - could invalidate entire approach
- **Data quality is unvalidated** - Mike noted this as biggest risk
- **Signal strength is unproven** - churn could be too random to predict
- **Tight timeline** - 10 weeks to testable solution is aggressive if data needs significant cleaning
- **Salesforce integration complexity** - unknown API limitations

**Recommendation:** Proceed with Phase 1, but establish hard go/no-go criteria:
- **GO if:** Data quality check passes, exploratory analysis shows signal (AUC >0.65 on basic model), CS capacity confirmed, Salesforce integration feasible
- **NO-GO if:** Data too messy to clean in timeline, no predictive signal exists, CS can't handle volume, Salesforce integration blocked

---

## Recommended Next Steps

1. **Before Phase 1 kickoff (immediate):**
   - Confirm CS team capacity with leadership (how many users/week can they handle?)
   - Establish target success metrics (target churn rate, intervention success rate, ROI threshold)
   - Get Salesforce admin access for Alex to prototype integration

2. **Phase 1 Week 1 deliverables (make explicit):**
   - Mike: Exploratory data analysis with GO/NO-GO recommendation
   - Mike: Detailed feature specification document
   - Alex: Salesforce integration feasibility assessment with effort estimate
   - Sarah: CS capacity confirmation and intervention playbook draft

3. **After Phase 1 (before Phase 2 kickoff):**
   - Finalize experiment design (sample size, duration, randomization)
   - Create detailed feature engineering plan
   - Draft model explainability requirements with CS team input
   - Estimate infrastructure costs (compute, storage, Salesforce API usage)

4. **PRD updates needed:**
   - Fill in "[NEEDS CLARIFICATION]" for success metrics (targets and baselines)
   - Add intervention strategy section with playbook details
   - Specify data requirements in more detail (features, time windows, historical depth)
   - Complete experiment design section (sample size, duration, randomization)
   - Add explainability format specification
   - Clarify CS capacity as a Phase 1 blocker

---

## Questions for Author/Stakeholders

### For Sarah (Product Lead):
1. What's the acceptable target churn rate? (e.g., reduce from 8% to what?)
2. What's the budget for discounts/interventions? (affects how many users we can target)
3. How do we measure ROI - what's the minimum retained revenue to justify the project?
4. Are there user segments within premium we care about more? (e.g., high LTV, annual contracts)
5. What happens if CS team can't handle the volume of flagged users?

### For Mike (DS Lead):
6. How much historical data do we have? (months/years)
7. What's the expected class distribution? (exactly 8% churn or does it vary?)
8. Have you done any preliminary analysis showing predictive signal exists?
9. What's your confidence this is feasible in the 10-week timeline to Q1?
10. What's the plan if gradient boosting doesn't achieve ≥80% precision?

### For Alex (Engineering Lead):
11. What are the Salesforce API limitations we should know about?
12. Where will predictions be stored? (database, data warehouse, Salesforce only?)
13. What's the compute infrastructure available for daily batch scoring?
14. How will you handle model versioning and rollback?
15. What's the monitoring infrastructure - custom dashboard or existing tooling?

### For Jessica (CS):
16. What's the current CS team capacity? (users/week realistic to handle)
17. How do you currently identify at-risk users? (baseline to beat)
18. What interventions work best in your experience?
19. How much context do you need about *why* a user is at risk? (explainability requirement)
20. Would you prefer a daily list, weekly digest, or Salesforce alerts?

### For All Stakeholders:
21. Are there data privacy or compliance concerns with using behavioral data for churn prediction?
22. Who will own model retraining and maintenance long-term?
23. What's the escalation process if model performance degrades?
24. Should we consider regional/demographic fairness in the model?
25. How will we handle users who appear on the high-risk list repeatedly?

---

## Final Recommendation

**Proceed with Phase 1, but address critical issues before Phase 2 kickoff.**

This PRD provides a solid foundation for a feasible, valuable DS project. The problem is well-defined, the approach is sensible, and the team has thought through key risks. However, three critical gaps must be resolved before committing to full development:

1. **CS capacity** must be confirmed - this is a project blocker
2. **Success metrics** need targets and baselines - otherwise you can't evaluate results
3. **Experiment design** needs details - sample size, duration, randomization

The 25 open questions demonstrate thoroughness, but prioritize answering the questions in the "Critical Issues" section first. The Phase 1 validation week is well-designed - use it to establish GO/NO-GO criteria and don't proceed to Phase 2 unless data quality, predictive signal, and CS capacity all check out.

Overall, this is a **good PRD** that's ready for stakeholder review with minor revisions. With the suggested improvements, it will be an **excellent PRD** that sets the project up for success.
