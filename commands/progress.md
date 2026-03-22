---
name: progress
description: View project progress - skills/commands to check current status
---

# Progress Command

Skills and commands to check current project status. Available to all stakeholders.

## Quick Status

### Sprint Progress
```
/progress sprint [sprint-id]
```

Shows:
- Sprint Goal progress
- Tasks completed vs planned
- Days remaining
- Blockers count

### Team Progress
```
/progress team [sprint-id]
```

Shows:
- Per-member task completion
- Team velocity
- Collaboration metrics

### Backlog Progress
```
/progress backlog [options]
```

Shows:
- Items by status
- Priority distribution
- Recent additions

### Blockers Progress
```
/progress blockers [sprint-id]
```

Shows:
- Active blockers
- Resolved this Sprint
- Blocker trends

## Detailed Reports

### Velocity Report
```
/progress velocity
```

Shows:
- Historical velocity chart
- Average velocity
- Trend direction

### Quality Report
```
/progress quality
```

Shows:
- Bugs found vs resolved
- Test coverage
- Technical debt items

### Team Performance
```
/progress performance
```

Shows:
- Tasks by member
- Completion rates
- Average cycle time

## Stakeholder View

### For PO
```
/progress po
```

Shows:
- Sprint Goal achievement probability
- Upcoming deliverables
- Backlog health
- Risk indicators

### For SM
```
/progress sm
```

Shows:
- Team capacity
- Blocker status
- Ceremony schedule
- Action items

### For User/Stakeholder
```
/progress status
```

Shows:
- Current sprint progress
- What's been delivered
- What's coming next

## Real-Time Dashboard

### Daily Summary
```
/progress daily
```

Shows:
- Today's standup summary
- Tasks updated
- Blockers raised/resolved
- Next actions

### Weekly Summary
```
/progress weekly
```

Shows:
- Week's completed items
- Velocity
- Team highlights
- Blockers resolved

## Data Storage

Progress data aggregated from:
- `.claude/agile/sprints.json`
- `.claude/agile/board.json`
- `.claude/agile/backlog.json`
- `.claude/agile/blockers.json`
