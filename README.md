# AI PM Toolkit

A collection of AI-powered tools to automate and streamline product management tasks for data science projects. Built for use with [Claude Code](https://claude.com/claude-code).

## Overview

This toolkit helps bridge the gap between data science teams and product organizations by automating common PM workflows like:
- Converting stakeholder discussions into structured PRDs
- Estimating data science effort
- Creating executive summaries
- Reviewing PRDs for quality
- Defining success metrics

## Quick Start

1. Clone this repo or download it to your local machine
2. Open the `ai-pm-toolkit` directory in Claude Code
3. Use the slash commands to access the AI PM apps

## Available Apps

### `/stakeholder-to-prd`
Convert meeting transcripts or stakeholder discussions into comprehensive PRDs.

**Usage:**
```
/stakeholder-to-prd
```
Then provide your transcript (inline or as a file path).

**Output:** Structured PRD saved to `./output/prd-[project-name]-[date].md`

---

### `/ds-estimate`
Generate effort estimates for data science projects with phase breakdowns and risk assessment.

**Usage:**
```
/ds-estimate
```
Then provide a PRD file path or project description.

**Output:** Detailed estimate saved to `./output/estimate-[project-name]-[date].md`

---

### `/exec-summary`
Distill technical PRDs into concise executive summaries focused on business impact.

**Usage:**
```
/exec-summary
```
Then provide the PRD file path or project description.

**Output:** Executive summary saved to `./output/exec-summary-[project-name]-[date].md`

---

### `/prd-reviewer`
Review PRDs for completeness, clarity, and DS-specific requirements.

**Usage:**
```
/prd-reviewer
```
Then provide the PRD file path to review.

**Output:** Detailed review saved to `./output/review-[project-name]-[date].md`

---

### `/success-metrics`
Define measurable success criteria including primary metrics, guardrails, and measurement approach.

**Usage:**
```
/success-metrics
```
Then provide a PRD or project description.

**Output:** Metrics definition saved to `./output/metrics-[project-name]-[date].md`

---

## Typical Workflows

### New Project Intake
1. Record stakeholder meeting
2. Use `/stakeholder-to-prd` to generate initial PRD
3. Use `/prd-reviewer` to identify gaps
4. Use `/success-metrics` to define measurement
5. Use `/ds-estimate` to scope effort
6. Use `/exec-summary` to get leadership buy-in

### Project Planning
1. Use `/ds-estimate` for effort estimation
2. Use `/success-metrics` to align on goals
3. Use `/exec-summary` for stakeholder updates

### Quality Review
1. Use `/prd-reviewer` to check PRD completeness
2. Iterate based on feedback

## Directory Structure

```
ai-pm-toolkit/
├── .claude/commands/      # Slash command definitions
├── prompts/               # Detailed prompt instructions for each app
├── templates/             # Output templates (PRD, estimates, etc.)
├── examples/              # Sample inputs/outputs
├── transcripts/           # Store meeting transcripts here
├── output/                # Generated documents saved here
└── docs/                  # Additional documentation
```

## Customization

### Adapting Templates
Edit files in `templates/` to match your organization's format:
- `prd-template.md` - PRD structure
- `ds-estimate-template.md` - Effort estimation format
- `exec-summary-template.md` - Executive summary format
- `success-metrics-template.md` - Metrics definition format

### Adapting Prompts
Edit files in `prompts/` to change how the AI processes information:
- Adjust for your team's terminology
- Add company-specific context
- Change the level of detail or rigor

### Adding New Apps
1. Create a prompt file in `prompts/[category]/[app-name].md`
2. Create a template in `templates/[app-name]-template.md` (if needed)
3. Create a slash command in `.claude/commands/[app-name].md`

## Best Practices

### For Best Results
- **Provide context:** The more detail you provide, the better the output
- **Iterate:** Use the review tools to improve documents
- **Customize:** Adapt templates to your organization's needs
- **Chain commands:** Use output from one app as input to another

### File Organization
- Store meeting transcripts in `./transcripts/`
- Review generated outputs in `./output/`
- Keep templates version-controlled
- Archive old projects to keep directories clean

## Support

This toolkit is designed to work with Claude Code. For questions or issues:
- Check the documentation in `docs/`
- Review example usage in `examples/`
- Refer to prompt instructions in `prompts/`

## Future Enhancements

Potential additions (see `initial_planning.md` for full list):
- `/idea-validator` - Assess feasibility of incoming requests
- `/risk-assessment` - Identify and document project risks
- `/experimentation-plan` - Create A/B test designs
- `/stakeholder-update` - Generate status updates
- `/impact-analyzer` - Quantify business impact

## License

[Your license here]

## Contributing

[Your contribution guidelines here]
