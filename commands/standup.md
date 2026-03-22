---
name: standup
description: Daily standup meeting - record updates, blockers, and generate summaries
---

# Daily Standup Command

Use this command to run daily standup meetings following Scrum practices.

## Standup Workflow

### Start Standup
```
/standup start [options]
```

Options:
- `--format`: Meeting format
  - `three-questions`: Yesterday, Today, Blockers (default)
  - `update`: Progress-focused updates
  - `async`: Asynchronous updates collection

Starts a standup meeting for the active sprint.

### Submit Update
```
/standup update [options]
```

Options:
- `--member`: Team member name (required for async)
- `--yesterday` or `-y`: What was accomplished
- `--today` or `-t`: What will be worked on
- `--blockers` or `-b`: Any impediments (comma-separated)

**Example:**
```
/standup update --member "John" --yesterday "Completed login form" --today "Work on API integration" --blockers "Need API credentials"
```

### Submit Blockers Only
```
/standup blockers [options]
```

Quick way to report blockers without full update.

Options:
- `--member`: Team member name
- `--blockers`: Blockers (comma-separated)

### Standup Summary
```
/standup summary
```

Generates a summary of today's standup including:
- Participants
- Key updates
- Blockers raised
- Action items

### List Standups
```
/standup list [options]
```

Options:
- `--sprint`: Filter by sprint ID
- `--member`: Filter by team member
- `--date`: Filter by date (YYYY-MM-DD)
- `--recent`: Show recent N standups (default: 10)

## Standup Best Practices

### Three Questions Format
1. **What did you accomplish yesterday?**
2. **What will you work on today?**
3. **Any blockers?**

### Guidelines (2025 Scrum Guide)
- Time-box to 15 minutes
- Focus on progress toward Sprint Goal
- Adapt the Sprint Backlog as needed
- Raise impediments immediately
- Scrum Master facilitates and removes blockers

## Blockers Priority

| Impact | Response Time |
|--------|--------------|
| Critical | Immediate escalation |
| High | Same day resolution |
| Medium | Within 2 days |
| Low | Next sprint planning |

## Data Storage

Standup data is stored in `.claude/agile/standups.json` within the project directory.
