# Success Metrics Definition: [Project Name]

**Project:** [Project Name]

**Date:** [Date]

**Owner:** [Name]

---

## Primary Success Metrics

These are the key metrics that define project success. If these don't move, the project has not succeeded.

### 1. [Primary Metric Name]

**Definition:** [Exact definition of how this metric is calculated]

**Current Baseline:** [X] ([as of date])

**Target:** [Y] ([by when])

**Measurement Method:** [How we'll measure this - dashboard, query, experiment, etc.]

**Why This Matters:** [Business impact of moving this metric]

**Confidence in Baseline:** [High/Medium/Low] - [Any caveats about current measurement]

---

### 2. [Secondary Primary Metric - if applicable]

**Definition:** [Exact definition]

**Current Baseline:** [X]

**Target:** [Y]

**Measurement Method:** [How we'll measure]

**Why This Matters:** [Business impact]

---

## Guardrail Metrics

These metrics ensure we don't break existing functionality or harm the user experience while pursuing our goals.

| Metric | Current Value | Acceptable Range | Why It Matters |
|--------|---------------|------------------|----------------|
| [Guardrail 1] | [X] | [Must stay above/below Y] | [Impact if degraded] |
| [Guardrail 2] | [X] | [Must stay above/below Y] | [Impact if degraded] |
| [Guardrail 3] | [X] | [Must stay above/below Y] | [Impact if degraded] |

---

## Secondary/Diagnostic Metrics

These help us understand *how* and *why* the primary metrics are moving, but aren't success criteria themselves.

| Metric | Purpose | Target Direction |
|--------|---------|------------------|
| [Diagnostic 1] | [What this tells us] | [Increase/Decrease/Maintain] |
| [Diagnostic 2] | [What this tells us] | [Increase/Decrease/Maintain] |
| [Diagnostic 3] | [What this tells us] | [Increase/Decrease/Maintain] |

---

## Segmentation Plan

How we'll break down metrics to understand impact across different user groups or contexts.

**Key Segments:**
- **[Segment 1]:** [e.g., New users vs. returning users]
  - *Hypothesis:* [Expected differential impact]
- **[Segment 2]:** [e.g., Mobile vs. desktop]
  - *Hypothesis:* [Expected differential impact]
- **[Segment 3]:** [e.g., By region, product tier, etc.]
  - *Hypothesis:* [Expected differential impact]

---

## Success Criteria Tiers

Clear definitions of what different levels of success look like.

### Minimum Success
**Criteria:** [Minimum bar to call this worthwhile]
- [Primary metric moves by at least X%]
- [No degradation in key guardrails]

**Interpretation:** Project delivered value but less than hoped

---

### Expected Success
**Criteria:** [What we realistically expect based on past projects]
- [Primary metric moves by Y%]
- [Guardrails maintained]
- [Secondary metrics show expected patterns]

**Interpretation:** Project met goals

---

### Exceptional Success
**Criteria:** [Best-case scenario]
- [Primary metric moves by Z%]
- [Unexpected positive impacts on other metrics]

**Interpretation:** Project exceeded expectations

---

## Measurement Plan

### Data Sources
- **[Metric 1]:** [Table/dashboard/system where this is tracked]
- **[Metric 2]:** [Table/dashboard/system where this is tracked]

### Measurement Frequency
- **During Development:** [How often we check progress]
- **During Experiment:** [How often we monitor A/B test]
- **Post-Launch:** [Ongoing monitoring cadence]

### Statistical Rigor
- **Minimum Detectable Effect (MDE):** [X%]
- **Statistical Significance:** [p < 0.05 or other threshold]
- **Sample Size Required:** [N users/sessions]
- **Experiment Duration:** [X days/weeks]

### Dashboards/Tools
- **Primary Dashboard:** [Link or name]
- **Data Access:** [How to query the data]
- **Alerting:** [Any automated alerts set up]

---

## Risks & Caveats

### Measurement Risks
1. **[Risk 1]:** [e.g., "Metric is noisy and may take 4 weeks to see signal"]
   - **Mitigation:** [How we'll address]

2. **[Risk 2]:** [e.g., "Data pipeline has 24hr delay"]
   - **Mitigation:** [How we'll address]

### Interpretation Challenges
1. **[Challenge 1]:** [e.g., "Metric may be affected by seasonality"]
   - **How to account for it:** [Approach]

2. **[Challenge 2]:** [e.g., "Hard to isolate impact from other concurrent changes"]
   - **How to account for it:** [Approach]

---

## Definition of Done

The project is complete when:

- [ ] [Primary metric] reaches [target] with statistical significance
- [ ] All guardrail metrics remain within acceptable ranges
- [ ] Results have been validated across key segments
- [ ] [X weeks] of post-launch monitoring shows sustained impact
- [ ] Results documented and presented to stakeholders

**OR** (if experiment-based)

- [ ] Experiment runs for minimum [X days]
- [ ] Reaches statistical significance (p < 0.05)
- [ ] Decision made to ship/not ship based on results
- [ ] Results documented regardless of outcome

---

## Alternatives Considered

**Why not [Alternative Metric X]?**
[Reasoning for why this wasn't chosen as a primary metric]

**Why not [Alternative Metric Y]?**
[Reasoning]

---

## Historical Context

**Similar Past Projects:**
| Project | Primary Metric | Result | Lessons |
|---------|----------------|--------|---------|
| [Project 1] | [Metric] | [+X%] | [What we learned] |
| [Project 2] | [Metric] | [-Y%] | [What we learned] |

**How This Informs Our Targets:**
[Explanation of how past results inform current goals]

---

## Sign-off

- [ ] PM approved metrics definition
- [ ] DS lead confirmed metrics are measurable
- [ ] Data analyst validated baseline and measurement approach
- [ ] Key stakeholders agree these metrics define success

**Approved By:** [Name]

**Date:** [Date]
