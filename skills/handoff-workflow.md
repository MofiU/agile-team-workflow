---
name: handoff-workflow
description: Handoff workflow - SM delivers to PO, PO validates, commands next iteration
---

# Handoff Workflow

The critical交接 between SM and PO after each iteration.

## Handoff Sequence

```
SM: Sprint ends
    ↓
SM: Prepares delivery report
    ↓
SM: Requests handoff to PO
    ↓
PO: Reviews deliverables
    ↓
PO: Validates against acceptance criteria
    ↓
┌─────────────────────────────────────┐
│  PO Decision:                        │
│                                       │
│  ACCEPTED → PO commands next iteration│
│  REJECTED → SM fixes issues          │
│  CONDITIONAL → SM meets conditions   │
└─────────────────────────────────────┘
    ↓
SM: Plans next Sprint (if accepted)
```

## SM's Delivery Responsibilities

### Before Handoff
- Ensure all completed items are in DONE status
- Document remaining items
- Prepare delivery report
- List blockers encountered
- Note team performance

### Delivery Report Contents
```
## Sprint [N] Delivery Report

### Sprint Goal
[Original goal]

### Goal Achievement
[Achieved/Partially Achieved/Not Achieved]

### Deliverables
- [Deliverable 1] ✓
- [Deliverable 2] ✓
- [Deliverable 3] ✗ (carried to next Sprint)

### Metrics
- Velocity: X story points
- Tasks completed: Y/Z
- Blockers resolved: Z/A

### Blockers Encountered
- [Blocker 1] - Resolved
- [Blocker 2] - Carried over

### Team Performance
[Assessment]

### Recommendations
[For next Sprint]
```

## PO's Review Responsibilities

### Review Checklist
- [ ] Deliverables match Sprint Goal?
- [ ] Quality acceptable (no critical bugs)?
- [ ] Acceptance criteria met?
- [ ] No unresolved critical blockers?
- [ ] Stakeholder value delivered?

### PO Decision Options

**ACCEPTED**
```
/handoff review HANDOFF-123 --decision accepted
```

**REJECTED** (with reason)
```
/handoff review HANDOFF-123 --decision rejected --feedback "Auth module has critical bugs"
```

**CONDITIONAL** (with conditions)
```
/handoff review HANDOFF-123 --decision conditional --conditions "Fix critical bugs, complete documentation"
```

## After Handoff Accepted

### PO Actions
1. Communicate to stakeholders
2. Adjust Product Backlog if needed
3. Review upcoming priorities
4. Command SM for next iteration

### PO Commands Next Iteration
```
/handoff next --focus "Payment integration" --continue true
```

## Continuous PO Activities

During iteration, PO should:

### Product Investigation
- Use the product as a user would
- Identify friction points
- Note improvement opportunities
- Gather stakeholder feedback

### Backlog Management
- Add new requirements from user feedback
- Adjust priorities based on learning
- Refine user stories
- Split epics into stories

### Market Analysis
- Competitive analysis
- User behavior tracking
- Industry trends
- Technical feasibility review

## Data Storage

Handoff records stored in `.claude/agile/handoffs.json`.
