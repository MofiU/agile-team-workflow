---
name: review
description: Sprint review - team demonstrates increment, PO inspects, stakeholders feedback
---

# Sprint Review Command

**⚠️ CRITICAL: Sprint Review is NOT a handoff. It is a collaborative inspection.**

- **Team demonstrates** what they built (developers demo their own work)
- **PO inspects** individual items against acceptance criteria
- **Stakeholders provide** feedback
- **SM facilitates** but does NOT present

---

## Sprint Review Workflow

### 1. Schedule Review
```
/review schedule [options]
```

**Required participants**: Full Scrum Team + Stakeholders

Options:
- `--sprint`: Sprint ID (default: current)
- `--date`: Review date/time
- `--participants`: Stakeholder names to invite

**Example:**
```
/review schedule --sprint sprint-123 --date "2026-03-27 14:00"
```

### 2. Team Demonstrates

**Developers demo their own work, not SM.**

```
/review demo [options]
```

Options:
- `--title`: Demo title (required)
- `--description`: What was demonstrated
- `--presenter`: Developer name (required)
- `--url`: Link to demo
- `--notes`: Additional notes

**Example:**
```
/review demo --title "User Authentication" --presenter @alice --description "Complete OAuth2 login flow"
```

### 3. PO Inspects Items

PO evaluates each completed item:

```
/review inspect [options]
```

Options:
- `--item`: Backlog item ID
- `--decision`: `accept` | `reject` | `rework`
- `--feedback`: Reason if rejected/rework

**Example:**
```
/review inspect --item AUTH-3 --decision accept
/review inspect --item AUTH-5 --decision rework --feedback "Error messages need localization"
```

### 4. Collect Stakeholder Feedback

```
/review feedback [options]
```

Options:
- `--type`: `positive` | `concern` | `suggestion`
- `--content`: Feedback text
- `--author`: Stakeholder name (optional)

### 5. Review Report

```
/review report [sprint-id]
```

Shows:
- Sprint Goal achievement
- Items: completed, rejected, rework
- Stakeholder feedback
- Product Backlog updates
- Next Sprint implications

---

## Who Does What

| Role | Action |
|------|--------|
| Developer | **Demo their own work** |
| QA | Demo testing results if applicable |
| SM | Facilitate, timebox, capture feedback |
| PO | **Inspect items against acceptance criteria** |
| Stakeholders | Provide feedback, ask questions |

---

## PO Decision Options

### Accept
Item meets acceptance criteria → Moves to Done

### Reject
Item doesn't meet criteria → Returns to backlog with priority

### Rework
Item needs fixes → Developer fixes, PO re-inspects

**Important**: PO accepts/rejects **items**, NOT the Sprint itself.

---

## Definition of Done vs Acceptance Criteria

| Concept | Owner | Purpose |
|---------|-------|---------|
| Definition of Done | **Team** | Quality standards for "done" |
| Acceptance Criteria | **PO** | Business value requirements |

Items may be "Done" (meets DoD) but not "Accepted" (doesn't meet AC).

```
Team: "AUTH-3 is Done - code reviewed, tests passing, deployed."

PO: "But the error messages aren't user-friendly. Rework."

Team: *fixes error messages*

PO: "Now accepted."
```

---

## SM Responsibilities

### Before Review
- Confirm all team members know their demo assignments
- Prepare stakeholder invite list with PO
- Book rooms/video call

### During Review
- Facilitate transitions between demos
- Timebox each demo
- Capture all feedback
- Ensure PO makes decisions on each item

### After Review
- Update backlog with PO decisions
- Log feedback for backlog refinement
- Communicate outcomes to stakeholders

---

## What NOT To Do

| ❌ Wrong | ✅ Correct |
|---------|------------|
| SM demos everything | Developers demo their own work |
| "PO, do you approve this sprint?" | "PO, any items to inspect?" |
| PO rejects entire sprint | PO accepts/rejects individual items |
| Team presents to SM | Team presents to PO + stakeholders |
| SM "delivers" to PO | Team demonstrates, PO inspects |

---

## 2025 Scrum Guide

The Sprint Review is to **inspect the outcome of the Sprint** and determine future adaptations. The Product Backlog is adjusted based on input. The Sprint Review is a working session, not a status meeting.

---

## Data Storage

Review data stored in:
- `.claude/agile/reviews.json`
- `.claude/agile/demos.json`
- `.claude/agile/review-feedback.json`
- `.claude/agile/backlog.json` (updated)
