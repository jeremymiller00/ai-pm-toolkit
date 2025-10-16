# App Catalog

Complete reference for all available AI PM apps in the toolkit.

## Discovery & Intake Apps

### `/stakeholder-to-prd`

**Purpose:** Convert meeting transcripts or stakeholder discussions into structured PRDs

**Input:**
- Meeting transcript (inline or file path)
- Stakeholder discussion notes
- Project description from any source

**Output:** Comprehensive PRD following the standard template

**Use Cases:**
- After product discovery meetings
- Converting email threads into structured requirements
- Documenting informal discussions

**Prompt Location:** `prompts/discovery/stakeholder-to-prd.md`

**Template Location:** `templates/prd-template.md`

**Example Workflow:**
```
1. Record stakeholder meeting
2. Save transcript to ./transcripts/
3. Run /stakeholder-to-prd
4. Review and iterate on generated PRD
```

---

## Scoping & Planning Apps

### `/ds-estimate`

**Purpose:** Generate effort estimates for data science projects

**Input:**
- PRD file path
- Project description
- Scope outline

**Output:** Detailed effort estimate with phase breakdown, timeline, and risk assessment

**Use Cases:**
- Scoping new DS projects
- Resource planning
- Timeline forecasting
- Risk identification

**Prompt Location:** `prompts/scoping/ds-estimate.md`

**Template Location:** `templates/ds-estimate-template.md`

**Key Features:**
- Phase-by-phase breakdown
- Person-weeks and calendar time
- Risk factors and contingencies
- Comparison to similar projects
- Confidence assessment

---

### `/success-metrics`

**Purpose:** Define measurable success criteria for DS projects

**Input:**
- PRD file path
- Project description
- Business goals

**Output:** Comprehensive metrics definition with baselines, targets, and measurement plan

**Use Cases:**
- Aligning on success criteria
- Experiment planning
- OKR definition
- Progress tracking

**Prompt Location:** `prompts/scoping/success-metrics.md`

**Template Location:** `templates/success-metrics-template.md`

**Key Features:**
- Primary success metrics (with SMART criteria)
- Guardrail metrics
- Secondary/diagnostic metrics
- Segmentation plan
- Statistical rigor requirements
- Tiered success criteria

---

## Communication & Alignment Apps

### `/exec-summary`

**Purpose:** Create executive-friendly summaries from technical PRDs

**Input:**
- PRD file path
- Technical documentation
- Project details

**Output:** Concise 1-2 page summary focused on business impact

**Use Cases:**
- Executive updates
- Stakeholder alignment
- Leadership reviews
- Project approvals

**Prompt Location:** `prompts/communication/exec-summary.md`

**Template Location:** `templates/exec-summary-template.md`

**Key Features:**
- Non-technical language
- Business impact focus
- Clear ask/recommendation
- Timeline and investment
- Risk summary

---

## Documentation & Quality Apps

### `/prd-reviewer`

**Purpose:** Review PRDs for completeness, clarity, and quality

**Input:**
- PRD file path

**Output:** Detailed review report with specific feedback and recommendations

**Use Cases:**
- Quality assurance
- PRD iteration
- Best practice enforcement
- Team training

**Prompt Location:** `prompts/documentation/prd-reviewer.md`

**Key Features:**
- Completeness checklist
- DS-specific requirement review
- Feasibility assessment
- Prioritized feedback (critical/suggested/minor)
- Actionable recommendations

**Review Dimensions:**
- Completeness
- Clarity
- DS-specific requirements
- Feasibility
- Strategic alignment
- Common red flags

---

## Coming Soon

The following apps are planned for future releases (see `initial_planning.md` for details):

### Discovery & Intake
- `/idea-validator` - Assess feasibility and DS effort for requests
- `/problem-clarifier` - Generate follow-up questions
- `/similar-projects` - Find similar past projects

### Scoping & Planning
- `/risk-assessment` - Identify and document risks
- `/dependencies-mapper` - Extract dependencies
- `/experimentation-plan` - Create A/B test designs

### Communication
- `/stakeholder-update` - Generate status updates
- `/ds-to-product` - Translate technical language
- `/kickoff-agenda` - Generate meeting agendas

### Documentation
- `/retro-generator` - Create retrospectives
- `/decision-log` - Extract key decisions

### Analysis
- `/impact-analyzer` - Quantify business impact
- `/priority-scorer` - Score and rank requests
- `/capacity-planner` - Match capacity to requests
- `/quarterly-roadmap` - Synthesize projects into roadmap

---

## App Usage Patterns

### Linear Workflow
Use apps sequentially for new projects:
1. `/stakeholder-to-prd` - Create initial PRD
2. `/prd-reviewer` - Identify gaps
3. `/success-metrics` - Define measurement
4. `/ds-estimate` - Scope effort
5. `/exec-summary` - Get buy-in

### Iterative Workflow
Refine documents through multiple passes:
1. Generate initial output with any app
2. Review manually
3. Run reviewer app
4. Iterate based on feedback
5. Repeat until satisfied

### Parallel Workflow
Generate multiple artifacts at once:
1. Start with a solid PRD
2. Run `/success-metrics`, `/ds-estimate`, and `/exec-summary` in parallel
3. Review all outputs together
4. Iterate as needed

### Ad-hoc Usage
Use individual apps as needed:
- Quick estimate for a meeting: `/ds-estimate`
- Exec summary for unexpected ask: `/exec-summary`
- Sanity check a PRD: `/prd-reviewer`

---

## Customization Guide

### Adapting Apps for Your Organization

Each app can be customized in three ways:

#### 1. Edit Templates (`templates/`)
Modify the output structure to match your format:
- Add/remove sections
- Change terminology
- Adjust level of detail
- Include company-specific fields

#### 2. Edit Prompts (`prompts/`)
Adjust how the AI processes information:
- Add domain-specific context
- Change tone or style
- Adjust rigor or depth
- Include organizational knowledge

#### 3. Edit Slash Commands (`.claude/commands/`)
Modify the command interface:
- Change command names
- Add pre-filled context
- Chain multiple apps
- Set default parameters

### Example Customizations

**Add Industry Context:**
Edit `prompts/scoping/ds-estimate.md` to include typical timelines for your industry

**Company-Specific Metrics:**
Edit `templates/success-metrics-template.md` to include your standard KPIs

**Simplified Executive Format:**
Edit `templates/exec-summary-template.md` to match your leadership's preferences

**Custom Approval Flow:**
Edit `templates/prd-template.md` to include your approval chain

---

## Tips for Maximum Value

### Provide Rich Input
- More detailed transcripts → better PRDs
- Specific numbers and dates → better estimates
- Clear goals → better metrics

### Iterate Freely
- Run commands multiple times
- Refine based on output
- Use review tools liberally

### Build a Library
- Save all outputs for reference
- Compare estimates to actuals
- Learn from past projects

### Chain Commands
- Use output from one app as input to another
- Build workflows that fit your process
- Automate repetitive sequences

### Customize for Your Team
- Update templates to match your standards
- Add team-specific context to prompts
- Create new apps for unique needs

---

## App Comparison Matrix

| App | Input | Output | Time | Best For |
|-----|-------|--------|------|----------|
| `/stakeholder-to-prd` | Transcript | PRD | 5-10 min | New projects |
| `/ds-estimate` | PRD/description | Estimate | 5-10 min | Planning, scoping |
| `/success-metrics` | PRD/goals | Metrics doc | 5-10 min | Alignment, experiments |
| `/exec-summary` | PRD/docs | 1-pager | 3-5 min | Exec updates |
| `/prd-reviewer` | PRD | Review report | 5-10 min | Quality checks |

---

## Getting Help

- **App not working as expected?** Check the prompt file in `prompts/` to understand the instructions
- **Want different output format?** Edit the template file in `templates/`
- **Need a new app?** See `docs/contributing.md` for how to create custom apps
- **Questions about usage?** Review examples in `examples/` or `docs/getting-started.md`
