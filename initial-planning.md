# AI PM Toolkit - Initial Planning

## Feature/App Ideas for AI PM Automation

### 1. **Discovery & Intake**
- **`/stakeholder-to-prd`** - Convert meeting transcripts into structured PRD drafts
- **`/idea-validator`** - Assess feasibility, data requirements, and DS effort for incoming requests
- **`/problem-clarifier`** - Generate follow-up questions to refine vague requests
- **`/similar-projects`** - Search for similar past DS projects to inform scoping

### 2. **Scoping & Planning**
- **`/ds-estimate`** - Generate effort estimates (person-weeks) based on project description
- **`/success-metrics`** - Define measurable success criteria and KPIs
- **`/risk-assessment`** - Identify technical, data, and organizational risks
- **`/dependencies-mapper`** - Extract and track dependencies on data, teams, or infrastructure
- **`/experimentation-plan`** - Create A/B test or experiment design from requirements

### 3. **Communication & Alignment**
- **`/exec-summary`** - Distill technical PRDs into executive summaries
- **`/stakeholder-update`** - Generate status updates from project notes/activity
- **`/ds-to-product`** - Translate DS technical language to product-friendly terms
- **`/kickoff-agenda`** - Generate meeting agendas for project kickoffs

### 4. **Documentation & Knowledge Management**
- **`/retro-generator`** - Create retrospective documents from project notes
- **`/doc-template-filler`** - Auto-populate templates with context from conversations
- **`/project-index`** - Maintain searchable index of all DS projects and status
- **`/decision-log`** - Extract and format key decisions from meeting notes

### 5. **Analysis & Insights**
- **`/impact-analyzer`** - Quantify expected business impact from DS work
- **`/priority-scorer`** - Score and rank multiple project requests
- **`/capacity-planner`** - Match DS team capacity against incoming requests
- **`/quarterly-roadmap`** - Synthesize multiple projects into roadmap view

### 6. **Quality & Review**
- **`/prd-reviewer`** - Check PRDs for completeness, clarity, and DS-specific requirements
- **`/requirements-validator`** - Ensure data requirements are well-specified
- **`/handoff-checklist`** - Generate handoff documentation for DS→Engineering transitions

---

## Recommended Repo Architecture

```
ai-pm-toolkit/
├── .claude/
│   └── commands/
│       ├── stakeholder-to-prd.md
│       ├── idea-validator.md
│       ├── ds-estimate.md
│       ├── success-metrics.md
│       └── ...
│
├── prompts/
│   ├── discovery/
│   │   ├── stakeholder-to-prd.md
│   │   ├── idea-validator.md
│   │   └── problem-clarifier.md
│   ├── scoping/
│   │   ├── ds-estimate.md
│   │   ├── risk-assessment.md
│   │   └── experimentation-plan.md
│   ├── communication/
│   │   ├── exec-summary.md
│   │   └── stakeholder-update.md
│   └── documentation/
│       ├── retro-generator.md
│       └── decision-log.md
│
├── templates/
│   ├── prd-template.md
│   ├── experiment-design-template.md
│   ├── ds-estimate-template.md
│   ├── kickoff-agenda-template.md
│   ├── exec-summary-template.md
│   └── retro-template.md
│
├── examples/
│   ├── sample-transcript.txt
│   ├── sample-prd.md
│   └── sample-exec-summary.md
│
├── docs/
│   ├── README.md
│   ├── getting-started.md
│   ├── app-catalog.md (index of all apps)
│   └── contributing.md
│
├── workflows/
│   └── intake-to-kickoff.md (multi-step workflows)
│
└── utils/
    └── prompt-builder.md (reusable prompt components)
```

### Key Design Principles:

1. **`.claude/commands/` as the interface**: Each slash command is a thin wrapper that pulls in the actual prompt from `prompts/` and relevant template from `templates/`

2. **Separation of concerns**:
   - `prompts/` = the AI logic/instructions
   - `templates/` = the output structures
   - `examples/` = sample inputs/outputs for testing

3. **Composability**: Prompts reference templates and can chain together (e.g., `/stakeholder-to-prd` → `/prd-reviewer`)

4. **Context-aware**: Prompts should reference where to find inputs (e.g., "use transcript from `./transcripts/latest.txt`")

### Next Steps:

1. Start with **3-5 high-impact apps** (I'd suggest: stakeholder-to-prd, ds-estimate, exec-summary, prd-reviewer, success-metrics)
2. Create the basic repo structure
3. Build one complete app end-to-end as a template
4. Iterate based on actual usage

### Potential Next Actions:

- **Create the initial repo structure** with a starter set of apps
- **Deep-dive into specific apps** (e.g., build out the `/stakeholder-to-prd` workflow)
- **Refine the architecture** based on feedback
