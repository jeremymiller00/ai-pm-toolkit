# Getting Started with AI PM Toolkit

This guide will walk you through setting up and using the AI PM Toolkit for the first time.

## Prerequisites

- [Claude Code](https://claude.com/claude-code) installed and configured
- Basic familiarity with command-line interfaces
- Access to meeting transcripts or project descriptions (for testing)

## Installation

### Option 1: Clone from Git (Recommended)
```bash
git clone [your-repo-url] ai-pm-toolkit
cd ai-pm-toolkit
```

### Option 2: Download
1. Download the toolkit as a ZIP file
2. Extract to a directory called `ai-pm-toolkit`
3. Navigate to the directory

## Setup

1. **Open in Claude Code:**
   ```bash
   cd ai-pm-toolkit
   # Open Claude Code in this directory
   ```

2. **Verify structure:**
   Ensure you see these directories:
   - `.claude/commands/`
   - `prompts/`
   - `templates/`
   - `output/`
   - `transcripts/`

3. **Test a command:**
   Type `/stakeholder-to-prd` to verify the slash commands are loaded.

## Your First Workflow: Stakeholder Call to PRD

Let's walk through a complete example of converting a stakeholder discussion into a PRD.

### Step 1: Prepare Your Transcript

Save a meeting transcript to `./transcripts/sample-meeting.txt`. Here's an example:

```
Meeting: Product Discovery for Churn Prediction
Date: 2024-01-15
Attendees: Sarah (Product), Mike (DS Lead), Alex (Engineering)

Sarah: We're seeing about 8% monthly churn in our premium tier, which is costing us about $2M annually. I'd like to explore whether we can predict which users are likely to churn so we can intervene proactively.

Mike: That makes sense. Do we have any data on why users are churning?

Sarah: We have survey data from exit interviews, but only about 20% of churning users respond. The most common reasons are "not using features enough" and "cost".

Alex: We track a lot of usage data - logins, feature usage, support tickets. We could probably use that.

Mike: For this to be useful, we'd need to predict churn maybe 2-4 weeks in advance, so we have time to intervene. What kind of intervention are you thinking?

Sarah: Probably personalized outreach from the CS team, maybe offering a discount or product education. We'd need to prioritize though - we can't reach out to everyone.

Mike: So we'd want high precision - only flag users who are really likely to churn. What's the acceptable false positive rate?

Sarah: If we're offering discounts, we need to be pretty confident. Maybe we reach out to the top 10% most at-risk users?

Alex: Timeline-wise, when do you need this?

Sarah: We're planning a retention push for Q2, so ideally we'd have something testable by end of Q1.

Mike: That's about 10 weeks. Tight but doable if the data is clean. I'd want to do a proper A/B test to validate the impact.
```

### Step 2: Generate the PRD

1. Run the command:
   ```
   /stakeholder-to-prd
   ```

2. When prompted, provide the transcript:
   ```
   Use the transcript from ./transcripts/sample-meeting.txt
   ```

3. Claude will:
   - Read the transcript
   - Extract key information
   - Structure it into a PRD
   - Save it to `./output/prd-churn-prediction-[date].md`

4. Review the generated PRD in `./output/`

### Step 3: Review the PRD

1. Run the reviewer:
   ```
   /prd-reviewer
   ```

2. Provide the path to the generated PRD:
   ```
   ./output/prd-churn-prediction-2024-01-15.md
   ```

3. Claude will:
   - Check completeness
   - Identify gaps
   - Flag missing DS-specific requirements
   - Save review to `./output/review-churn-prediction-[date].md`

4. Review the feedback and iterate on your PRD

### Step 4: Define Success Metrics

1. Run the metrics tool:
   ```
   /success-metrics
   ```

2. Provide the PRD path:
   ```
   ./output/prd-churn-prediction-2024-01-15.md
   ```

3. Claude will:
   - Define measurable success criteria
   - Set baselines and targets
   - Identify guardrail metrics
   - Save to `./output/metrics-churn-prediction-[date].md`

### Step 5: Estimate Effort

1. Run the estimator:
   ```
   /ds-estimate
   ```

2. Provide the PRD path:
   ```
   ./output/prd-churn-prediction-2024-01-15.md
   ```

3. Claude will:
   - Break down work into phases
   - Estimate person-weeks per phase
   - Identify risks
   - Save to `./output/estimate-churn-prediction-[date].md`

### Step 6: Create Executive Summary

1. Run the exec summary tool:
   ```
   /exec-summary
   ```

2. Provide the PRD path:
   ```
   ./output/prd-churn-prediction-2024-01-15.md
   ```

3. Claude will:
   - Distill the PRD into a concise summary
   - Focus on business impact
   - Save to `./output/exec-summary-churn-prediction-[date].md`

## Understanding the Output

After running through this workflow, you'll have:

- **PRD:** Comprehensive technical requirements document
- **Review:** Quality assessment with feedback
- **Metrics:** Measurable success criteria
- **Estimate:** Effort breakdown and timeline
- **Exec Summary:** Business-focused one-pager

All saved in `./output/` for easy sharing with stakeholders.

## Tips for Success

### Provide Rich Context
- More detailed transcripts → better PRDs
- Include specific numbers, dates, and names
- Capture concerns and questions raised

### Iterate
- Use the review tool to improve documents
- Run commands multiple times as you refine
- Update templates based on your needs

### Customize
- Edit templates in `templates/` to match your format
- Adjust prompts in `prompts/` for your team's style
- Add company-specific context to prompts

### Organize Your Work
- Use consistent naming: `[artifact]-[project-name]-[date]`
- Archive old projects periodically
- Keep transcripts and outputs together

## Next Steps

### Explore Other Apps
Try the other available commands (see README.md for full list)

### Customize Templates
Edit the templates in `templates/` to match your organization's standards

### Add Your Own Apps
See `docs/contributing.md` for how to create custom apps

### Integrate into Your Workflow
- Set up git for version control
- Share outputs with stakeholders
- Build a library of past projects for reference

## Troubleshooting

### Commands Not Found
- Ensure you're in the `ai-pm-toolkit` directory
- Check that `.claude/commands/` exists and contains the command files

### Poor Quality Output
- Provide more context in your input
- Review and customize the prompts in `prompts/`
- Iterate: use review tools and refine

### File Not Found Errors
- Use relative paths from the toolkit root
- Ensure transcripts are in `./transcripts/`
- Check file names for typos

## Getting Help

- Review the full planning doc: `initial-planning.md`
- Check prompt instructions in `prompts/`
- Look at template structure in `templates/`
- Review example outputs in `examples/`

## What's Next?

Once you're comfortable with the basics:
1. Customize templates for your organization
2. Add company-specific context to prompts
3. Create new apps for your specific needs
4. Build a workflow that fits your team

Happy product managing!
