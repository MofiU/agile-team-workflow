---
name: handoff
description: Handoff - coordination with external teams after sprint completion
---

# Handoff Command

**⚠️ THIS IS NOT: SM delivers to PO. That is Sprint Review.**

This command is for **external handoff** - coordinating with other teams/systems after Sprint Review:
- DevOps (deployment)
- Another squad (integration)
- QA (handoff testing)
- Support (knowledge transfer)

---

## When to Use This

```
Sprint Review Complete
        ↓
Internal: Team reflects in Retrospective
        ↓
External: Coordinate with other teams
```

Example scenarios:
- DevOps takes deployment
- API team takes microservice
- QA team takes for regression
- Support team gets knowledge base

---

## Handoff Workflow

### 1. Initiate Handoff
```
/handoff initiate [options]
```

Options:
- `--sprint`: Sprint ID (required)
- `--to`: Target team/person (required)
- `--deliverables`: What is being handed off
- `--type`: `deployment` | `integration` | `knowledge` | `testing`

**Example:**
```
/handoff initiate --sprint sprint-123 --to "DevOps" --deliverables "Auth module v2.1" --type deployment
```

### 2. Confirm Receipt
```
/handoff confirm [handoff-id] [options]
```

Options:
- `--status`: `accepted` | `rejected` | `pending-info`
- `--feedback`: Additional notes
- `--timeline`: Expected completion

**Example:**
```
/handoff confirm HANDOFF-456 --status accepted --timeline "Deploy by Friday"
```

### 3. Track Status
```
/handoff status [handoff-id]
```

Shows:
- Handoff details
- Current status
- Timeline
- Any blockers

### 4. Handoff Report
```
/handoff report [sprint-id]
```

Shows all handoffs from a sprint:
- Who received what
- Status of each
- Timeline adherence

---

## Internal vs External

| Type | This Command | Sprint Review |
|------|--------------|---------------|
| Purpose | Coordinate with other teams | Inspect increment |
| Participants | Team + external party | Full team + stakeholders |
| Goal | Transfer ownership | Gather feedback |
| Timing | After Sprint Review | End of Sprint |

---

## DevOps Handoff Example

```
SM: Sprint Review complete. Auth module ready for deploy.

DevOps: Great. What's the handoff?

SM: 
/handoff initiate --sprint sprint-123 --to DevOps --deliverables "Auth module, DB migrations, runbook" --type deployment

DevOps:
/handoff confirm HANDOFF-789 --status accepted --timeline "Tuesday deploy"

        ↓ (after deploy)

DevOps:
/handoff confirm HANDOFF-789 --status accepted --feedback "Deployed successfully"
```

---

## Knowledge Transfer Example

```
SM: Sprint done. We built a new knowledge base article.

Support: Can you walk me through it?

SM:
/handoff initiate --sprint sprint-123 --to Support --deliverables "KB-123: Auth module guide" --type knowledge

Support:
/handoff confirm HANDOFF-789 --status accepted
```

---

## What NOT To Use This For

| ❌ Wrong Use | ✅ Correct Use |
|-------------|---------------|
| SM → PO "delivery" | Team → DevOps (deployment) |
| PO "approval" | Team → QA (testing) |
| Sprint "acceptance" | Team → Another squad (integration) |

---

## Data Storage

Handoff data stored in `.claude/agile/handoffs.json`.
