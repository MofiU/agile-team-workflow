---
name: review
description: Sprint review - SM facilitates, team demos, stakeholders feedback
---

# Sprint Review Command

The Sprint Review is where the team demos completed work. SM facilitates, team presents.

## Review Workflow

### Schedule Review
```
/review schedule [options]
```

Options:
- `--sprint`: Sprint ID (default: current)
- `--date`: Review date/time
- `--participants`: Stakeholder names

### Record Demo
```
/review demo [options]
```

Options:
- `--title`: Demo title (required)
- `--description`: What was demonstrated
- `--url`: Link to demo
- `--notes`: Additional notes

**Example:**
```
/review demo --title "User Authentication" --description "Complete OAuth2 login flow" --url "https://demo.example.com"
```

### Collect Feedback
```
/review feedback [options]
```

Options:
- `--type`: Feedback type
  - `positive`: What works well
  - `concern`: Issues or concerns
  - `suggestion`: Improvement suggestions
- `--content`: Feedback text (required)
- `--author`: Stakeholder name (optional)

### Review Report
```
/review report [sprint-id]
```

Shows:
- Sprint Goal achievement
- Completed items
- Stakeholder feedback
- Product Backlog updates

## Your Role as SM

### Before Review
- Prepare demo schedule with team
- Invite key stakeholders
- Ensure demos are ready

### During Review
- Facilitate the session
- Ensure clear presentation of value
- Capture stakeholder feedback
- Plan next steps

### After Review
- Update Product Backlog with feedback
- Communicate outcomes
- Plan adjustments to next Sprint

## 2025 Scrum Guide

The Sprint Review is to inspect the outcome of the Sprint and determine future adaptations. The Product Backlog is adjusted based on input.

## Data Storage

Review data stored in:
- `.claude/agile/reviews.json`
- `.claude/agile/demos.json`
- `.claude/agile/review-feedback.json`
