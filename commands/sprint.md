---
name: sprint
description: Sprint management - SM controls sprint lifecycle, team commits to sprint goal
---

# Sprint Command

**⚠️ CRITICAL: SM controls Sprint lifecycle. Team commits. PO provides priorities.**

This is NOT:
- PO creating sprints
- PO commanding the team
- SM delivering work to PO

This IS:
- SM orchestrates sprint ceremonies
- Team commits to Sprint Goal based on capacity
- PO provides priorities and accepts/rejects individual items

---

## Sprint Lifecycle

### 1. Sprint Planning (Team Commits)

```
SM facilitates → PO presents priorities → Team commits to capacity
```

**Required participants**: SM, PO, All Developers
**Timebox**: Up to 8 hours for 2-week sprint

```
/sprint planning [options]
```

Options:
- `--goal`: Sprint goal statement (required)
- `--sprint-id`: Sprint identifier (auto-generated if not provided)
- `--duration`: Duration in weeks (default: 2)

**Example:**
```
/sprint planning --goal "Complete user authentication module" --duration 2
```

### 2. Daily Scrum (Team Syncs)

**Required participants**: Developers working that day
**Optional**: SM
**Timebox**: 15 minutes max

```
/sprint daily [options]
```

Options:
- `--yesterday`: What you did yesterday
- `--today`: What you'll do today
- `--blockers`: Any impediments

**Example:**
```
/sprint daily --yesterday "Completed login form" --today "API integration" --blockers "None"
```

### 3. Sprint Review (Team Demonstrates)

**⚠️ NOT a handoff. Team demonstrates. PO inspects.**

**Required participants**: Full Scrum Team + Stakeholders
**Timebox**: Up to 4 hours for 2-week sprint

```
/sprint review [sprint-id]
```

Shows:
- What was built (developers demo)
- What was not completed
- Next steps for Product Backlog

**After Sprint Review**: SM and Team clean up, then **fresh Sprint Planning begins**

### 4. Sprint Retrospective (Team Reflects)

**Required participants**: Full Scrum Team (including PO)
**Timebox**: Up to 3 hours for 2-week sprint

```
/retro start --format start-stop-continue
```

---

## SM Responsibilities

### Sprint Planning
- Schedule and facilitate the meeting
- Ensure team understands Sprint Goal
- Team commits based on capacity (not SM or PO dictating)
- Break items into tasks

### During Sprint
- Run Daily Scrums (15 min, same time daily)
- Track blockers and remove impediments
- Protect team from scope changes
- Update sprint board

### Sprint Review
- Facilitate (team presents)
- Ensure feedback is captured
- Coordinate with PO for stakeholder engagement

### Sprint Retrospective
- Facilitate the session
- Create safe space for honest feedback
- Ensure action items are tracked

---

## PO Responsibilities

### Sprint Planning
- Present top-priority backlog items
- Answer questions about requirements
- Clarify acceptance criteria
- **Does NOT commit the team**

### During Sprint
- Be available for clarifications
- Resist scope changes
- Update backlog based on learning

### Sprint Review
- Inspect the increment
- Accept/reject individual items (not the sprint)
- Gather stakeholder feedback

### Sprint Retrospective
- **Participate as a team member**
- Share perspective on collaboration
- Commit to improvements

---

## Team Commitments

**Developers**:
- Commit to what they can realistically deliver
- Break work into tasks
- Update progress daily
- Raise blockers immediately

**The team self-organizes** - SM facilitates, doesn't manage.

---

## Sprint States

| State | Description |
|-------|-------------|
| `planned` | Sprint planned, not started |
| `active` | Sprint in progress |
| `review` | Sprint ended, review scheduled |
| `completed` | Review done, retro done |

---

## Cancel Sprint

Only cancel if Sprint Goal is no longer valuable.

```
/sprint cancel [sprint-id] --reason "Business priorities changed"
```

---

## 2025 Scrum Guide

The Sprint Goal provides a shared objective. Even if Product Backlog items change, the Sprint Goal remains the focus. The Developers maintain the Sprint Goal.

---

## Data Storage

Sprint data stored in `.claude/agile/sprints.json`.
