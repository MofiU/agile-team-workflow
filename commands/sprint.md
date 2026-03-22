---
name: sprint
description: Sprint management - team commits, configurable turns, quorum-based attendance
---

# Sprint Command

**⚠️ CRITICAL: Team commits. PO provides priorities. SM facilitates.**

**Sprint capacity = configurable conversation turns** (default: 35, adjustable 25-40)

---

## Sprint Lifecycle

### Turn Budget (Default: 35 Turns)

| Ceremony | Turns | Notes |
|----------|-------|-------|
| Sprint Planning | 3 | Goal + commitment |
| Daily Scrums (10 days) | 10 | 1 turn per day |
| Backlog Refinement | 2 | As needed |
| Development | 18 | Main work |
| Sprint Review | 1 | Team demo |
| Sprint Retrospective | 1 | Team reflection |
| **TOTAL** | **35** | configurable |

**Team decides what they can commit in configured turns.**

### Configurable Turns

```
/sprint config --turns 30   # Struggling team
/sprint config --turns 40   # High-performing team
```

**Recommendation**: Start at 35, adjust after 2 sprints.

### Turn Borrowing (Emergency)

```
/sprint borrow --turns 5   # Emergency, team consensus required
```

### 1. Sprint Planning (Quorum Required)

```
SM facilitates → PO presents priorities → Team commits to capacity
```

**Quorum**: 2/3 of team + ALL Developers + PO + SM
**All developers MUST attend** (no proxy, no exception)

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

**Participants**: Developers working that day (no quorum needed)
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

**Quorum**: 2/3 of team + stakeholders
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

**Quorum**: 2/3 of team (including PO)
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
