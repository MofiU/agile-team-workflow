---
name: review
description: Sprint review meeting - demo completed work, collect stakeholder feedback
---

# Sprint Review Command

Use this command to conduct sprint review meetings following Scrum practices.

## Review Workflow

### Start Review
```
/review start [options]
```

Options:
- `--sprint`: Sprint ID to review (default: current/last sprint)
- `--participants`: Stakeholder names/roles (comma-separated)

Starts a sprint review session.

### Record Demo
```
/review demo [options]
```

Options:
- `--title`: Demo title (required)
- `--description`: What was demonstrated
- `--url`: Link to live demo or recording
- `--notes`: Additional notes

**Example:**
```
/review demo --title "User Authentication" --description "Complete OAuth2 login flow" --url "https://demo.example.com/auth"
```

### Record Feedback
```
/review feedback [options]
```

Options:
- `--type`: Feedback type
  - `positive`: What works well
  - `concern`: Issues or concerns
  - `suggestion`: Improvement suggestions
- `--content`: Feedback text (required)
- `--author`: Author/stakeholder name (optional)

### Review Report
```
/review report [options]
```

Options:
- `--sprint`: Sprint ID (default: latest completed)

Generates a sprint review report including:
- Sprint goal achievement status
- Completed items demoed
- Incomplete items
- Stakeholder feedback summary
- Next steps

## Review Best Practices

### Guidelines (2025 Scrum Guide)
- Held at the end of each Sprint
- Inspect the outcome of the Sprint
- Determine future adaptations
- Collaborate on the next steps
- Time-box to 4 hours for a 2-week sprint

### Attendees
- Development Team
- Product Owner
- Scrum Master
- Key Stakeholders
- Anyone interested in the product

### Agenda Template
1. Welcome and sprint goal review (5 min)
2. Demo completed items (30-60 min)
3. Q&A and discussion (30 min)
4. Stakeholder feedback collection (20 min)
5. Next sprint preview (10 min)
6. Wrap-up and action items (5 min)

## Feedback Categories

| Type | Purpose | Action |
|------|---------|--------|
| Positive | Acknowledge what worked | Continue doing |
| Concern | Flag potential issues | Investigate and address |
| Suggestion | Ideas for improvement | Evaluate and prioritize |

## Data Storage

Review data is stored in:
- `.claude/agile/reviews.json` - Review sessions
- `.claude/agile/demos.json` - Demo records
- `.claude/agile/review-feedback.json` - Feedback entries
