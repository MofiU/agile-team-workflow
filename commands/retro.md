---
name: retro
description: Sprint retrospective - SM facilitates, FULL TEAM participates, improvements planned
---

# Sprint Retrospective Command

**⚠️ CRITICAL: Full Scrum Team must participate. This includes PO.**

Retrospective is where trust is built. If PO or any developer skips it, the team is signaling that their input doesn't matter.

---

## Sprint Retrospective Workflow

### 1. Start Retrospective
```
/retro start [options]
```

**Required participants**: Full Scrum Team (SM, PO, All Developers)

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

### 2. Collect Feedback
```
/retro feedback [options]
```

Options:
- `--type`: Feedback category (depends on format)
- `--content`: Feedback text (required)
- `--author`: Author name (optional, but encouraged)

**Example:**
```
/retro feedback --type continue --content "Daily standups helped us stay aligned"
```

### 3. Vote on Feedback
```
/retro vote [feedback-id]
```

Team votes to prioritize feedback (each person has limited votes).

### 4. Generate Action Items
```
/retro actions [options]
```

Options:
- `--top`: Number of top items (default: 5)

Creates actionable items from highest-voted feedback.

### 5. Retro Report
```
/retro report [sprint-id]
```

Shows:
- Feedback by category with vote counts
- Action items with owners and due dates
- Commitment from team

---

## Why PO Must Participate

PO is **not** separate from the team. PO:

- Benefits from hearing developer concerns
- Shares perspective on stakeholder pressures
- Commits to improving collaboration
- Builds trust that enables honest feedback

**If PO doesn't attend, team thinks: "PO doesn't care about our experience"**

---

## Why All Developers Must Participate

The retrospective only works if:

- Everyone shares their perspective
- Problems are surfaced, not buried
- Action items have team commitment

**If developers don't attend, the team can't improve**

---

## SM Facilitation Role

### Before Retro
- Schedule time with full team (including PO)
- Prepare materials (virtual or physical)
- Set ground rules for safe space

### During Retro
- Facilitate, don't dominate
- Ensure all voices are heard (extroverts and introverts)
- Keep discussion actionable, not whiny
- Timebox each section

### After Retro
- Document action items with owners and dates
- Follow up on previous retro actions
- Report progress at next retro

---

## Retro Formats

### Start-Stop-Continue
| Category | Question |
|----------|----------|
| Start | What should we start doing? |
| Stop | What should we stop doing? |
| Continue | What should we keep doing? |

### Mad-Sad-Glad
| Emotion | Trigger |
|---------|---------|
| Mad | What frustrated me? |
| Sad | What disappointed me? |
| Glad | What made me happy? |

### 4Ls
| Letter | Meaning |
|--------|---------|
| Liked | What did I like? |
| Learned | What did I learn? |
| Lacked | What was missing? |
| Longed For | What did I wish for? |

---

## Action Item Template

```markdown
## Sprint [N] Retro Actions

| Action | Owner | Due Date | Status |
|--------|-------|----------|--------|
| Add code review guidelines | @dev1 | Sprint N+1 | In Progress |
| Schedule 1:1s between PO and Dev | @sm | This week | Done |

## Previous Actions Follow-up
| Action | Commitment | Status |
|--------|------------|--------|
| Reduce meeting load | 30 min/day | Partially done |
```

---

## 2025 Scrum Guide

The Sprint Retrospective is an opportunity for the Scrum Team to **inspect itself** and create a plan for improvements. The Scrum Team includes the PO and SM.

---

## Data Storage

Retro data stored in:
- `.claude/agile/retros.json` - Feedback and votes
- `.claude/agile/retro-actions.json` - Action items

---

## Common Mistakes

| ❌ Wrong | ✅ Correct |
|---------|------------|
| SM runs retro alone | SM facilitates, team participates |
| PO skips retro | PO attends as team member |
| No follow-up on actions | SM tracks and reports |
| Blame and complaints | Focus on improvement |
| Same retro every time | Vary formats to keep fresh |
