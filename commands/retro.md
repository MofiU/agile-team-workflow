---
name: retro
description: Sprint retrospective - SM facilitates, team reflects, improvements planned
---

# Sprint Retrospective Command

The Sprint Retrospective is where the team reflects on how to improve. SM facilitates.

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
  - `sailboat`: Wind, Anchor, Rock, Island
  - `starfish`: Keep, More, Less, Stop, Start

**Example:**
```
/retro start --format start-stop-continue
```

### Collect Feedback
```
/retro feedback [options]
```

Options:
- `--type`: Feedback category
- `--content`: Feedback text (required)
- `--author`: Author name (optional)

### Vote on Feedback
```
/retro vote [feedback-id]
```

Team votes to prioritize feedback.

### Generate Action Items
```
/retro actions [options]
```

Options:
- `--top`: Number of top items (default: 5)

Creates actionable items from feedback.

### Retro Report
```
/retro report [sprint-id]
```

Shows:
- Feedback by category
- Vote counts
- Action items
- Improvements planned

## Your Role as SM

### During Retrospective
- Facilitate the session
- Create safe space for feedback
- Ensure all voices are heard
- Focus on actionable improvements

### After Retrospective
- Track action items
- Follow up with team
- Measure improvement impact

## 2025 Scrum Guide

The Sprint Retrospective is an opportunity for the Scrum Team to inspect itself and create a plan for improvements.

## Data Storage

Retro data stored in:
- `.claude/agile/retros.json` - Feedback
- `.claude/agile/retro-actions.json` - Action items
