---
name: sprint
description: Sprint planning and management - PO creates sprints with goals, reviews progress
---

# Sprint Planning Command (Product Owner)

As the Product Owner, you create and manage Sprints to deliver value. The Sprint Goal is your commitment to stakeholders.

## Sprint Planning Workflow

### Plan a New Sprint
```
/sprint plan [options]
```

Options:
- `--goal` or `-g`: Sprint goal statement (required)
- `--duration` or `-d`: Duration in weeks (default: 2)
- `--start-date`: Start date YYYY-MM-DD (default: next business day)
- `--capacity`: Expected team capacity (story points)

**Example:**
```
/sprint plan --goal "Launch user authentication for Q1 launch" --duration 2 --capacity 34
```

### Review Sprint Status
```
/sprint status [sprint-id]
```

Shows:
- Progress toward Sprint Goal
- Completed vs committed items
- Blockers affecting delivery
- Team health indicators

### Review Sprint Report
```
/sprint report [sprint-id]
```

Generated after Sprint ends:
- Sprint Goal achievement
- Velocity metrics
- Items completed vs planned
- Lessons for next Sprint

### Cancel Sprint (if goal is obsolete)
```
/sprint cancel [sprint-id] --reason "Business priorities changed"
```

Only cancel if Sprint Goal is no longer valuable.

## Your Responsibilities as PO

### Sprint Planning
- Present the Sprint Goal clearly
- Communicate product priorities
- Make scope decisions
- Commit to delivering value

### During Sprint
- Remain available for clarification
- Resist scope changes unless critical
- Monitor progress toward goal
- Make acceptance decisions

### Sprint Review
- Demonstrate completed value
- Gather stakeholder feedback
- Adapt Product Backlog based on feedback
- Plan next Sprint

## 2025 Scrum Guide

The Sprint Goal provides a shared objective. Even if the Product Backlog items change, the Sprint Goal remains the focus.

## Data Storage

Sprint data stored in `.claude/agile/sprints.json` - you own this as PO.
