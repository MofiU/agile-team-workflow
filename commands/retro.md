---
name: retro
description: Sprint retrospective - start, collect feedback, vote, and generate action items
---

# Sprint Retrospective Command

Use this command to conduct sprint retrospectives following Scrum practices.

## Retro Workflow

### Start Retrospective
```
/retro start [options]
```

Options:
- `--format`: Retro format (required)
  - `start-stop-continue`: What to start, stop, continue (default)
  - `mad-sad-glad`: Emotional check-in format
  - `4ls`: Liked, Learned, Lacked, Longed For
  - `sailboat`: Wind (positives), Anchor (negatives), Rock (risks), Island (goals)
  - `starfish`: Keep, More, Less, Stop, Start
  - `flower`: 6 petals for different aspects

**Example:**
```
/retro start --format start-stop-continue
```

### Collect Feedback
```
/retro feedback [options]
```

Options:
- `--type`: Feedback category (depends on format)
- `--content`: Feedback text (required)
- `--author`: Author name (optional for anonymity)

**Format-specific Categories:**

**start-stop-continue:**
- `start`: Things the team should start doing
- `stop`: Things the team should stop doing
- `continue`: Things the team should continue doing

**mad-sad-glad:**
- `mad`: Frustrating experiences
- `sad`: Disappointing experiences
- `glad`: Positive experiences

**4ls:**
- `loved`: Things enjoyed
- `learned`: Knowledge gained
- `lacked`: Missing elements
- `longed-for`: Desired improvements

### Vote on Feedback
```
/retro vote [feedback-id]
```

Team members vote on important feedback items to prioritize action planning.

### Generate Action Items
```
/retro actions [options]
```

Options:
- `--format`: Output format (list|board)
- `--top`: Number of top items to action (default: 5)

Creates actionable items from the most voted feedback.

### Retro Report
```
/retro report
```

Generates a comprehensive retro report including:
- Feedback summary by category
- Vote counts
- Action items
- Improvement recommendations

## Retrospective Best Practices

### Guidelines (2025 Scrum Guide)
- Held at the end of each Sprint
- Inspect how the last Sprint went regarding individuals, interactions, tools, Definition of Done
- Create a plan for implementing improvements
- Time-box to 3 hours for a 2-week sprint

### Blending Formats
Combine elements from different formats:
- Sailboat + 4ls: Use wind/anchor for team, 4ls for personal growth
- Start-Stop-Continue + Starfish: Start/stop/continue with the 5 Starfish categories

## Data Storage

Retro data is stored in:
- `.claude/agile/retros.json` - Feedback entries
- `.claude/agile/retro-actions.json` - Action items
