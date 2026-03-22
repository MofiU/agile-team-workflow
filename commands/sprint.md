---
name: sprint
description: Sprint management - create, start, end, list sprints and generate reports
---

# Sprint Management Command

Use this command to manage sprints following the 2025 Scrum Guide.

## Sprint Workflow

### Create a Sprint
```
/sprint create [options]
```

Options:
- `--name` or `-n`: Sprint name (e.g., "Sprint 23", "2025-Q1-Sprint-3")
- `--goal` or `-g`: Sprint goal statement
- `--duration` or `-d`: Duration in weeks (default: 2)
- `--start-date`: Start date YYYY-MM-DD (default: today)

**Example:**
```
/sprint create --name "Sprint 1" --goal "Complete user authentication" --duration 2
```

### Start a Sprint
```
/sprint start [sprint-id]
```

Activates a sprint and sets it as the current active sprint.

### End a Sprint
```
/sprint end [sprint-id]
```

Completes a sprint and generates a sprint report with velocity metrics.

### List Sprints
```
/sprint list [options]
```

Options:
- `--status`: Filter by status (planned|active|completed|cancelled)
- `--all`: Show all sprints (default: show recent 10)

### Update Sprint
```
/sprint update [sprint-id] [options]
```

Options:
- `--goal`: Update sprint goal
- `--status`: Update status (planned|active|completed|cancelled)
- `--achieved`: Mark goal as achieved (true|false)

### Sprint Report
```
/sprint report [sprint-id]
```

Generates a detailed sprint report including:
- Sprint goal status
- Story points committed vs completed
- Velocity metrics
- Burndown data
- Team performance

## 2025 Scrum Guide Reference

- Sprint is a fixed-length event (1-4 weeks) that contains all other Scrum events
- Each Sprint has a goal that provides a shared objective
- Sprint Planning initiates the Sprint by laying out the work to be performed
- Daily Scrum inspects progress toward the Sprint Goal and adapts the Sprint Backlog
- Sprint Review inspects the outcome of the Sprint and determines future adaptations
- Sprint Retrospective inspects individuals, interactions, tools, and Definition of Done

## Data Storage

Sprint data is stored in `.claude/agile/sprints.json` and `.claude/agile/backlog.json` within the project directory.

## Sprint Naming Convention

Recommended naming:
- Sequential: `Sprint 1`, `Sprint 2`, `Sprint 3`
- Date-based: `2025-Q1-Sprint-1`, `2025-Q2-Sprint-1`
- Theme-based: `Sprint-Auth-Feature`, `Sprint-Payment-Integration`
