---
name: standup
description: Daily standup - SM facilitates, team reports, track blockers
---

# Daily Standup Command

The Daily Scrum is where the team synchronizes. SM facilitates, team reports progress.

## Standup Workflow

### Start Standup
```
/standup start [sprint-id]
```

Starts today's standup session.

### Submit My Update
```
/standup update [options]
```

Options:
- `--yesterday` or `-y`: What I accomplished
- `--today` or `-t`: What I will work on
- `--blockers` or `-b`: Any blockers

**Example:**
```
/standup update --yesterday "Completed login form" --today "API integration" --blockers "Need credentials"
```

### View Updates
```
/standup updates [date]
```

Shows all team updates for the day.

### Summary (for SM)
```
/standup summary [options]
```

Options:
- `--date`: Date (default: today)
- `--format`: brief|detailed

Shows:
- Team progress toward Sprint Goal
- Blockers raised
- Action items

### Track Blockers
```
/standup blockers [options]
```

Options:
- `--sprint`: Filter by Sprint
- `--status`: active|resolved|all
- `--impact`: critical|high|medium|low

## Your Role

### As SM
- Facilitate (15 min max)
- Note blockers for follow-up
- Shield team from interruptions
- Remove impediments

### As Developer
- Answer three questions
- Focus on Sprint Goal
- Raise blockers immediately
- Coordinate with teammates

## 2025 Scrum Guide

The Daily Scrum is an internal meeting for the Development Team to synchronize work and plan the next 24 hours.

## Three Questions

1. What did I accomplish yesterday?
2. What will I work on today?
3. What blockers do I have?

## Data Storage

Standup data stored in `.claude/agile/standups.json`.
